---
template: lesson.html
title: Monitoring Machine Learning Systems
description: Learn how to monitor ML systems to identify and address sources of drift to prevent model performance decay.
keywords: monitoring, monitoring ml, drift, data drift, concept drift, mlops, machine learning
image: https://madewithml.com/static/images/mlops.png
repository: https://github.com/GokuMohandas/Made-With-ML
notebook: https://github.com/GokuMohandas/monitoring-ml/blob/main/monitoring.ipynb
---

## Intuition

Even though we've trained and thoroughly evaluated our model, the real work begins once we deploy to production. This is one of the fundamental differences between traditional software engineering and ML development. Traditionally, with rule based, deterministic, software, the majority of the work occurs at the initial stage and once deployed, our system works as we've defined it. But with machine learning, we haven't explicitly defined how something works but used data to architect a probabilistic solution. This approach is subject to natural performance degradation over time, as well as unintended behavior, since the data exposed to the model will be different from what it has been trained on. This isn't something we should be trying to avoid but rather understand and mitigate as much as possible. In this lesson, we'll understand the short comings from attempting to capture performance degradation in order to motivate the need for [drift](#drift) detection.

!!! tip
    We highly recommend that you explore this lesson *after* completing the previous lessons since the topics (and code) are iteratively developed. We did, however, create the :fontawesome-brands-github:{ .github } [monitoring-ml](https://github.com/GokuMohandas/monitoring-ml){:target="_blank"} repository for a quick overview with an interactive notebook.

## System health

The first step to insure that our model is performing well is to ensure that the actual system is up and running as it should. This can include metrics specific to service requests such as latency, throughput, error rates, etc. as well as infrastructure utilization such as CPU/GPU utilization, memory, etc.

<div class="ai-center-all">
    <a href="https://miro.medium.com/max/2400/1*DQdiQupXSSd3fldg9eAQjA.jpeg" target="_blank"><img width="600" src="/static/images/mlops/monitoring/system_health.png" alt="system health dashboard"></a>
</div>

Fortunately, most cloud providers and even orchestration layers will provide this insight into our system's health for free through a dashboard. In the event we don't, we can easily use [Grafana](https://grafana.com/){:target="_blank"}, [Datadog](https://www.datadoghq.com/){:target="_blank"}, etc. to ingest system performance metrics from logs to create a customized dashboard and set alerts.

## Performance

Unfortunately, just monitoring the system's health won't be enough to capture the underlying issues with our model. So, naturally, the next layer of metrics to monitor involves the model's performance. These could be quantitative evaluation metrics that we used during model evaluation (accuracy, precision, f1, etc.) but also key business metrics that the model influences (ROI, click rate, etc.).

It's usually never enough to just analyze the cumulative performance metrics across the entire span of time since the model has been deployed. Instead, we should also inspect performance across a period of time that's significant for our application (ex. daily). These sliding metrics might be more indicative of our system's health and we might be able to identify issues faster by not obscuring them with historical data.

> 👉 &nbsp; Follow along interactive notebook in the :fontawesome-brands-github:{ .github } [**monitoring-ml**](https://github.com/GokuMohandas/monitoring-ml){:target="_blank"} repository as we implement the concepts below.

```python linenums="1"
import matplotlib.pyplot as plt
import numpy as np
import seaborn as sns
sns.set_theme()
```
```python linenums="1"
# Generate data
hourly_f1 = list(np.random.randint(low=94, high=98, size=24*20)) + \
            list(np.random.randint(low=92, high=96, size=24*5)) + \
            list(np.random.randint(low=88, high=96, size=24*5)) + \
            list(np.random.randint(low=86, high=92, size=24*5))
```
```python linenums="1"
# Cumulative f1
cumulative_f1 = [np.mean(hourly_f1[:n]) for n in range(1, len(hourly_f1)+1)]
print (f"Average cumulative f1 on the last day: {np.mean(cumulative_f1[-24:]):.1f}")
```
<pre class="output">
Average cumulative f1 on the last day: 93.7
</pre>
```python linenums="1"
# Sliding f1
window_size = 24
sliding_f1 = np.convolve(hourly_f1, np.ones(window_size)/window_size, mode="valid")
print (f"Average sliding f1 on the last day: {np.mean(sliding_f1[-24:]):.1f}")
```
<pre class="output">
Average sliding f1 on the last day: 88.6
</pre>
```python linenums="1"
plt.ylim([80, 100])
plt.hlines(y=90, xmin=0, xmax=len(hourly_f1), colors="blue", linestyles="dashed", label="threshold")
plt.plot(cumulative_f1, label="cumulative")
plt.plot(sliding_f1, label="sliding")
plt.legend()
```

<div class="ai-center-all">
    <img width="500" src="/static/images/mlops/monitoring/performance_drift.png" alt="performance drift">
</div>

> We may need to monitor metrics at various window sizes to catch performance degradation as soon as possible. Here we're monitoring the overall f1 but we can do the same for slices of data, individual classes, etc. For example, if we monitor the performance on a specific tag, we may be able to quickly catch new algorithms that were released for that tag (ex. new transformer architecture).

## Delayed outcomes

We may not always have the ground-truth outcomes available to determine the model's performance on production inputs. This is especially true if there is significant lag or annotation is required on the real-world data. To mitigate this, we could:

- devise an **approximate signal** that can help us *estimate* the model's performance. For example, in our tag prediction task, we could use the actual tags that an author attributes to a project as the intermediary labels until we have verified labels from an annotation pipeline.
- label a small subset of our live dataset to estimate performance. This subset should try to be representative of the various distributions in the live data.

## Importance weighting

However, approximate signals are not always available for every situation because there is no feedback on the ML system’s outputs or it’s too delayed. For these situations, a recent line of research relies on the only component that’s available in all situations: the input data.

<div class="ai-center-all">
    <img width="700" src="/static/images/mlops/monitoring/mandoline.png" alt="importance weighting with mandoline">
</div>
<div class="ai-center-all">
    <small><a href="https://arxiv.org/abs/2107.00643" target="_blank">Mandoline: Model Evaluation under Distribution Shift</a></small>
</div>

The core idea is to develop slicing functions that may potentially capture the ways our data may experience distribution shift. These slicing functions should capture obvious slices such as class labels or different categorical feature values but also slices based on implicit metadata (hidden aspects of the data that are not explicit feature columns). These slicing functions are then applied to our labeled dataset to create matrices with the corresponding labels. The same slicing functions are applied to our unlabeled production data to approximate what the weighted labels would be. With this, we can determine the approximate performance! The intuition here is that we can better approximate performance on our unlabeled dataset based on the similarity between the labeled slice matrix and unlabeled slice matrix. A core dependency of this assumption is that our slicing functions are comprehensive enough that they capture the causes of distributional shift.

!!! warning
    If we wait to catch the model decay based on the performance, it may have already caused significant damage to downstream business pipelines that are dependent on it. We need to employ more fine-grained monitoring to identify the *sources* of model drift prior to actual performance degradation.

## Drift

We need to first understand the different types of issues that can cause our model's performance to decay (model drift). The best way to do this is to look at all the moving pieces of what we're trying to model and how each one can experience drift.

<center>

| Entity               | Description                              | Drift                                                               |
| :------------------- | :--------------------------------------- | :------------------------------------------------------------------ |
| $X$                  | inputs (features)                        | data drift     $\rightarrow P(X) \neq P_{ref}(X)$                 |
| $y$                  | outputs (ground-truth)                   | target drift   $\rightarrow P(y) \neq P_{ref}(y)$                 |
| $P(y \vert X)$       | actual relationship between $X$ and $y$  | concept drift  $\rightarrow P(y \vert X) \neq P_{ref}(y \vert X)$ |

</center>

### Data drift

Data drift, also known as feature drift or covariate shift, occurs when the distribution of the *production* data is different from the *training* data. The model is not equipped to deal with this drift in the feature space and so, it's predictions may not be reliable. The actual cause of drift can be attributed to natural changes in the real-world but also to systemic issues such as missing data, pipeline errors, schema changes, etc. It's important to inspect the drifted data and trace it back along it's pipeline to identify when and where the drift was introduced.

!!! warning
    Besides just looking at the distribution of our input data, we also want to ensure that the workflows to retrieve and process our input data is the same during training and serving to avoid training-serving skew. However, we can skip this step if we retrieve our features from the same source location for both training and serving, ie. from a [feature store](feature-store.md){:target="_blank"}.

<div class="ai-center-all">
    <img width="700" src="/static/images/mlops/monitoring/data_drift.png" alt="data drift">
</div>
<div class="ai-center-all">
    <small>Data drift can occur in either continuous or categorical features.</small>
</div>

> As data starts to drift, we may not yet notice significant decay in our model's performance, especially if the model is able to interpolate well. However, this is a great opportunity to [potentially](#solutions) retrain before the drift starts to impact performance.

### Target drift

Besides just the input data changing, as with data drift, we can also experience drift in our outcomes. This can be a shift in the distributions but also the removal or addition of new classes with categorical tasks. Though retraining can mitigate the performance decay caused target drift, it can often be avoided with proper inter-pipeline communication about new classes, schema changes, etc.

### Concept drift

Besides the input and output data drifting, we can have the actual relationship between them drift as well. This concept drift renders our model ineffective because the patterns it learned to map between the original inputs and outputs are no longer relevant. Concept drift can be something that occurs in [various patterns](https://link.springer.com/article/10.1007/s11227-018-2674-1){:target="_blank"}:

<div class="ai-center-all">
    <img width="500" src="/static/images/mlops/monitoring/concept_drift.png" alt="concept drift">
</div>

- gradually over a period of time
- abruptly as a result of an external event
- periodically as a result of recurring events

> All the different types of drift we discussed can can occur simultaneously which can complicated identifying the sources of drift.

## Locating drift

Now that we've identified the different types of drift, we need to learn how to locate and how often to measure it. Here are the constraints we need to consider:

- **reference window**: the set of points to compare production data distributions with to identify drift.
- **test window**: the set of points to compare with the reference window to determine if drift has occurred.

Since we're dealing with online drift detection (ie. detecting drift in live production data as opposed to past batch data), we can employ either a [fixed or sliding window approach](https://onlinelibrary.wiley.com/doi/full/10.1002/widm.1381){:target="_blank"} to identify our set of points for comparison. Typically, the reference window is a fixed, recent subset of the training data while the test window slides over time.

[Scikit-multiflow](https://scikit-multiflow.github.io/){:target="_blank"} provides a toolkit for concept drift detection [techniques](https://scikit-multiflow.readthedocs.io/en/stable/api/api.html#module-skmultiflow.drift_detection){:target="_blank"} directly on streaming data. The package offers windowed, moving average functionality (including dynamic preprocessing) and even methods around concepts like [gradual concept drift](https://scikit-multiflow.readthedocs.io/en/stable/api/generated/skmultiflow.drift_detection.EDDM.html#skmultiflow-drift-detection-eddm){:target="_blank"}.

> We can also compare across various window sizes simultaneously to ensure smaller cases of drift aren't averaged out by large window sizes.

## Measuring drift

Once we have the window of points we wish to compare, we need to know how to compare them.

```python linenums="1"
import great_expectations as ge
import json
import pandas as pd
from urllib.request import urlopen
```
```python linenums="1"
# Load labeled projects
projects = pd.read_csv("https://raw.githubusercontent.com/GokuMohandas/Made-With-ML/main/datasets/projects.csv")
tags = pd.read_csv("https://raw.githubusercontent.com/GokuMohandas/Made-With-ML/main/datasets/tags.csv")
df = ge.dataset.PandasDataset(pd.merge(projects, tags, on="id"))
df["text"] = df.title + " " + df.description
df.drop(["title", "description"], axis=1, inplace=True)
df.head(5)
```

<pre class="output">
<div class="output_subarea output_html rendered_html output_result" dir="auto"><div>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>id</th>
      <th>created_on</th>
      <th>tag</th>
      <th>text</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>6</td>
      <td>2020-02-20 06:43:18</td>
      <td>computer-vision</td>
      <td>Comparison between YOLO and RCNN on real world...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>7</td>
      <td>2020-02-20 06:47:21</td>
      <td>computer-vision</td>
      <td>Show, Infer &amp; Tell: Contextual Inference for C...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>9</td>
      <td>2020-02-24 16:24:45</td>
      <td>graph-learning</td>
      <td>Awesome Graph Classification A collection of i...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>15</td>
      <td>2020-02-28 23:55:26</td>
      <td>reinforcement-learning</td>
      <td>Awesome Monte Carlo Tree Search A curated list...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>19</td>
      <td>2020-03-03 13:54:31</td>
      <td>graph-learning</td>
      <td>Diffusion to Vector Reference implementation o...</td>
    </tr>
  </tbody>
</table>
</div></div>
</pre>

### Expectations

The first form of measurement can be rule-based such as validating [expectations](https://docs.greatexpectations.io/en/latest/reference/glossary_of_expectations.html){:target="_blank"} around missing values, data types, value ranges, etc. as we did in our [data testing lesson](testing.md#expectations){:target="_blank"}. The difference now is that we'll be validating these expectations on live production data.

```python linenums="1"
# Simulated production data
prod_df = ge.dataset.PandasDataset([{"text": "hello"}, {"text": 0}, {"text": "world"}])
```
```python linenums="1"
# Expectation suite
df.expect_column_values_to_not_be_null(column="text")
df.expect_column_values_to_be_of_type(column="text", type_="str")
expectation_suite = df.get_expectation_suite()
```
```python linenums="1"
# Validate reference data
df.validate(expectation_suite=expectation_suite, only_return_failures=True)["statistics"]
```
<pre class="output">
{'evaluated_expectations': 2,
 'success_percent': 100.0,
 'successful_expectations': 2,
 'unsuccessful_expectations': 0}
</pre>
```python linenums="1"
# Validate production data
prod_df.validate(expectation_suite=expectation_suite, only_return_failures=True)["statistics"]
```
<pre class="output">
{'evaluated_expectations': 2,
 'success_percent': 50.0,
 'successful_expectations': 1,
 'unsuccessful_expectations': 1}
</pre>

Once we've validated our rule-based expectations, we need to quantitatively measure drift across the different features in our data.

### Univariate

Our task may involve univariate (1D) features that we will want to monitor. While there are many types of hypothesis tests we can use, a popular option is the [Kolmogorov-Smirnov (KS) test](https://en.wikipedia.org/wiki/Kolmogorov%E2%80%93Smirnov_test){:target="_blank"}.

#### Kolmogorov-Smirnov (KS) test

The KS test determines the maximum distance between two distribution's cumulative density functions. Here, we'll measure if there is any drift on the size of our input text feature between two different data subsets.

!!! tip
    While text is a direct feature in our task, we can also monitor other implicit features such as % of unknown tokens in text (need to maintain a training vocabulary), etc. While they may not be used for our machine learning model, they can be great indicators for detecting drift.

```python linenums="1"
from alibi_detect.cd import KSDrift
```

```python linenums="1"
# Reference
df["num_tokens"] = df.text.apply(lambda x: len(x.split(" ")))
ref = df["num_tokens"][0:200].to_numpy()
plt.hist(ref, alpha=0.75, label="reference")
plt.legend()
plt.show()
```

```python linenums="1"
# Initialize drift detector
length_drift_detector = KSDrift(ref, p_val=0.01)
```

```python linenums="1"
# No drift
no_drift = df["num_tokens"][200:400].to_numpy()
plt.hist(ref, alpha=0.75, label="reference")
plt.hist(no_drift, alpha=0.5, label="test")
plt.legend()
plt.show()
```

<div class="ai-center-all">
    <img width="500" src="/static/images/mlops/monitoring/ks_no_drift.png" alt="no drift with KS test">
</div>

```python linenums="1"
length_drift_detector.predict(no_drift, return_p_val=True, return_distance=True)
```

<pre class="output">
{'data': {'distance': array([0.09], dtype=float32),
  'is_drift': 0,
  'p_val': array([0.3927307], dtype=float32),
  'threshold': 0.01},
 'meta': {'data_type': None,
  'detector_type': 'offline',
  'name': 'KSDrift',
  'version': '0.9.1'}}
</pre>

> &darr; p-value = &uarr; confident that the distributions are different.

```python linenums="1"
# Drift
drift = np.random.normal(30, 5, len(ref))
plt.hist(ref, alpha=0.75, label="reference")
plt.hist(drift, alpha=0.5, label="test")
plt.legend()
plt.show()
```

<div class="ai-center-all">
    <img width="500" src="/static/images/mlops/monitoring/ks_drift.png" alt="drift detection with KS">
</div>

```python linenums="1"
length_drift_detector.predict(drift, return_p_val=True, return_distance=True)
```

<pre class="output">
{'data': {'distance': array([0.63], dtype=float32),
  'is_drift': 1,
  'p_val': array([6.7101775e-35], dtype=float32),
  'threshold': 0.01},
 'meta': {'data_type': None,
  'detector_type': 'offline',
  'name': 'KSDrift',
  'version': '0.9.1'}}
</pre>

#### Chi-squared test

Similarly, for categorical data (input features, targets, etc.), we can apply the [Pearson's chi-squared test](https://en.wikipedia.org/wiki/Pearson%27s_chi-squared_test){:target="_blank"} to determine if a frequency of events in production is consistent with a reference distribution.

> We're creating a categorical variable for the # of tokens in our text feature but we could very very apply it to the tag distribution itself, individual tags (binary), slices of tags, etc.

```python linenums="1"
from alibi_detect.cd import ChiSquareDrift
```

```python linenums="1"
# Reference
df.token_count = df.num_tokens.apply(lambda x: "small" if x <= 10 else ("medium" if x <=25 else "large"))
ref = df.token_count[0:200].to_numpy()
plt.hist(ref, alpha=0.75, label="reference")
plt.legend()
```

```python linenums="1"
# Initialize drift detector
target_drift_detector = ChiSquareDrift(ref, p_val=0.01)
```

```python linenums="1"
# No drift
no_drift = df.token_count[200:400].to_numpy()
plt.hist(ref, alpha=0.75, label="reference")
plt.hist(no_drift, alpha=0.5, label="test")
plt.legend()
plt.show()
```

<div class="ai-center-all">
    <img width="500" src="/static/images/mlops/monitoring/chi_no_drift.png" alt="no drift with chi squared test">
</div>

```python linenums="1"
target_drift_detector.predict(no_drift, return_p_val=True, return_distance=True)
```

<pre class="output">
{'data': {'distance': array([4.135522], dtype=float32),
  'is_drift': 0,
  'p_val': array([0.12646863], dtype=float32),
  'threshold': 0.01},
 'meta': {'data_type': None,
  'detector_type': 'offline',
  'name': 'ChiSquareDrift',
  'version': '0.9.1'}}
</pre>

```python linenums="1"
# Drift
drift = np.array(["small"]*80 + ["medium"]*40 + ["large"]*80)
plt.hist(ref, alpha=0.75, label="reference")
plt.hist(drift, alpha=0.5, label="test")
plt.legend()
plt.show()
```

<div class="ai-center-all">
    <img width="500" src="/static/images/mlops/monitoring/chi_drift.png" alt="drift detection with chi squared tests">
</div>

```python linenums="1"
target_drift_detector.predict(drift, return_p_val=True, return_distance=True)
```

<pre class="output">
{'data': {'is_drift': 1,
  'distance': array([118.03355], dtype=float32),
  'p_val': array([2.3406739e-26], dtype=float32),
  'threshold': 0.01},
 'meta': {'name': 'ChiSquareDrift',
  'detector_type': 'offline',
  'data_type': None}}
</pre>

### Multivariate

As we can see, measuring drift is fairly straightforward for univariate data but difficult for multivariate data. We'll summarize the reduce and measure approach outlined in the following paper: [Failing Loudly: An Empirical Study of Methods for Detecting Dataset Shift](https://arxiv.org/abs/1810.11953){:target="_blank"}.

<div class="ai-center-all">
    <img width="700" src="/static/images/mlops/monitoring/failing_loudly.png" alt="multivariate drift detection">
</div>
We vectorized our text using tf-idf (to keep modeling simple), which has high dimensionality and is not semantically rich in context. However, typically with text, word/char embeddings are used. So to illustrate what drift detection on multivariate data would look like, let's represent our text using pretrained embeddings.

> Be sure to refer to our [embeddings](../foundations/embeddings.md){:target="_blank"} and [transformers](../foundations/transformers.md){:target="_blank"} lessons to learn more about these topics. But note that detecting drift on multivariate text embeddings is still quite difficult so it's typically more common to use these methods applied to tabular features or images.

We'll start by loading the tokenizer from a pretrained model.

```python linenums="1"
from transformers import AutoTokenizer
```

```python linenums="1"
model_name = "allenai/scibert_scivocab_uncased"
tokenizer = AutoTokenizer.from_pretrained(model_name)
vocab_size = len(tokenizer)
print (vocab_size)
```

<pre class="output">
31090
</pre>

```python linenums="1"
# Tokenize inputs
encoded_input = tokenizer(df.text.tolist(), return_tensors="pt", padding=True)
ids = encoded_input["input_ids"]
masks = encoded_input["attention_mask"]
```

```python linenums="1"
# Decode
print (f"{ids[0]}\n{tokenizer.decode(ids[0])}")
```

<pre class="output">
tensor([  102,  2029,   467,  1778,   609,   137,  6446,  4857,   191,  1332,
         2399, 13572, 19125,  1983,   147,  1954,   165,  6240,   205,   185,
          300,  3717,  7434,  1262,   121,   537,   201,   137,  1040,   111,
          545,   121,  4714,   205,   103,     0,     0,     0,     0,     0,
            0,     0,     0,     0,     0,     0,     0,     0,     0,     0,
            0,     0,     0,     0,     0,     0,     0,     0,     0,     0,
            0])
[CLS] comparison between yolo and rcnn on real world videos bringing theory to experiment is cool. we can easily train models in colab and find the results in minutes. [SEP] [PAD] [PAD] ...
</pre>

```python linenums="1"
# Sub-word tokens
print (tokenizer.convert_ids_to_tokens(ids=ids[0]))
```

<pre class="output">
['[CLS]', 'comparison', 'between', 'yo', '##lo', 'and', 'rc', '##nn', 'on', 'real', 'world', 'videos', 'bringing', 'theory', 'to', 'experiment', 'is', 'cool', '.', 'we', 'can', 'easily', 'train', 'models', 'in', 'col', '##ab', 'and', 'find', 'the', 'results', 'in', 'minutes', '.', '[SEP]', '[PAD]', '[PAD]', ...]
</pre>

Next, we'll load the pretrained model's weights and use the `TransformerEmbedding` object to extract the embeddings from the hidden state (averaged across tokens).

```python linenums="1"
from alibi_detect.models.pytorch import TransformerEmbedding
```

```python linenums="1"
# Embedding layer
emb_type = "hidden_state"
layers = [-x for x in range(1, 9)]  # last 8 layers
embedding_layer = TransformerEmbedding(model_name, emb_type, layers)
```

```python linenums="1"
# Embedding dimension
embedding_dim = embedding_layer.model.embeddings.word_embeddings.embedding_dim
embedding_dim
```

<pre class="output">
768
</pre>

#### Dimensionality reduction

Now we need to use a dimensionality reduction method to reduce our representations dimensions into something more manageable (ex. 32 dim) so we can run our two-sample tests on to detect drift. Popular options include:

- [Principle component analysis (PCA)](https://en.wikipedia.org/wiki/Principal_component_analysis){:target="_blank"}: orthogonal transformations that preserve the variability of the dataset.
- [Autoencoders (AE)](https://en.wikipedia.org/wiki/Autoencoder){:target="_blank"}: networks that consume the inputs and attempt to reconstruct it from an lower dimensional space while minimizing the error. These can either be trained or untrained (the Failing loudly paper recommends untrained).
- [Black box shift detectors (BBSD)](https://arxiv.org/abs/1802.03916){:target="_blank"}: the actual model trained on the training data can be used as a dimensionality reducer. We can either use the softmax outputs (multivariate) or the actual predictions (univariate).

```python linenums="1"
import torch
import torch.nn as nn
```

```python linenums="1"
# Device
device = torch.device("cuda" if torch.cuda.is_available() else "cpu")
print(device)
```

<pre class="output">
cuda
</pre>

```python linenums="1"
# Untrained autoencoder (UAE) reducer
encoder_dim = 32
reducer = nn.Sequential(
    embedding_layer,
    nn.Linear(embedding_dim, 256),
    nn.ReLU(),
    nn.Linear(256, encoder_dim)
).to(device).eval()
```

We can wrap all of the operations above into one preprocessing function that will consume input text and produce the reduced representation.

```python linenums="1"
from alibi_detect.cd.pytorch import preprocess_drift
from functools import partial
```

```python linenums="1"
# Preprocessing with the reducer
max_len = 100
batch_size = 32
preprocess_fn = partial(preprocess_drift, model=reducer, tokenizer=tokenizer,
                        max_len=max_len, batch_size=batch_size, device=device)
```

#### Maximum Mean Discrepancy (MMD)

After applying dimensionality reduction techniques on our multivariate data, we can use different statistical tests to calculate drift. A popular option is [Maximum Mean Discrepancy (MMD)](https://jmlr.csail.mit.edu/papers/v13/gretton12a.html){:target="_blank"}, a kernel-based approach that determines the distance between two distributions by computing the distance between the mean embeddings of the features from both distributions.

```python linenums="1"
from alibi_detect.cd import MMDDrift
```

```python linenums="1"
# Initialize drift detector
mmd_drift_detector = MMDDrift(ref, backend="pytorch", p_val=.01, preprocess_fn=preprocess_fn)
```

```python linenums="1"
# No drift
no_drift = df.text[200:400].to_list()
mmd_drift_detector.predict(no_drift)
```

<pre class="output">
{'data': {'distance': 0.0021169185638427734,
  'distance_threshold': 0.0032651424,
  'is_drift': 0,
  'p_val': 0.05999999865889549,
  'threshold': 0.01},
 'meta': {'backend': 'pytorch',
  'data_type': None,
  'detector_type': 'offline',
  'name': 'MMDDriftTorch',
  'version': '0.9.1'}}
</pre>

```python linenums="1"
# Drift
drift = ["UNK " + text for text in no_drift]
mmd_drift_detector.predict(drift)
```

<pre class="output">
{'data': {'distance': 0.014705955982208252,
  'distance_threshold': 0.003908038,
  'is_drift': 1,
  'p_val': 0.0,
  'threshold': 0.01},
 'meta': {'backend': 'pytorch',
  'data_type': None,
  'detector_type': 'offline',
  'name': 'MMDDriftTorch',
  'version': '0.9.1'}}
</pre>

## Online

So far we've applied our drift detection methods on offline data to try and understand what reference window sizes should be, what p-values are appropriate, etc. However, we'll need to apply these methods in the online production setting so that we can catch drift as easy as possible.

> Many monitoring libraries and platforms come with [online equivalents](https://docs.seldon.io/projects/alibi-detect/en/latest/cd/methods.html#online){:target="_blank"} for their detection methods.

Typically, reference windows are large so that we have a proper benchmark to compare our production data points to. As for the test window, the smaller it is, the more quickly we can catch sudden drift. Whereas, a larger test window will allow us to identify more subtle/gradual drift. So it's best to compose windows of different sizes to regularly monitor.

```python linenums="1"
from alibi_detect.cd import MMDDriftOnline
```

```python linenums="1"
# Online MMD drift detector
ref = df.text[0:800].to_list()
online_mmd_drift_detector = MMDDriftOnline(
    ref, ert=400, window_size=200, backend="pytorch", preprocess_fn=preprocess_fn)
```

<pre class="output">
Generating permutations of kernel matrix..
100%|██████████| 1000/1000 [00:00<00:00, 13784.22it/s]
Computing thresholds: 100%|██████████| 200/200 [00:32<00:00,  6.11it/s]
</pre>

As data starts to flow in, we can use the detector to predict drift at every point. Our detector should detect drift sooner in our drifter dataset than in our normal data.

```python linenums="1"
def simulate_production(test_window):
    i = 0
    online_mmd_drift_detector.reset()
    for text in test_window:
        result = online_mmd_drift_detector.predict(text)
        is_drift = result["data"]["is_drift"]
        if is_drift:
            break
        else:
            i += 1
    print (f"{i} steps")
```

```python linenums="1"
# Normal
test_window = df.text[800:]
simulate_production(test_window)
```

<pre class="output">
27 steps
</pre>

```python linenums="1"
# Drift
test_window = "UNK" * len(df.text[800:])
simulate_production(test_window)
```

<pre class="output">
11 steps
</pre>

There are also several considerations around how often to refresh both the reference and test windows. We could base in on the number of new observations or time without drift, etc. We can also adjust the various thresholds (ERT, window size, etc.) based on what we learn about our system through monitoring.

## Outliers

With drift, we're comparing a window of production data with reference data as opposed to looking at any one specific data point. While each individual point may not be an anomaly or outlier, the group of points may cause a drift. The easiest way to illustrate this is to imagine feeding our live model the same input data point repeatedly. The actual data point may not have anomalous features but feeding it repeatedly will cause the feature distribution to change and lead to drift.

<div class="ai-center-all">
    <img width="600" src="/static/images/mlops/monitoring/outliers.png" alt="outlier detection">
</div>

Unfortunately, it's not very easy to detect outliers because it's hard to constitute the criteria for an outlier. Therefore the outlier detection task is typically unsupervised and requires a stochastic streaming algorithm to identify potential outliers. Luckily, there are several powerful libraries such as [PyOD](https://pyod.readthedocs.io/en/latest/){:target="_blank"}, [Alibi Detect](https://docs.seldon.io/projects/alibi-detect/en/latest/){:target="_blank"}, [WhyLogs](https://whylogs.readthedocs.io/en/latest/){:target="_blank"} (uses [Apache DataSketches](https://datasketches.apache.org/){:target="_blank"}), etc. that offer a suite of outlier detection functionality (largely for tabular and image data for now).

Typically, outlier detection algorithms fit (ex. via reconstruction) to the training set to understand what normal data looks like and then we can use a threshold to predict outliers. If we have a small labeled dataset with outliers, we can empirically choose our threshold but if not, we can choose some reasonable tolerance.

```python linenums="1"
from alibi_detect.od import OutlierVAE
X_train = (n_samples, n_features)
outlier_detector = OutlierVAE(
    threshold=0.05,
    encoder_net=encoder,
    decoder_net=decoder,
    latent_dim=512
)
outlier_detector.fit(X_train, epochs=50)
outlier_detector.infer_threshold(X, threshold_perc=95)  # infer from % outliers
preds = outlier_detector.predict(X, outlier_type="instance", outlier_perc=75)
```

> When we identify outliers, we may want to let the end user know that the model's response may not be reliable. Additionally, we may want to remove the outliers from the next training set or further inspect them and upsample them in case they're early signs of what future distributions of incoming features will look like.

## Solutions

It's not enough to just be able to measure drift or identify outliers but to also be able to act on it. We want to be able to alert on drift, inspect it and then act on it.

### Alert

Once we've identified outliers and/or measured statistically significant drift, we need to a devise a workflow to notify stakeholders of the issues. A negative connotation with monitoring is fatigue stemming from false positive alerts. This can be mitigated by choosing the appropriate constraints (ex. alerting thresholds) based on what's important to our specific application. For example, thresholds could be:

- fixed values/range for situations where we're concretely aware of expected upper/lower bounds.
```python linenums="1"
if percentage_unk_tokens > 5%:
    trigger_alert()
```
- [forecasted](https://www.datadoghq.com/blog/forecasts-datadog/){;target="_blank"} thresholds dependent on previous inputs, time, etc.
```python linenums="1"
if current_f1 < forecast_f1(current_time):
    trigger_alert()
```
- appropriate p-values for different drift detectors (&darr; p-value = &uarr; confident that the distributions are different).
```python linenums="1"
from alibi_detect.cd import KSDrift
length_drift_detector = KSDrift(reference, p_val=0.01)
```

Once we have our carefully crafted alerting workflows in place, we can notify stakeholders as issues arise via email, [Slack](https://slack.com/){:target="_blank"}, [PageDuty](https://www.pagerduty.com/){:target="_blank"}, etc. The stakeholders can be of various levels (core engineers, managers, etc.) and they can subscribe to the alerts that are relevant for them.

### Inspect

Once we receive an alert, we need to inspect it before acting on it. An alert needs several components in order for us to completely inspect it:

- specific alert that was triggered
- relevant metadata (time, inputs, outputs, etc.)
- thresholds / expectations that failed
- drift detection tests that were conducted
- data from reference and test windows
- [log](logging.md){:target="_blank"} records from the relevant window of time

```bash
# Sample alerting ticket
{
    "triggered_alerts": ["text_length_drift"],
    "threshold": 0.05,
    "measurement": "KSDrift",
    "distance": 0.86,
    "p_val": 0.03,
    "reference": [],
    "target": [],
    "logs": ...
}
```

With these pieces of information, we can work backwards from the alert towards identifying the root cause of the issue. **Root cause analysis (RCA)** is an important first step when it comes to monitoring because we want to prevent the same issue from impacting our system again. Often times, many alerts are triggered but they maybe all actually be caused by the same underlying issue. In this case, we'd want to intelligently trigger just one alert that pinpoints the core issue. For example, let's say we receive an alert that our overall user satisfaction ratings are reducing but we also receive another alert that our North American users also have low satisfaction ratings. Here's the system would automatically assess for drift in user satisfaction ratings across many different slices and aggregations to discover that only users in a specific area are experiencing the issue but because it's a popular user base, it ends up triggering all aggregate downstream alerts as well!

### Act

There are many different ways we can act to drift based on the situation. An initial impulse may be to retrain our model on the new data but it may not always solve the underlying issue.

- ensure all data expectations have passed.
- confirm no data schema changes.
- retrain the model on the new shifted dataset.
- move the reference window to more recent data or give it more weight.
- determine if outliers are potentially valid data points.

## Production

Since detecting drift and outliers can involve compute intensive operations, we need a solution that can execute serverless workloads on top of our event data streams (ex. [Kafka](https://kafka.apache.org/){:target="_blank"}). Typically these solutions will ingest payloads (ex. model's inputs and outputs) and can trigger monitoring workloads. This allows us to segregate the resources for monitoring from our actual ML application and scale them as needed.

<div class="ai-center-all">
    <img width="600" src="/static/images/mlops/monitoring/serverless.png" alt="serverless production monitoring">
</div>

When it actually comes to implementing a monitoring system, we have several options, ranging from fully managed to from-scratch. Several popular managed solutions are [Arize](https://arize.com/){:target="_blank"}, [Arthur](https://www.arthur.ai/){:target="_blank"}, [Fiddler](https://www.fiddler.ai/ml-monitoring){:target="_blank"}, [Gantry](https://gantry.io/){:target="_blank"}, [Mona](https://www.monalabs.io/){:target="_blank"}, [WhyLabs](https://whylabs.ai/){:target="_blank"}, etc., all of which allow us to create custom monitoring views, trigger alerts, etc. There are even several great open-source solutions such as [EvidentlyAI](https://evidentlyai.com/){:target="_blank"}, [TorchDrift](https://torchdrift.org/){:target="_blank"}, [WhyLogs](https://whylogs.readthedocs.io/en/latest/){:target="_blank"}, etc.

We'll often notice that monitoring solutions are offered as part of the larger deployment option such as [Sagemaker](https://docs.aws.amazon.com/sagemaker/latest/dg/model-monitor.html){:target="_blank"}, [TensorFlow Extended (TFX)](https://www.tensorflow.org/tfx){:target="_blank"}, [TorchServe](https://pytorch.org/serve/){:target="_blank"}, etc. And if we're already working with Kubernetes, we could use [KNative](https://knative.dev/){:target="_blank"} or [Kubeless](https://kubeless.io/){:target="_blank"} for serverless workload management. But we could also use a higher level framework such as [KFServing](https://www.kubeflow.org/docs/components/kfserving/){:target="_blank"} or [Seldon core](https://docs.seldon.io/projects/seldon-core/en/v0.4.0/#){:target="_blank"} that natively use a serverless framework like KNative.

## References
- [An overview of unsupervised drift detection methods](https://onlinelibrary.wiley.com/doi/full/10.1002/widm.1381){:target="_blank"}
- [Failing Loudly: An Empirical Study of Methods for Detecting Dataset Shift](https://arxiv.org/abs/1810.11953){:target="_blank"}
- [Monitoring and explainability of models in production](https://arxiv.org/abs/2007.06299){:target="_blank"}
- [Detecting and Correcting for Label Shift with Black Box Predictors](https://arxiv.org/abs/1802.03916){:target="_blank"}
- [Outlier and anomaly pattern detection on data streams](https://link.springer.com/article/10.1007/s11227-018-2674-1){:target="_blank"}

<!-- Course signup -->
{% include "templates/signup.md" %}

<!-- Citation -->
{% include "templates/cite.md" %}