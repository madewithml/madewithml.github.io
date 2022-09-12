---
title: Made With ML
template: main.html
keywords: mlops, applied ml, machine learning, ml in production, machine learning in production, applied machine learning
---

{% include "styles/page.md" %}

<!-- Hero -->
<div class="row flex-column-reverse flex-md-row">
    <div class="col-md-7" data-aos="fade-right">
        <div class="ai-hero-text">
            <h1 style="margin-bottom: 0rem; color: #000; font-weight: 500;">Made With ML</h1>
            <p style="margin-top: 0rem; margin-bottom: 0rem !important; color: #807e7e;">Applied ML · MLOps · Production</p>
            <p style="font-size: 0.89rem;">Join <b>35K+ developers</b> in learning how to responsibly deliver value with ML.</p>
            <div id="revue-embed">
                <form action="https://www.getrevue.co/profile/madewithml/add_subscriber" method="post" id="revue-form" name="revue-form"  target="_blank">
                    <input class="revue-form-field" placeholder="Your personal email address..." type="email" name="member[email]" id="member_email" style="width: 80%; border: 1px solid #b3b3b3; border-radius: 3px;">
                    <button class="md-button md-button--purple-gradient mr-2 mb-2 mb-md-0 mt-md-2 mt-2" type="submit" style="cursor: pointer !important;">
                        <span class="twemoji mr-1"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill-rule="evenodd" d="M1.75 3A1.75 1.75 0 000 4.75v14c0 .966.784 1.75 1.75 1.75h20.5A1.75 1.75 0 0024 18.75v-14A1.75 1.75 0 0022.25 3H1.75zM1.5 4.75a.25.25 0 01.25-.25h20.5a.25.25 0 01.25.25v.852l-10.36 7a.25.25 0 01-.28 0l-10.36-7V4.75zm0 2.662V18.75c0 .138.112.25.25.25h20.5a.25.25 0 00.25-.25V7.412l-9.52 6.433c-.592.4-1.368.4-1.96 0L1.5 7.412z"></path></svg></span> Subscribe</button>
                        <a href="#lessons"><span class="md-button md-button--grey-secondary mr-2 mb-2 mb-md-0 mt-md-2 px-3 py-1">View lessons</span></a>
                </form>
            </div>
        </div>
    </div>
    <div class="col-md-5 ai-center-all" data-aos="fade-left">
        <div class="mb-md-0 mb-4">
            <img src="/static/images/logos.png" style="width: 12rem;" alt="machine learning logos">
        </div>
    </div>
</div>

<div class="ai-center-all" style="margin-top: 2rem;">
    <div class="row">
        <div class="col-md-4" data-aos="fade-up" data-aos-easing="ease-out-cubic" data-aos-duration="1000" data-aos-delay="0">
            <div class="px-md-3 py-md-3 px-5 py-3 ai-header-card">🏆 &nbsp;Among the <a href="https://github.com/GokuMohandas/Made-With-ML" target="_blank">top ML repositories</a> on GitHub.</div>
        </div>
        <div class="col-md-4 mt-4 mt-md-0" data-aos="fade-up" data-aos-easing="ease-out-cubic" data-aos-duration="1000" data-aos-delay="500">
            <div class="px-md-3 py-md-3 px-5 py-3 ai-header-card">❤️ &nbsp;<a href="https://newsletter.madewithml.com/" target="_blank">35K+ community members</a> and growing.</div>
        </div>
        <div class="col-md-4 mt-4 mt-md-0" data-aos="fade-up" data-aos-easing="ease-out-cubic" data-aos-duration="1000" data-aos-delay="1000">
            <div class="px-md-3 py-md-3 px-5 py-3 ai-header-card">🛠️  &nbsp;<a href="https://youtu.be/CjU_6OaYKpw?t=1009" target="_blank">Highly recommended</a> industry resource.</div>
        </div>
    </div>
</div>

<!-- Course header -->
<hr style="margin-top: 2rem; margin-bottom: 2rem;">
<section data-aos="zoom-in" data-aos-delay="1500" class="p-4" style="background: rgb(245,249,253); background: linear-gradient(180deg, rgba(245,249,253,1) 0%, rgba(255,255,255,1) 100%); border-radius: 10px;">
    <h1 class="ai-center-all mb-0" style="color: rgb(75, 115, 245); font-size: 1rem;">Made With ML</h1>
    <h2 class="ai-center-all mt-0 mb-0" style="font-size: 1.5rem;">MLOps Course</h2>
    <div class="ai-center-all">
        <p class="mt-3" style="font-size: 0.83rem;">A project-based course on MLOps fundamentals with a focus on intuition & application that teaches you how to apply ML in industry. All the lessons below are <b>100% free</b> but we also offer a highly interactive <a href="#features">6-week course</a> where you'll learn how to master MLOps.</p>
    </div>
    <div class="ai-center-all">
        <a href="#apply" class="md-button md-button--green-gradient mb-2 mb-md-0 mt-md-0 mt-1" style="cursor: pointer !important;"><span class="twemoji mr-1"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24"><path fill-rule="evenodd" d="M20.322.75a10.75 10.75 0 00-7.373 2.926l-1.304 1.23A23.743 23.743 0 0010.103 6.5H5.066a1.75 1.75 0 00-1.5.85l-2.71 4.514a.75.75 0 00.49 1.12l4.571.963c.039.049.082.096.129.14L8.04 15.96l1.872 1.994c.044.047.091.09.14.129l.963 4.572a.75.75 0 001.12.488l4.514-2.709a1.75 1.75 0 00.85-1.5v-5.038a23.741 23.741 0 001.596-1.542l1.228-1.304a10.75 10.75 0 002.925-7.374V2.499A1.75 1.75 0 0021.498.75h-1.177zM16 15.112c-.333.248-.672.487-1.018.718l-3.393 2.262.678 3.223 3.612-2.167a.25.25 0 00.121-.214v-3.822zm-10.092-2.7L8.17 9.017c.23-.346.47-.685.717-1.017H5.066a.25.25 0 00-.214.121l-2.167 3.612 3.223.679zm8.07-7.644a9.25 9.25 0 016.344-2.518h1.177a.25.25 0 01.25.25v1.176a9.25 9.25 0 01-2.517 6.346l-1.228 1.303a22.248 22.248 0 01-3.854 3.257l-3.288 2.192-1.743-1.858a.764.764 0 00-.034-.034l-1.859-1.744 2.193-3.29a22.248 22.248 0 013.255-3.851l1.304-1.23zM17.5 8a1.5 1.5 0 11-3 0 1.5 1.5 0 013 0zm-11 13c.9-.9.9-2.6 0-3.5-.9-.9-2.6-.9-3.5 0-1.209 1.209-1.445 3.901-1.49 4.743a.232.232 0 00.247.247c.842-.045 3.534-.281 4.743-1.49z"></path></svg></span> Apply</a>
    </div>
    <div class="ai-center-all mt-2">
        <small><b>Upcoming cohort:</b></small>
    </div>
    <div class="ai-center-all">
        <small>Sept 18th, 2021</small>
    </div>
</section>

<!-- Testimonials -->
<hr style="margin-top: 1rem; margin-bottom: 2rem;">
<div id="testimonials" class="carousel slide" data-ride="carousel">
    <div class="carousel-inner">
        <div class="carousel-item active px-4">
            <div class="row">
                <div class="col-md-6 mb-2">
                    <div class="card ai-testimonial-card mt-2">
                        <div class="card-body">
                            <div>
                                <div class="row">
                                    <div class="col-3 col-sm-2 pr-0 ai-center-all">
                                        <img class="ai-testimonial-profile-image" src="/static/images/testimonials/ritchie_ng.jpeg" alt="profile">
                                    </div>
                                    <div class="col-9 col-md-10 pl-2">
                                        <div>
                                            <b>Ritchie Ng</b>
                                            <a href="https://youtu.be/CjU_6OaYKpw?t=1009" target="_blank">
                                                <span class="twemoji youtube ml-1">
                                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 576 512"><path d="M549.655 124.083c-6.281-23.65-24.787-42.276-48.284-48.597C458.781 64 288 64 288 64S117.22 64 74.629 75.486c-23.497 6.322-42.003 24.947-48.284 48.597-11.412 42.867-11.412 132.305-11.412 132.305s0 89.438 11.412 132.305c6.281 23.65 24.787 41.5 48.284 47.821C117.22 448 288 448 288 448s170.78 0 213.371-11.486c23.497-6.321 42.003-24.171 48.284-47.821 11.412-42.867 11.412-132.305 11.412-132.305s0-89.438-11.412-132.305zm-317.51 213.508V175.185l142.739 81.205-142.739 81.201z"></path></svg>
                                                </span>
                                            </a>
                                        </div>
                                <span class="ai-testimonial-org">PyTorch Keynote Speaker</span>
                                    </div>
                                </div>
                            </div>
                            <p class="card-subtitle">"For production ML, I cannot possibly think of a better resource out there ... this resource is the gold standard."</p>
                        </div>
                    </div>
                </div>
                <div class="col-md-6 mb-2">
                    <div class="card ai-testimonial-card mt-2">
                        <div class="card-body">
                            <div>
                                <div class="row">
                                    <div class="col-3 col-sm-2 pr-0 ai-center-all">
                                        <img class="ai-testimonial-profile-image" src="/static/images/testimonials/daniel_bourke.jpeg" alt="profile">
                                    </div>
                                    <div class="col-9 col-md-10 pl-2">
                                        <div>
                                            <b>Daniel Bourke</b>
                                            <a href="https://twitter.com/mrdbourke/status/1409737996455141388" target="_blank">
                                                <span class="twemoji twitter ml-1">
                                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M459.37 151.716c.325 4.548.325 9.097.325 13.645 0 138.72-105.583 298.558-298.558 298.558-59.452 0-114.68-17.219-161.137-47.106 8.447.974 16.568 1.299 25.34 1.299 49.055 0 94.213-16.568 130.274-44.832-46.132-.975-84.792-31.188-98.112-72.772 6.498.974 12.995 1.624 19.818 1.624 9.421 0 18.843-1.3 27.614-3.573-48.081-9.747-84.143-51.98-84.143-102.985v-1.299c13.969 7.797 30.214 12.67 47.431 13.319-28.264-18.843-46.781-51.005-46.781-87.391 0-19.492 5.197-37.36 14.294-52.954 51.655 63.675 129.3 105.258 216.365 109.807-1.624-7.797-2.599-15.918-2.599-24.04 0-57.828 46.782-104.934 104.934-104.934 30.213 0 57.502 12.67 76.67 33.137 23.715-4.548 46.456-13.32 66.599-25.34-7.798 24.366-24.366 44.833-46.132 57.827 21.117-2.273 41.584-8.122 60.426-16.243-14.292 20.791-32.161 39.308-52.628 54.253z"></path></svg>
                                                </span>
                                            </a>
                                        </div>
                                <span class="ai-testimonial-org">Mrdbourke Studios</span>
                                    </div>
                                </div>
                            </div>
                            <p class="card-subtitle">"Built some machine learning models? Want to take them to the next level? I do. And I’m using <a href="https://twitter.com/MadeWithML" target="_blank">@madewithml</a> to learn how. Outstanding MLOps lessons!"</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="carousel-item px-4">
            <div class="row">
                <div class="col-md-6 mb-2">
                    <div class="card ai-testimonial-card mt-2">
                        <div class="card-body">
                            <div>
                                <div class="row">
                                    <div class="col-3 col-sm-2 pr-0 ai-center-all">
                                        <img class="ai-testimonial-profile-image" src="/static/images/testimonials/ask_katnoria.jpeg" alt="profile">
                                    </div>
                                    <div class="col-9 col-md-10 pl-2">
                                        <div>
                                            <b>Ash Katnoria</b>
                                            <a href="https://twitter.com/katnoria1/status/1409782295968448514" target="_blank">
                                                <span class="twemoji twitter ml-1">
                                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M459.37 151.716c.325 4.548.325 9.097.325 13.645 0 138.72-105.583 298.558-298.558 298.558-59.452 0-114.68-17.219-161.137-47.106 8.447.974 16.568 1.299 25.34 1.299 49.055 0 94.213-16.568 130.274-44.832-46.132-.975-84.792-31.188-98.112-72.772 6.498.974 12.995 1.624 19.818 1.624 9.421 0 18.843-1.3 27.614-3.573-48.081-9.747-84.143-51.98-84.143-102.985v-1.299c13.969 7.797 30.214 12.67 47.431 13.319-28.264-18.843-46.781-51.005-46.781-87.391 0-19.492 5.197-37.36 14.294-52.954 51.655 63.675 129.3 105.258 216.365 109.807-1.624-7.797-2.599-15.918-2.599-24.04 0-57.828 46.782-104.934 104.934-104.934 30.213 0 57.502 12.67 76.67 33.137 23.715-4.548 46.456-13.32 66.599-25.34-7.798 24.366-24.366 44.833-46.132 57.827 21.117-2.273 41.584-8.122 60.426-16.243-14.292 20.791-32.161 39.308-52.628 54.253z"></path></svg>
                                                </span>
                                            </a>
                                        </div>
                                <span class="ai-testimonial-org">Katnoria</span>
                                    </div>
                                </div>
                            </div>
                            <p class="card-subtitle">"Easily one of the most comprehensive series. I am amazed by how much ground it covers starting with data collection,  all the way up to k8s + model monitoring."</p>
                        </div>
                    </div>
                </div>
                <div class="col-md-6 mb-2">
                    <div class="card ai-testimonial-card mt-2">
                        <div class="card-body">
                            <div>
                                <div class="row">
                                    <div class="col-3 col-sm-2 pr-0 ai-center-all">
                                        <img class="ai-testimonial-profile-image" src="/static/images/testimonials/arghyadeep_das.jpeg" alt="profile">
                                    </div>
                                    <div class="col-9 col-md-10 pl-2">
                                        <div>
                                            <b>Arghyadeep Das</b>
                                            <a href="https://www.linkedin.com/posts/arghyadeep-das_made-with-ml-activity-6815267985788342272-yJ8e" target="_blank">
                                                <span class="twemoji linkedin ml-1">
                                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M416 32H31.9C14.3 32 0 46.5 0 64.3v383.4C0 465.5 14.3 480 31.9 480H416c17.6 0 32-14.5 32-32.3V64.3c0-17.8-14.4-32.3-32-32.3zM135.4 416H69V202.2h66.5V416zm-33.2-243c-21.3 0-38.5-17.3-38.5-38.5S80.9 96 102.2 96c21.2 0 38.5 17.3 38.5 38.5 0 21.3-17.2 38.5-38.5 38.5zm282.1 243h-66.4V312c0-24.8-.5-56.7-34.5-56.7-34.6 0-39.9 27-39.9 54.9V416h-66.4V202.2h63.7v29.2h.9c8.9-16.8 30.6-34.5 62.9-34.5 67.2 0 79.7 44.3 79.7 101.9V416z"></path></svg>
                                                </span>
                                            </a>
                                        </div>
                                <span class="ai-testimonial-org">Barclays</span>
                                    </div>
                                </div>
                            </div>
                            <p class="card-subtitle">"Ideal place for grad students and software engineers to learn about practical ML. Couldn't have a better resource collection than this!"</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="carousel-item px-4">
            <div class="row">
                <div class="col-md-6 mb-2">
                    <div class="card ai-testimonial-card mt-2">
                        <div class="card-body">
                            <div>
                                <div class="row">
                                    <div class="col-3 col-sm-2 pr-0 ai-center-all">
                                        <img class="ai-testimonial-profile-image" src="/static/images/testimonials/peter_ku.jpeg" alt="profile">
                                    </div>
                                    <div class="col-9 col-md-10 pl-2">
                                        <div>
                                            <b>Peter Ku</b>
                                            <a href="https://twitter.com/peterkuai/status/1409503953172140034" target="_blank">
                                                <span class="twemoji twitter ml-1">
                                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M459.37 151.716c.325 4.548.325 9.097.325 13.645 0 138.72-105.583 298.558-298.558 298.558-59.452 0-114.68-17.219-161.137-47.106 8.447.974 16.568 1.299 25.34 1.299 49.055 0 94.213-16.568 130.274-44.832-46.132-.975-84.792-31.188-98.112-72.772 6.498.974 12.995 1.624 19.818 1.624 9.421 0 18.843-1.3 27.614-3.573-48.081-9.747-84.143-51.98-84.143-102.985v-1.299c13.969 7.797 30.214 12.67 47.431 13.319-28.264-18.843-46.781-51.005-46.781-87.391 0-19.492 5.197-37.36 14.294-52.954 51.655 63.675 129.3 105.258 216.365 109.807-1.624-7.797-2.599-15.918-2.599-24.04 0-57.828 46.782-104.934 104.934-104.934 30.213 0 57.502 12.67 76.67 33.137 23.715-4.548 46.456-13.32 66.599-25.34-7.798 24.366-24.366 44.833-46.132 57.827 21.117-2.273 41.584-8.122 60.426-16.243-14.292 20.791-32.161 39.308-52.628 54.253z"></path></svg>
                                                </span>
                                            </a>
                                        </div>
                                <span class="ai-testimonial-org">Amazon Alexa</span>
                                    </div>
                                </div>
                            </div>
                            <p class="card-subtitle">"Covers the broad MLOps landscape in great detail, extremely high quality tested code and not just talking about concepts on a high level, open-sourced."</p>
                        </div>
                    </div>
                </div>
                <div class="col-md-6 mb-2">
                    <div class="card ai-testimonial-card mt-2">
                        <div class="card-body">
                            <div>
                                <div class="row">
                                    <div class="col-3 col-sm-2 pr-0 ai-center-all">
                                        <img class="ai-testimonial-profile-image" src="/static/images/testimonials/abinaya_mahendiran.jpeg" alt="profile">
                                    </div>
                                    <div class="col-9 col-md-10 pl-2">
                                        <div>
                                            <b>Abinaya Mahendiran</b>
                                            <a href="https://www.linkedin.com/posts/abinayamahendiran_made-with-ml-activity-6815497954481328128-5ENz" target="_blank">
                                                <span class="twemoji linkedin ml-1">
                                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M416 32H31.9C14.3 32 0 46.5 0 64.3v383.4C0 465.5 14.3 480 31.9 480H416c17.6 0 32-14.5 32-32.3V64.3c0-17.8-14.4-32.3-32-32.3zM135.4 416H69V202.2h66.5V416zm-33.2-243c-21.3 0-38.5-17.3-38.5-38.5S80.9 96 102.2 96c21.2 0 38.5 17.3 38.5 38.5 0 21.3-17.2 38.5-38.5 38.5zm282.1 243h-66.4V312c0-24.8-.5-56.7-34.5-56.7-34.6 0-39.9 27-39.9 54.9V416h-66.4V202.2h63.7v29.2h.9c8.9-16.8 30.6-34.5 62.9-34.5 67.2 0 79.7 44.3 79.7 101.9V416z"></path></svg>
                                                </span>
                                            </a>
                                        </div>
                                <span class="ai-testimonial-org">Mphasis</span>
                                    </div>
                                </div>
                            </div>
                            <p class="card-subtitle">"For anyone interested in seeing MLOps in action, this is the best practical resource out there! Thank you for this wonderful course. Highly recommended!"</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="carousel-item px-4">
            <div class="row">
                <div class="col-md-6 mb-2">
                    <div class="card ai-testimonial-card mt-2">
                        <div class="card-body">
                            <div>
                                <div class="row">
                                    <div class="col-3 col-sm-2 pr-0 ai-center-all">
                                        <img class="ai-testimonial-profile-image" src="/static/images/testimonials/jeremy_jordan.jpeg" alt="profile">
                                    </div>
                                    <div class="col-9 col-md-10 pl-2">
                                        <div>
                                            <b>Jeremy Jordan</b>
                                            <a href="https://twitter.com/jeremyjordan/status/1316052661133815809" target="_blank">
                                                <span class="twemoji twitter ml-1">
                                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M459.37 151.716c.325 4.548.325 9.097.325 13.645 0 138.72-105.583 298.558-298.558 298.558-59.452 0-114.68-17.219-161.137-47.106 8.447.974 16.568 1.299 25.34 1.299 49.055 0 94.213-16.568 130.274-44.832-46.132-.975-84.792-31.188-98.112-72.772 6.498.974 12.995 1.624 19.818 1.624 9.421 0 18.843-1.3 27.614-3.573-48.081-9.747-84.143-51.98-84.143-102.985v-1.299c13.969 7.797 30.214 12.67 47.431 13.319-28.264-18.843-46.781-51.005-46.781-87.391 0-19.492 5.197-37.36 14.294-52.954 51.655 63.675 129.3 105.258 216.365 109.807-1.624-7.797-2.599-15.918-2.599-24.04 0-57.828 46.782-104.934 104.934-104.934 30.213 0 57.502 12.67 76.67 33.137 23.715-4.548 46.456-13.32 66.599-25.34-7.798 24.366-24.366 44.833-46.132 57.827 21.117-2.273 41.584-8.122 60.426-16.243-14.292 20.791-32.161 39.308-52.628 54.253z"></path></svg>
                                                </span>
                                            </a>
                                        </div>
                                <span class="ai-testimonial-org">Duo Security</span>
                                    </div>
                                </div>
                            </div>
                            <p class="card-subtitle">"This will be a great journey for those interested in deploying machine learning models which lead to a positive impact on the product."</p>
                        </div>
                    </div>
                </div>
                <div class="col-md-6 mb-2">
                    <div class="card ai-testimonial-card mt-2">
                        <div class="card-body">
                            <div>
                                <div class="row">
                                    <div class="col-3 col-sm-2 pr-0 ai-center-all">
                                        <img class="ai-testimonial-profile-image" src="/static/images/testimonials/karthik_bhaskar.jpeg" alt="profile">
                                    </div>
                                    <div class="col-9 col-md-10 pl-2">
                                        <div>
                                            <b>Karthik Bhaskar</b>
                                            <a href="https://twitter.com/kbhaskar_95/status/1401879875955265543" target="_blank">
                                                <span class="twemoji twitter ml-1">
                                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M459.37 151.716c.325 4.548.325 9.097.325 13.645 0 138.72-105.583 298.558-298.558 298.558-59.452 0-114.68-17.219-161.137-47.106 8.447.974 16.568 1.299 25.34 1.299 49.055 0 94.213-16.568 130.274-44.832-46.132-.975-84.792-31.188-98.112-72.772 6.498.974 12.995 1.624 19.818 1.624 9.421 0 18.843-1.3 27.614-3.573-48.081-9.747-84.143-51.98-84.143-102.985v-1.299c13.969 7.797 30.214 12.67 47.431 13.319-28.264-18.843-46.781-51.005-46.781-87.391 0-19.492 5.197-37.36 14.294-52.954 51.655 63.675 129.3 105.258 216.365 109.807-1.624-7.797-2.599-15.918-2.599-24.04 0-57.828 46.782-104.934 104.934-104.934 30.213 0 57.502 12.67 76.67 33.137 23.715-4.548 46.456-13.32 66.599-25.34-7.798 24.366-24.366 44.833-46.132 57.827 21.117-2.273 41.584-8.122 60.426-16.243-14.292 20.791-32.161 39.308-52.628 54.253z"></path></svg>
                                                </span>
                                            </a>
                                        </div>
                                <span class="ai-testimonial-org">Vector Institute</span>
                                    </div>
                                </div>
                            </div>
                            <p class="card-subtitle">"Best available practical course on MLOps. Thanks <a href="https://twitter.com/GokuMohandas" target="_blank">@GokuMohandas</a> for creating such awesome content and sharing it!"</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="carousel-item px-4">
            <div class="row">
                <div class="col-md-6 mb-2">
                    <div class="card ai-testimonial-card mt-2">
                        <div class="card-body">
                            <div>
                                <div class="row">
                                    <div class="col-3 col-sm-2 pr-0 ai-center-all">
                                        <img class="ai-testimonial-profile-image" src="/static/images/testimonials/dmitry_petrov.png" alt="profile">
                                    </div>
                                    <div class="col-9 col-md-10 pl-2">
                                        <div>
                                            <b>Dmitry Petrov</b>
                                            <a href="https://twitter.com/FullStackML/status/1316077799652749313" target="_blank">
                                                <span class="twemoji twitter ml-1">
                                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M459.37 151.716c.325 4.548.325 9.097.325 13.645 0 138.72-105.583 298.558-298.558 298.558-59.452 0-114.68-17.219-161.137-47.106 8.447.974 16.568 1.299 25.34 1.299 49.055 0 94.213-16.568 130.274-44.832-46.132-.975-84.792-31.188-98.112-72.772 6.498.974 12.995 1.624 19.818 1.624 9.421 0 18.843-1.3 27.614-3.573-48.081-9.747-84.143-51.98-84.143-102.985v-1.299c13.969 7.797 30.214 12.67 47.431 13.319-28.264-18.843-46.781-51.005-46.781-87.391 0-19.492 5.197-37.36 14.294-52.954 51.655 63.675 129.3 105.258 216.365 109.807-1.624-7.797-2.599-15.918-2.599-24.04 0-57.828 46.782-104.934 104.934-104.934 30.213 0 57.502 12.67 76.67 33.137 23.715-4.548 46.456-13.32 66.599-25.34-7.798 24.366-24.366 44.833-46.132 57.827 21.117-2.273 41.584-8.122 60.426-16.243-14.292 20.791-32.161 39.308-52.628 54.253z"></path></svg>
                                                </span>
                                            </a>
                                        </div>
                                <span class="ai-testimonial-org">DVC</span>
                                    </div>
                                </div>
                            </div>
                            <p class="card-subtitle">"This is not a usual ML class, it covers productionalization part of ML projects - the most important part from a business point of view."</p>
                        </div>
                    </div>
                </div>
                <div class="col-md-6 mb-2">
                    <div class="card ai-testimonial-card mt-2">
                        <div class="card-body">
                            <div>
                                <div class="row">
                                    <div class="col-3 col-sm-2 pr-0 ai-center-all">
                                        <img class="ai-testimonial-profile-image" src="/static/images/testimonials/lawrence_okegbemi.jpeg" alt="profile">
                                    </div>
                                    <div class="col-9 col-md-10 pl-2">
                                        <div>
                                            <b>Lawrence Okegbemi</b>
                                            <a href="https://www.linkedin.com/feed/update/urn:li:activity:6815254111030792192?commentUrn=urn%3Ali%3Acomment%3A%28activity%3A6815254111030792192%2C6815256765584678912%29" target="_blank">
                                                <span class="twemoji linkedin ml-1">
                                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 448 512"><path d="M416 32H31.9C14.3 32 0 46.5 0 64.3v383.4C0 465.5 14.3 480 31.9 480H416c17.6 0 32-14.5 32-32.3V64.3c0-17.8-14.4-32.3-32-32.3zM135.4 416H69V202.2h66.5V416zm-33.2-243c-21.3 0-38.5-17.3-38.5-38.5S80.9 96 102.2 96c21.2 0 38.5 17.3 38.5 38.5 0 21.3-17.2 38.5-38.5 38.5zm282.1 243h-66.4V312c0-24.8-.5-56.7-34.5-56.7-34.6 0-39.9 27-39.9 54.9V416h-66.4V202.2h63.7v29.2h.9c8.9-16.8 30.6-34.5 62.9-34.5 67.2 0 79.7 44.3 79.7 101.9V416z"></path></svg>
                                                </span>
                                            </a>
                                        </div>
                                <span class="ai-testimonial-org">Enterscale</span>
                                    </div>
                                </div>
                            </div>
                            <p class="card-subtitle">"Following all through, it's really amazing to see how you demonstrated best practices in building an ML driven application."</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        <div class="carousel-item px-4">
            <div class="row">
                <div class="col-md-6 mb-2">
                    <div class="card ai-testimonial-card mt-2">
                        <div class="card-body">
                            <div>
                                <div class="row">
                                    <div class="col-3 col-sm-2 pr-0 ai-center-all">
                                        <img class="ai-testimonial-profile-image" src="/static/images/testimonials/laxman_tomar.jpeg" alt="profile">
                                    </div>
                                    <div class="col-9 col-md-10 pl-2">
                                        <div>
                                            <b>Laxman Tomar</b>
                                            <a href="https://twitter.com/LaxmanSTomar/status/1409522738880860174" target="_blank">
                                                <span class="twemoji twitter ml-1">
                                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M459.37 151.716c.325 4.548.325 9.097.325 13.645 0 138.72-105.583 298.558-298.558 298.558-59.452 0-114.68-17.219-161.137-47.106 8.447.974 16.568 1.299 25.34 1.299 49.055 0 94.213-16.568 130.274-44.832-46.132-.975-84.792-31.188-98.112-72.772 6.498.974 12.995 1.624 19.818 1.624 9.421 0 18.843-1.3 27.614-3.573-48.081-9.747-84.143-51.98-84.143-102.985v-1.299c13.969 7.797 30.214 12.67 47.431 13.319-28.264-18.843-46.781-51.005-46.781-87.391 0-19.492 5.197-37.36 14.294-52.954 51.655 63.675 129.3 105.258 216.365 109.807-1.624-7.797-2.599-15.918-2.599-24.04 0-57.828 46.782-104.934 104.934-104.934 30.213 0 57.502 12.67 76.67 33.137 23.715-4.548 46.456-13.32 66.599-25.34-7.798 24.366-24.366 44.833-46.132 57.827 21.117-2.273 41.584-8.122 60.426-16.243-14.292 20.791-32.161 39.308-52.628 54.253z"></path></svg>
                                                </span>
                                            </a>
                                        </div>
                                <span class="ai-testimonial-org">Robofied</span>
                                    </div>
                                </div>
                            </div>
                            <p class="card-subtitle">"The best MLOps resource that I've come across on the web. Goes over whys, hows, tradeoffs, tools & their alternatives via high-quality explanations and code."</p>
                        </div>
                    </div>
                </div>
                <div class="col-md-6 mb-2">
                    <div class="card ai-testimonial-card mt-2">
                        <div class="card-body">
                            <div>
                                <div class="row">
                                    <div class="col-3 col-sm-2 pr-0 ai-center-all">
                                        <img class="ai-testimonial-profile-image" src="/static/images/testimonials/satyabrata_pal.jpeg" alt="profile">
                                    </div>
                                    <div class="col-9 col-md-10 pl-2">
                                        <div>
                                            <b>Satyabrata Pal</b>
                                            <a href="https://twitter.com/TheCodingProjec/status/1381259115901558784" target="_blank">
                                                <span class="twemoji twitter ml-1">
                                                    <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 512 512"><path d="M459.37 151.716c.325 4.548.325 9.097.325 13.645 0 138.72-105.583 298.558-298.558 298.558-59.452 0-114.68-17.219-161.137-47.106 8.447.974 16.568 1.299 25.34 1.299 49.055 0 94.213-16.568 130.274-44.832-46.132-.975-84.792-31.188-98.112-72.772 6.498.974 12.995 1.624 19.818 1.624 9.421 0 18.843-1.3 27.614-3.573-48.081-9.747-84.143-51.98-84.143-102.985v-1.299c13.969 7.797 30.214 12.67 47.431 13.319-28.264-18.843-46.781-51.005-46.781-87.391 0-19.492 5.197-37.36 14.294-52.954 51.655 63.675 129.3 105.258 216.365 109.807-1.624-7.797-2.599-15.918-2.599-24.04 0-57.828 46.782-104.934 104.934-104.934 30.213 0 57.502 12.67 76.67 33.137 23.715-4.548 46.456-13.32 66.599-25.34-7.798 24.366-24.366 44.833-46.132 57.827 21.117-2.273 41.584-8.122 60.426-16.243-14.292 20.791-32.161 39.308-52.628 54.253z"></path></svg>
                                                </span>
                                            </a>
                                        </div>
                                <span class="ai-testimonial-org">Julia Community</span>
                                    </div>
                                </div>
                            </div>
                            <p class="card-subtitle">"Completely sold out on the clean code and detailed writeup. This is one of the few ML courses which doesn't stop on just training a model but goes beyond that."</p>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
    <a class="carousel-control-prev" style="width: 0%;" href="#testimonials" role="button" data-slide="prev">
        <span style="font-size: 2.5rem; font-weight: 700;">&lsaquo;</span>
    </a>
    <a class="carousel-control-next" style="width: 0%;" href="#testimonials" role="button" data-slide="next">
        <span style="font-size: 2.5rem; font-weight: 700;">&rsaquo;</span>
    </a>
</div>


<hr style="margin-top: 2rem; margin-bottom: 2rem;">
<h2 class="ai-center-all mt-0 mb-2 md-typeset">Who is this course for?</h2>
<p class="ai-center-all" style="font-size: 0.9rem;">Machine learning is not a separate industry, instead, it's a powerful way of thinking about data that's not reserved for any one type of person.</p>

<div class="row ai-features">
    <div class="col-md-6 ai-feature" data-aos="fade-right">
        <div class="ai-feature-header">
            <span class="twemoji mr-1"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path d="M10.3 8.24a.75.75 0 01-.04 1.06L7.352 12l2.908 2.7a.75.75 0 11-1.02 1.1l-3.5-3.25a.75.75 0 010-1.1l3.5-3.25a.75.75 0 011.06.04zm3.44 1.06a.75.75 0 111.02-1.1l3.5 3.25a.75.75 0 010 1.1l-3.5 3.25a.75.75 0 11-1.02-1.1l2.908-2.7-2.908-2.7z"></path><path fill-rule="evenodd" d="M2 3.75C2 2.784 2.784 2 3.75 2h16.5c.966 0 1.75.784 1.75 1.75v16.5A1.75 1.75 0 0120.25 22H3.75A1.75 1.75 0 012 20.25V3.75zm1.75-.25a.25.25 0 00-.25.25v16.5c0 .138.112.25.25.25h16.5a.25.25 0 00.25-.25V3.75a.25.25 0 00-.25-.25H3.75z"></path></svg></span> Software engineers
        </div>
        <div class="ai-feature-text">
            looking to learn ML and become even better software engineers. ML is integrated into increasingly more products so it's important to know how ML systems operate.
        </div>
    </div>
    <div class="col-md-6 ai-feature" data-aos="fade-left">
        <div class="ai-feature-header">
            <span class="twemoji mr-1"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill-rule="evenodd" d="M8.114 2.094a.75.75 0 01.386.656V9h1.252a.75.75 0 110 1.5H5.75a.75.75 0 010-1.5H7V4.103l-.853.533a.75.75 0 01-.795-1.272l2-1.25a.75.75 0 01.762-.02zm4.889 5.66a.75.75 0 01.75-.75h5.232a.75.75 0 01.53 1.28l-2.776 2.777c.55.097 1.057.253 1.492.483.905.477 1.504 1.284 1.504 2.418 0 .966-.471 1.75-1.172 2.27-.687.511-1.587.77-2.521.77-1.367 0-2.274-.528-2.667-.756a.75.75 0 01.755-1.297c.331.193.953.553 1.912.553.673 0 1.243-.188 1.627-.473.37-.275.566-.635.566-1.067 0-.5-.219-.836-.703-1.091-.538-.284-1.375-.443-2.471-.443a.75.75 0 01-.53-1.28l2.643-2.644h-3.421a.75.75 0 01-.75-.75zM7.88 15.215a1.4 1.4 0 00-1.446.83.75.75 0 01-1.37-.61 2.9 2.9 0 012.986-1.71 2.565 2.565 0 011.557.743c.434.446.685 1.058.685 1.778 0 1.641-1.254 2.437-2.12 2.986-.538.341-1.18.694-1.495 1.273H9.75a.75.75 0 010 1.5h-4a.75.75 0 01-.75-.75c0-1.799 1.337-2.63 2.243-3.21 1.032-.659 1.55-1.031 1.55-1.8 0-.355-.116-.584-.26-.732a1.068 1.068 0 00-.652-.298z"></path></svg></span> Data scientists
        </div>
        <div class="ai-feature-text">
            who want to want to go way beyond developing models in a notebook to wrapping them around robust workflows that enable ML systems to improve over time.
        </div>
    </div>
    <div class="col-md-6 ai-feature" data-aos="fade-right">
        <div class="ai-feature-header">
            <span class="twemoji mr-1"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill-rule="evenodd" d="M12.292 2.06a.75.75 0 00-.584 0L.458 6.81a.75.75 0 000 1.38L4.25 9.793v3.803a2.901 2.901 0 00-1.327.757c-.579.58-.923 1.41-.923 2.43v4.5c0 .248.128.486.335.624.06.04.117.073.22.124.124.062.297.138.52.213.448.149 1.09.288 1.925.288s1.477-.14 1.925-.288c.223-.075.396-.15.52-.213a2.11 2.11 0 00.21-.117A.762.762 0 008 21.28v-4.5c0-1.018-.344-1.85-.923-2.428a2.9 2.9 0 00-1.327-.758v-3.17l5.958 2.516a.75.75 0 00.584 0l5.208-2.2v4.003a2.552 2.552 0 01-.079.085 4.057 4.057 0 01-.849.65c-.826.488-2.255 1.021-4.572 1.021-.612 0-1.162-.037-1.654-.1a.75.75 0 00-.192 1.487c.56.072 1.173.113 1.846.113 2.558 0 4.254-.592 5.334-1.23.538-.316.914-.64 1.163-.896a2.84 2.84 0 00.392-.482h.001A.75.75 0 0019 15v-4.892l4.542-1.917a.75.75 0 000-1.382l-11.25-4.75zM5 15c-.377 0-.745.141-1.017.413-.265.265-.483.7-.483 1.368v4.022c.299.105.797.228 1.5.228s1.201-.123 1.5-.228V16.78c0-.669-.218-1.103-.483-1.368A1.431 1.431 0 005 15zm7-3.564L2.678 7.5 12 3.564 21.322 7.5 12 11.436z"></path></svg></span> College graduates
        </div>
        <div class="ai-feature-text">
            looking to learn the practical skills they'll need for the industry and bridge gap between their university curriculum and what industry expects them to know about ML systems.
        </div>
    </div>
    <div class="col-md-6 ai-feature" data-aos="fade-left">
        <div class="ai-feature-header">
            <span class="twemoji mr-1"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill-rule="evenodd" d="M12 2.5c-3.81 0-6.5 2.743-6.5 6.119 0 1.536.632 2.572 1.425 3.56.172.215.347.422.527.635l.096.112c.21.25.427.508.63.774.404.531.783 1.128.995 1.834a.75.75 0 01-1.436.432c-.138-.46-.397-.89-.753-1.357a18.354 18.354 0 00-.582-.714l-.092-.11c-.18-.212-.37-.436-.555-.667C4.87 12.016 4 10.651 4 8.618 4 4.363 7.415 1 12 1s8 3.362 8 7.619c0 2.032-.87 3.397-1.755 4.5-.185.23-.375.454-.555.667l-.092.109c-.21.248-.405.481-.582.714-.356.467-.615.898-.753 1.357a.75.75 0 01-1.437-.432c.213-.706.592-1.303.997-1.834.202-.266.419-.524.63-.774l.095-.112c.18-.213.355-.42.527-.634.793-.99 1.425-2.025 1.425-3.561C18.5 5.243 15.81 2.5 12 2.5zM9.5 21.75a.75.75 0 01.75-.75h3.5a.75.75 0 010 1.5h-3.5a.75.75 0 01-.75-.75zM8.75 18a.75.75 0 000 1.5h6.5a.75.75 0 000-1.5h-6.5z"></path></svg></span> Product managers
        </div>
        <div class="ai-feature-text">
            who want to develop a technical foundation in MLOps so they can effectively communicate with their technical team and help develop and iterate on applications.
        </div>
    </div>
</div>



<hr id="lessons" style="margin-top: 2rem; margin-bottom: 2rem;">

## Foundations
> Learn the foundations of machine learning through intuitive explanations, clean code and visualizations. &rarr; :fontawesome-brands-github:{ .github } [GokuMohandas/Made-With-ML](https://github.com/GokuMohandas/Made-With-ML){:target="_blank"}

{% include "templates/foundations.md" %}

<hr>

## MLOps
> Learn how to combine machine learning with software engineering to build production-grade applications. &rarr; :fontawesome-brands-github:{ .github } [GokuMohandas/Made-With-ML](https://github.com/GokuMohandas/Made-With-ML){:target="_blank"}

{% include "templates/mlops.md" %}

<hr id="features" style="margin-top: 2rem; margin-bottom: 2rem;">

<h2 class="ai-center-all mt-0 mb-2 md-typeset">Wait! All the lessons are 100% free?</h2>

Yes. The lessons above are 100% free and you can learn all the fundamentals of MLOps by going through them. **So what exactly is the paid course for?** It's extremely difficult to learn things on your own without the proper structure and experience, especially complicated topics such as MLOps. So we're offering the exact structure and experience you need to master the MLOps fundamentals in just 6 weeks. <a href="#six-weeks">Yes, 6 weeks is more than enough</a>.

<div class="row ai-features">
    <div class="col-md-6 ai-feature" data-aos="fade-right">
        <div class="ai-feature-header">
            <span class="mr-1">⚡️</span> Live lectures
        </div>
        <div class="ai-feature-text">
            Interactive sessions to deep dive into concepts from a top-down approach using visualizations.
        </div>
    </div>
    <div class="col-md-6 ai-feature" data-aos="fade-left">
        <div class="ai-feature-header">
            <span class="mr-1">💻</span> Coding workshops
        </div>
        <div class="ai-feature-text">
            Applying MLOps concepts by learning how to produce high quality, production-grade code in our project.
        </div>
    </div>
    <div class="col-md-6 ai-feature" data-aos="fade-right">
        <div class="ai-feature-header">
            <span class="mr-1">❓</span> Q&A
        </div>
        <div class="ai-feature-text">
            Opportunities to ask questions and have discussions after every single module before we progress.
        </div>
    </div>
    <div class="col-md-6 ai-feature" data-aos="fade-left">
        <div class="ai-feature-header">
            <span class="mr-1">🧭</span> Navigation series
        </div>
        <div class="ai-feature-text">
            Guiding sessions on how to approach ML research papers, Python libraries and your career.
        </div>
    </div>
    <div class="col-md-6 ai-feature" data-aos="fade-right">
        <div class="ai-feature-header">
            <span class="mr-1">🌎</span> Community
        </div>
        <div class="ai-feature-text">
            Alumni community to ask questions, share your work and get feedback and continue your learning journey in this ever-changing field.
        </div>
    </div>
    <div class="col-md-6 ai-feature" data-aos="fade-left">
        <div class="ai-feature-header">
            <span class="mr-1">🚀</span> Career assistance
        </div>
        <div class="ai-feature-text">
            Resume and portfolio reviews and mock interview practice to ensure you land your dream job (premium plan).
        </div>
    </div>
</div>


<hr style="margin-top: 2rem;" id="deliverables">
<section class="p-4">
<h2 class="ai-center-all mt-0 mb-2 md-typeset">Course deliverables</h2>

We will be applying the concepts we learn each week to iteratively complete two deliverables. One will demonstrate your <b>technical</b> skills while the other will showcase your <b>communication</b> and <b>domain expertise</b> through a written piece.

<div class="row ai-features mt-2">
    <div class="col-md-12 ai-feature" data-aos="fade-right">
        <div class="ai-feature-header">
            <span class="mr-1">💻</span> End-to-end repository
        </div>
        <div class="ai-feature-text">
            It's not enough to just learn about concepts at a high-level, so as we learn each concept, we will be building onto our end-to-end ML project from modeling to CI/CD. We will be learning the concepts from a <i>first principles</i> approach and develop the mental frameworks to be able to adapt to any context (tech stack, platform, tools, etc.).
        </div>
    </div>
    <div class="col-md-12 ai-feature" data-aos="fade-left">
        <div class="ai-feature-header">
            <span class="mr-1">✍️</span> MLOps in "X"
        </div>
        <div class="ai-feature-text">
            <i>Writing is a very important skill</i>, so as we learn each concept every week, we will be writing about how the concept applies to "X", where X is an industry (or even a specific task) that you're passionate about. By the end of the course, you'll have a well written, and reviewed, piece to share with the community that will be the start to establishing yourself as an expert in ML applied to "X".
        </div>
    </div>
</div>

</section>

<hr style="margin-bottom: 2rem;">
<section class="p-4" style="background-color: #f5f9fd;">
<h2 class="ai-center-all mt-0 mb-2 md-typeset"><span class="mr-1">⚡️</span> Your new superpowers <span class="ml-1">⚡️</span></h2>

<p class="ai-center-all" style="font-size: 0.9rem;">With live lectures, coding workshops, interactive discussions, you'll attain a:</p>
<div class="row">
    <div class="col-md-4 ai-feature" data-aos="fade-up" data-aos-easing="ease-out-cubic" data-aos-duration="1000" data-aos-delay="0">
        <span class="twemoji mr-1"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill-rule="evenodd" d="M20.322.75a10.75 10.75 0 00-7.373 2.926l-1.304 1.23A23.743 23.743 0 0010.103 6.5H5.066a1.75 1.75 0 00-1.5.85l-2.71 4.514a.75.75 0 00.49 1.12l4.571.963c.039.049.082.096.129.14L8.04 15.96l1.872 1.994c.044.047.091.09.14.129l.963 4.572a.75.75 0 001.12.488l4.514-2.709a1.75 1.75 0 00.85-1.5v-5.038a23.741 23.741 0 001.596-1.542l1.228-1.304a10.75 10.75 0 002.925-7.374V2.499A1.75 1.75 0 0021.498.75h-1.177zM16 15.112c-.333.248-.672.487-1.018.718l-3.393 2.262.678 3.223 3.612-2.167a.25.25 0 00.121-.214v-3.822zm-10.092-2.7L8.17 9.017c.23-.346.47-.685.717-1.017H5.066a.25.25 0 00-.214.121l-2.167 3.612 3.223.679zm8.07-7.644a9.25 9.25 0 016.344-2.518h1.177a.25.25 0 01.25.25v1.176a9.25 9.25 0 01-2.517 6.346l-1.228 1.303a22.248 22.248 0 01-3.854 3.257l-3.288 2.192-1.743-1.858a.764.764 0 00-.034-.034l-1.859-1.744 2.193-3.29a22.248 22.248 0 013.255-3.851l1.304-1.23zM17.5 8a1.5 1.5 0 11-3 0 1.5 1.5 0 013 0zm-11 13c.9-.9.9-2.6 0-3.5-.9-.9-2.6-.9-3.5 0-1.209 1.209-1.445 3.901-1.49 4.743a.232.232 0 00.247.247c.842-.045 3.534-.281 4.743-1.49z"></path></svg></span> <b>Foundational ML expertise</b> to <code class="highlight"><span class="nx">architect</span></code> an ML system using best practices, <code class="highlight"><span class="nx">articulate</span></code> your knowledge to others and continuously <code class="highlight"><span class="nx">adapt</span></code> to this evolving space.
    </div>
    <div class="col-md-4 ai-feature" data-aos="fade-up" data-aos-easing="ease-out-cubic" data-aos-duration="1000" data-aos-delay="500">
        <span class="twemoji mr-1"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path d="M10.3 8.24a.75.75 0 01-.04 1.06L7.352 12l2.908 2.7a.75.75 0 11-1.02 1.1l-3.5-3.25a.75.75 0 010-1.1l3.5-3.25a.75.75 0 011.06.04zm3.44 1.06a.75.75 0 111.02-1.1l3.5 3.25a.75.75 0 010 1.1l-3.5 3.25a.75.75 0 11-1.02-1.1l2.908-2.7-2.908-2.7z"></path><path fill-rule="evenodd" d="M2 3.75C2 2.784 2.784 2 3.75 2h16.5c.966 0 1.75.784 1.75 1.75v16.5A1.75 1.75 0 0120.25 22H3.75A1.75 1.75 0 012 20.25V3.75zm1.75-.25a.25.25 0 00-.25.25v16.5c0 .138.112.25.25.25h16.5a.25.25 0 00.25-.25V3.75a.25.25 0 00-.25-.25H3.75z"></path></svg></span> <b>Ability to compose high quality code</b> to create robust ML systems that <code class="highlight"><span class="nx">you</span></code>, <code class="highlight"><span class="nx">your future self</span></code> and <code class="highlight"><span class="nx">fellow developers</span></code> will come to greatly value as you iterate and develop.
    </div>
    <div class="col-md-4 ai-feature" data-aos="fade-up" data-aos-easing="ease-out-cubic" data-aos-duration="1000" data-aos-delay="1000">
        <span class="twemoji mr-1"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill-rule="evenodd" d="M12 1C5.925 1 1 5.925 1 12s4.925 11 11 11 11-4.925 11-11S18.075 1 12 1zM2.513 11.5h4.745c.1-3.037 1.1-5.49 2.093-7.204.39-.672.78-1.233 1.119-1.673C6.11 3.329 2.746 7 2.513 11.5zm4.77 1.5H2.552a9.505 9.505 0 007.918 8.377 15.698 15.698 0 01-1.119-1.673C8.413 18.085 7.47 15.807 7.283 13zm1.504 0h6.426c-.183 2.48-1.02 4.5-1.862 5.951-.476.82-.95 1.455-1.304 1.88L12 20.89l-.047-.057a13.888 13.888 0 01-1.304-1.88C9.807 17.5 8.969 15.478 8.787 13zm6.454-1.5H8.759c.1-2.708.992-4.904 1.89-6.451.476-.82.95-1.455 1.304-1.88L12 3.11l.047.057c.353.426.828 1.06 1.304 1.88.898 1.548 1.79 3.744 1.89 6.452zm1.476 1.5c-.186 2.807-1.13 5.085-2.068 6.704-.39.672-.78 1.233-1.118 1.673A9.505 9.505 0 0021.447 13h-4.731zm4.77-1.5h-4.745c-.1-3.037-1.1-5.49-2.093-7.204-.39-.672-.78-1.233-1.119-1.673 4.36.706 7.724 4.377 7.957 8.877z"></path></svg></span> <b>Community to continue the journey</b> and <code class="highlight"><span class="nx">grow</span></code> via discussions on new tools and best/bespoke practices, <code class="highlight"><span class="nx">collaborate</span></code> on projects and <code class="highlight"><span class="nx">share</span></code> your progress regularly.
    </div>
</div>
</section>

<!-- Instructor -->
{% include "templates/instructor.md" %}


<section id="schedule" class="p-4" style="background-color: #f5f9fd;">
<h2 class="ai-center-all mt-0 mb-2 md-typeset"><span class="mr-2">📅</span> Schedule</h2>

<p>This course runs from Saturday, September 18th 2021 to Saturday, October 23th 2021. However, the fundamental skills you develop and the community will be yours forever.</p>

<div class="row mt-2">
    <div class="col-6" data-aos="fade-right">
        <h4 class="mb-1">Week <span class="ml-1">1️⃣</span></h4>
        <div class="row">
            <div class="col-md-6 mt-md-0 mt-2">
                <div class="mb-2">
                <div>Saturday</div>
                <small><div>Sept 18th, 2021</div></small>
                <small><div>7 am - 10 am PT</div></small>
                </div>
                <div><a data-toggle="collapse" href="#collapseToolkit" aria-expanded="false" aria-controls="collapseToolkit">Toolkit</a></div>
                <div class="collapse multi-collapse" id="collapseToolkit">
                    <ul class="ai-course-list">
                    <li><a href="/courses/foundations/notebooks/">Notebooks</a></li>
                    <li><a href="/courses/foundations/python/">Python</a></li>
                    <li><a href="/courses/foundations/numpy/">NumPy</a></li>
                    <li><a href="/courses/foundations/pandas/">Pandas</a></li>
                    <li><a href="/courses/foundations/pytorch/">PyTorch</a></li>
                    </ul>
                </div>
                <div><a data-toggle="collapse" href="#collapseMachineLearning" aria-expanded="false" aria-controls="collapseMachineLearning">Machine Learning</a></div>
                <div class="collapse multi-collapse" id="collapseMachineLearning">
                    <ul class="ai-course-list">
                    <li><a href="/courses/foundations/linear-regression/">Linear Regression</a></li>
                    <li><a href="/courses/foundations/logistic-regression/">Logistic Regression</a></li>
                    <li><a href="/courses/foundations/neural-networks/">Neural Networks</a></li>
                    <li><a href="/courses/foundations/data-quality/">Data Quality</a></li>
                    <li><a href="/courses/foundations/utilities/">Utilities</a></li>
                    </ul>
                </div>
            </div>
            <div class="col-md-6 mt-md-0 mt-2">
                <div class="mb-2">
                <div>Sunday</div>
                <small><div>Sept 19th, 2021</div></small>
                <small><div>7 am - 10 am PT</div></small>
                </div>
                <div><a data-toggle="collapse" href="#collapseDeepLearning" aria-expanded="false" aria-controls="collapseDeepLearning">Deep Learning</a></div>
                <div class="collapse multi-collapse" id="collapseDeepLearning">
                    <ul class="ai-course-list">
                    <li><a href="/courses/foundations/convolutional-neural-networks/">CNNs</a></li>
                    <li><a href="/courses/foundations/embeddings/">Embeddings</a></li>
                    <li><a href="/courses/foundations/recurrent-neural-networks/">RNNs</a></li>
                    <li><a href="/courses/foundations/attention/">Attention</a></li>
                    <li><a href="/courses/foundations/transformers/">Transformers</a></li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
    <div class="col-6" data-aos="fade-left">
        <h4 class="mb-1">Week <span class="ml-1">2️⃣</span></h4>
        <div class="row">
            <div class="col-md-6 mt-md-0 mt-2">
                <div class="mb-2">
                <div>Saturday</div>
                <small><div>Sept 25th, 2021</div></small>
                <small><div>7 am - 10 am PT</div></small>
                </div>
                <div><a data-toggle="collapse" href="#collapseProduct" aria-expanded="false" aria-controls="collapseProduct">Product</a></div>
                <div class="collapse multi-collapse" id="collapseProduct">
                    <ul class="ai-course-list">
                    <li><a href="/courses/mlops/product/">Product</a></li>
                    <li><a href="/courses/mlops/product#system-design">System design</a></li>
                    <li><a href="/courses/mlops/product#project">Project</a></li>
                    </ul>
                </div>
                <div><a data-toggle="collapse" href="#collapseData" aria-expanded="false" aria-controls="collapseData">Data</a></div>
                <div class="collapse multi-collapse" id="collapseData">
                    <ul class="ai-course-list">
                    <li><a href="/courses/mlops/exploratory-data-analysis/">Exploration</a></li>
                    <li><a href="/courses/mlops/labeling/">Labeling</a></li>
                    <li><a href="/courses/mlops/preprocessing/">Preprocessing</a></li>
                    <li><a href="/courses/mlops/splitting/">Splitting</a></li>
                    <li><a href="/courses/mlops/augmentation/">Augmentation</a></li>
                    </ul>
                </div>
            </div>
            <div class="col-md-6 mt-md-0 mt-2">
                <div class="mb-2">
                <div>Sunday</div>
                <small><div>Sept 26th, 2021</div></small>
                <small><div>7 am - 10 am PT</div></small>
                </div>
                <div><a data-toggle="collapse" href="#collapseModeling" aria-expanded="false" aria-controls="collapseModeling">Modeling</a></div>
                <div class="collapse multi-collapse" id="collapseModeling">
                    <ul class="ai-course-list">
                    <li><a href="/courses/mlops/baselines/">Baselines</a></li>
                    <li><a href="/courses/mlops/evaluation/">Evaluation</a></li>
                    <li><a href="/courses/mlops/experiment-tracking/">Experiment tracking</a></li>
                    <li><a href="/courses/mlops/optimization/">Optimization</a></li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</div>

<div class="row mt-2">
    <div class="col-6" data-aos="fade-right">
        <h4 class="mb-1">Week <span class="ml-1">3️⃣</span></h4>
        <div class="row">
            <div class="col-md-6 mt-md-0 mt-2">
                <div class="mb-2">
                <div>Saturday</div>
                <small><div>Oct 2nd, 2021</div></small>
                <small><div>7 am - 10 am PT</div></small>
                </div>
                <div><a data-toggle="collapse" href="#collapseScripting" aria-expanded="false" aria-controls="collapseScripting">Scripting</a></div>
                <div class="collapse multi-collapse" id="collapseScripting">
                    <ul class="ai-course-list">
                    <li><a href="/courses/mlops/organization/">Organization</a></li>
                    <li><a href="/courses/mlops/packaging/">Packaging</a></li>
                    <li><a href="/courses/mlops/logging/">Logging</a></li>
                    <li><a href="/courses/mlops/documentation/">Documentation</a></li>
                    <li><a href="/courses/mlops/styling/">Styling</a></li>
                    <li><a href="/courses/mlops/makefile/">Makefile</a></li>
                    </ul>
                </div>
            </div>
            <div class="col-md-6 mt-md-0 mt-2">
                <div class="mb-2">
                <div>Sunday</div>
                <small><div>Oct 3rd, 2021</div></small>
                <small><div>7 am - 10 am PT</div></small>
                </div>
                <div><a data-toggle="collapse" href="#collapseInterfaces" aria-expanded="false" aria-controls="collapseInterfaces">Interfaces</a></div>
                <div class="collapse multi-collapse" id="collapseInterfaces">
                    <ul class="ai-course-list">
                    <li><a href="/courses/mlops/cli/">Command-line</a></li>
                    <li><a href="/courses/mlops/api/">RESTful API</a></li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
    <div class="col-6" data-aos="fade-left">
        <h4 class="mb-1">Week <span class="ml-1">4️⃣</span></h4>
        <div class="row">
            <div class="col-md-6 mt-md-0 mt-2">
                <div class="mb-2">
                <div>Saturday</div>
                <small><div>Oct 9th, 2021</div></small>
                <small><div>7 am - 10 am PT</div></small>
                </div>
                <div><a data-toggle="collapse" href="#collapseTesting" aria-expanded="false" aria-controls="collapseTesting">Testing</a></div>
                <div class="collapse multi-collapse" id="collapseTesting">
                    <ul class="ai-course-list">
                    <li><a href="/courses/mlops/testing/">Code</a></li>
                    <li><a href="/courses/mlops/testing/#data">Data</a></li>
                    <li><a href="/courses/mlops/testing/#models">Models</a></li>
                    </ul>
                </div>
            </div>
            <div class="col-md-6 mt-md-0 mt-2">
                <div class="mb-2">
                <div>Sunday</div>
                <small><div>Oct 10th, 2021</div></small>
                <small><div>7 am - 10 am PT</div></small>
                </div>
                <div><a data-toggle="collapse" href="#collapseReproducibility" aria-expanded="false" aria-controls="collapseReproducibility">Reproducibility</a></div>
                <div class="collapse multi-collapse" id="collapseReproducibility">
                    <ul class="ai-course-list">
                    <li><a href="/courses/mlops/git/">Git</a></li>
                    <li><a href="/courses/mlops/pre-commit/">Pre-commit</a></li>
                    <li><a href="/courses/mlops/versioning/">Versioning</a></li>
                    <li><a href="/courses/mlops/docker/">Docker</a></li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</div>

<div class="row mt-2">
    <div class="col-6" data-aos="fade-right">
        <h4 class="mb-1">Week <span class="ml-1">5️⃣</span></h4>
        <div class="row">
            <div class="col-md-6 mt-md-0 mt-2">
                <div class="mb-2">
                <div>Saturday</div>
                <small><div>Oct 16th, 2021</div></small>
                <small><div>7 am - 10 am PT</div></small>
                </div>
                <div><a data-toggle="collapse" href="#collapseProductionI" aria-expanded="false" aria-controls="collapseProductionI">Production I</a></div>
                <div class="collapse multi-collapse" id="collapseProductionI">
                    <ul class="ai-course-list">
                    <li><a href="/courses/mlops/dashboard/">Dashboard</a></li>
                    <li><a href="/courses/mlops/cicd/">CI/CD workflows</a></li>
                    <li><a href="/courses/mlops/infrastructure/">Infrastructure</a></li>
                    </ul>
                </div>
            </div>
            <div class="col-md-6 mt-md-0 mt-2">
                <div class="mb-2">
                <div>Sunday</div>
                <small><div>Oct 17th, 2021</div></small>
                <small><div>7 am - 10 am PT</div></small>
                </div>
                <div><a data-toggle="collapse" href="#collapseProductionII" aria-expanded="false" aria-controls="collapseProductionII">Production II</a></div>
                <div class="collapse multi-collapse" id="collapseProductionII">
                    <ul class="ai-course-list">
                    <li><a href="/courses/mlops/monitoring/">Monitoring</a></li>
                    <li><a href="/courses/mlops/feature-store/">Feature store</a></li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
    <div class="col-6" data-aos="fade-left">
        <h4 class="mb-1">Week <span class="ml-1">6️⃣</span></h4>
        <div class="row">
            <div class="col-md-12 mt-md-0 mt-2">
                <div class="mb-2">
                <div>Saturday</div>
                <small><div>Oct 23th, 2021</div></small>
                <small><div>7 am - 10 am PT</div></small>
                </div>
                <div><a data-toggle="collapse" href="#collapseReflection" aria-expanded="false" aria-controls="collapseReflection">Reflection and next steps</a></div>
                <div class="collapse multi-collapse" id="collapseReflection">
                    <ul class="ai-course-list">
                    <li>Product and project management</li>
                    <li>How to continue the learning journey</li>
                    <li>How to continue building personal brand</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
</div>


<div class="row mt-2">
    <div class="col-6" data-aos="fade-right">
        <h4 class="mb-1">Every week</h4>
        <div class="row">
            <div class="col-md-6 mt-md-0 mt-2">
                <div class="mb-2">
                <div>Tuesdays</div>
                <small><div>9 am - 10 am PT</div></small>
                </div>
                <div><a data-toggle="collapse" href="#collapseQA1" aria-expanded="false" aria-controls="collapseQA1">Q&A office hours</a> <small>(optional)</small></div>
                <div class="collapse multi-collapse" id="collapseQA1">
                    <p>Ask questions about anything!</p>
                    <ul class="ai-course-list">
                    <li>Doubts about any concepts</li>
                    <li>Assignment feedback</li>
                    <li>Personal project guidance</li>
                    </ul>
                </div>
            </div>
            <div class="col-md-6 mt-md-0 mt-2">
                <div class="mb-2">
                <div>Thursdays</div>
                <small><div>4 pm - 5 pm PT</div></small>
                </div>
                <div><a data-toggle="collapse" href="#collapseQA2" aria-expanded="false" aria-controls="collapseQA2">Q&A office hours</a> <small>(optional)</small></div>
                <div class="collapse multi-collapse" id="collapseQA2">
                    <p>Ask questions about anything!</p>
                    <ul class="ai-course-list">
                    <li>Doubts about any concepts</li>
                    <li>Assignment feedback</li>
                    <li>Personal project guidance</li>
                    </ul>
                </div>
            </div>
        </div>
    </div>
    <div class="col-6" data-aos="fade-left">
        <h4 class="mb-1">After the course</h4>
        <div><a data-toggle="collapse" href="#collapseCommunity" aria-expanded="false" aria-controls="collapseCommunity">Alumni community</a></div>
        <div class="collapse multi-collapse" id="collapseCommunity">
            <p>Continue your learning journey with the alumni community!</p>
            <ul>
                <li>Work on portfolio projects and get feedback.</li>
                <li>Participate in reading & study groups to stay up-to-date.</li>
                <li>Collaborate to build the next great product that's <i>made with ML</i>.</li>
            </ul>
        </div>
    </div>
</div>

</section>

<hr id="apply" style="margin-top: 3rem; margin-bottom: 2rem;">
<p class="ai-center-all mt-4" style="font-size: 1.1rem;">Learn how to responsibly deliver value with ML.</p>
<div class="ai-center-all">
    <small><b>Upcoming cohort:</b></small>
</div>
<div class="ai-center-all">
    <small>Sept 18th, 2021</small>
</div>

<div class="row mt-4" style="margin-bottom: 2.5rem;">
    <div class="col-md-4 mb-md-0 mb-4" data-aos="flip-left" data-aos-delay="0">
        <div class="card h-100" style="max-width: 18rem;">
            <div class="card-header bg-transparent ai-center-all"><h3 class="mt-0 mb-0">Free</h3></div>
            <div class="card-body">
                <ul class="task-list">
                    <li class="task-list-item"><label class="task-list-control"><input type="checkbox" checked=""><span class="task-list-indicator"></span></label>  &nbsp;Self-paced detailed lesson blog posts</li>
                    <li class="task-list-item"><label class="task-list-control"><input type="checkbox" checked=""><span class="task-list-indicator"></span></label>  &nbsp;Production grade code in every lesson</li>
                    <li class="task-list-item"><label class="task-list-control"><input type="checkbox" checked=""><span class="task-list-indicator"></span></label>  &nbsp;Visualizations to illustrate every concept</li>
                </ul>
            </div>
            <div class="card-footer bg-transparent">
                <div class="ai-center-all">
                    <p class="mt-0 mb-2" style="font-size: 0.9rem;">$0 USD</p>
                </div>
                <div class="ai-center-all">
                    <a href="#foundations" class="md-button md-button--grey-secondary mb-2 mb-md-1 mt-md-0 mt-1" style="cursor: pointer !important;">Get started</a>
                </div>
            </div>
        </div>
    </div>
    <div class="col-md-4 mb-md-0 mb-4" data-aos="flip-left" data-aos-delay="500">
        <div class="card h-100" style="max-width: 18rem;">
            <div class="card-header bg-transparent ai-center-all"><h3 class="mt-0 mb-0">Essential</h3></div>
            <div class="card-body">
                <ul class="task-list">
                    <li class="task-list-item"><label class="task-list-control"><input type="checkbox" checked=""><span class="task-list-indicator"></span></label>  &nbsp;Master MLOps in 6 weeks</li>
                    <li class="task-list-item"><label class="task-list-control"><input type="checkbox" checked=""><span class="task-list-indicator"></span></label>  &nbsp;Live sessions and coding workshops</li>
                    <li class="task-list-item"><label class="task-list-control"><input type="checkbox" checked=""><span class="task-list-indicator"></span></label>  &nbsp;Live Q&A office hours</li>
                    <li class="task-list-item"><label class="task-list-control"><input type="checkbox" checked=""><span class="task-list-indicator"></span></label>  &nbsp;"How to navigate X" series <small>(ML research, Python libraries, career)</small></li>
                    <li class="task-list-item"><label class="task-list-control"><input type="checkbox" checked=""><span class="task-list-indicator"></span></label>  &nbsp;Alumni community</li>
                </ul>
            </div>
            <div class="card-footer bg-transparent">
                <div class="ai-center-all">
                    <p class="mt-0 mb-2" style="font-size: 0.9rem;">$1,250 USD</p>
                </div>
                <div class="ai-center-all">
                    <a href="https://forms.gle/6mHLoMzEPx11ZRsK6" target="_blank" class="md-button md-button--purple-gradient mb-2 mb-md-1 mt-md-0 mt-1" style="cursor: pointer !important;">Apply</a>
                </div>
            </div>
        </div>
    </div>
    <div class="col-md-4 mb-md-0 mb-4" data-aos="flip-left" data-aos-delay="1000">
        <div class="card h-100" style="max-width: 18rem;">
            <div class="card-header bg-transparent ai-center-all"><h3 class="mt-0 mb-0">Premium</h3></div>
            <div class="card-body">
                <ul class="task-list">
                    <li class="task-list-item"><label class="task-list-control"><input type="checkbox" checked=""><span class="task-list-indicator"></span></label>  &nbsp;Everything in the <i>Essential</i> plan</li>
                    <li class="task-list-item"><label class="task-list-control"><input type="checkbox" checked=""><span class="task-list-indicator"></span></label>  &nbsp; 90 min. 1-on-1 session for career and project guidance.</li>
                    <li class="task-list-item"><label class="task-list-control"><input type="checkbox" checked=""><span class="task-list-indicator"></span></label>  &nbsp; In-depth instructor review of <a href="#deliverables">course deliverables</a>.</li>
                </ul>
            </div>
            <div class="card-footer bg-transparent">
                <div class="ai-center-all">
                    <p class="mt-0 mb-2" style="font-size: 0.9rem;">$2,000 USD</p>
                </div>
                <div class="ai-center-all">
                    <a href="https://forms.gle/Cz7omhnToUTpupD98" target="_blank" class="md-button md-button--purple-gradient mb-2 mb-md-1 mt-md-0 mt-1" style="cursor: pointer !important;">Apply</a>
                </div>
            </div>
        </div>
    </div>
</div>

> **ENTERPRISE** We also offer an accelerated 2-3 day live workshops with team project-based guidance (tooling, infrastructure) for enterprise customers which we've delivered across teams at Apple, Google and many other Fortune 500 companies, as well as early-stage startups to ensure they're aligning themselves for success. [Reach out](https://forms.gle/8L8ga4fTnmwss9by8){:target="_blank"} to us if your team is interested.

<div class="row mt-3 mb-0">
    <div class="col-md-12">
        <div class="admonition info">
            <p class="admonition-title">Reimbursement</p>
            <p>Our alumni have had a lot of success getting 100% of the course reimbursed by their employers since all of this directly falls under career development and, in many cases, immediately necessary for their work. After you apply and are accepted for a cohort, check out this <b><a href="../reimbursement" target="_blank">email template</a></b> that we've put together that you can send to your manager to get this course reimbursed.</p>
        </div>
    </div>
</div>

<hr style="margin-bottom: 2rem;">
<section class="p-4" style="background-color: #f5f9fd;">
<h2 class="ai-center-all mt-0 mb-2 md-typeset"><span class="mr-2">💸</span> Money Back Guarantee <span class="ml-2">💸</span></h2>
If you attend the live sessions and complete the deliverables yet still don’t find the course valuable, we’ll refund 100% of your payment within 30 days of the start of the course.
</section>

<section id="faq">
<h2 class="ai-center-all mt-0 mb-2 md-typeset">Frequently Asked Questions (FAQ)</h2>

<div class="faq-accordion mt-4" id="faq-accordion">
<div class="row">
    <div class="col-md-6" data-aos="fade-right">
        <div class="card">
            <div class="card-header collapsed" id="heading1" data-toggle="collapse" data-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
            <h5 class="my-0" style="display: inline-block;">Who is this course for?</h5>
            <span class="faq-toggle" aria-hidden="true" style="float:right;"></span>
            </div>
            <div id="collapseOne" class="collapse" aria-labelledby="heading1" data-parent="#faq-accordion">
            <div class="card-body">
            Machine learning is <b>not a separate industry</b>, instead, it's a powerful <b>way of thinking</b> about data that's not reserved for any one type of person.
                <ul>
                    <li><span class="twemoji mr-1"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path d="M10.3 8.24a.75.75 0 01-.04 1.06L7.352 12l2.908 2.7a.75.75 0 11-1.02 1.1l-3.5-3.25a.75.75 0 010-1.1l3.5-3.25a.75.75 0 011.06.04zm3.44 1.06a.75.75 0 111.02-1.1l3.5 3.25a.75.75 0 010 1.1l-3.5 3.25a.75.75 0 11-1.02-1.1l2.908-2.7-2.908-2.7z"></path><path fill-rule="evenodd" d="M2 3.75C2 2.784 2.784 2 3.75 2h16.5c.966 0 1.75.784 1.75 1.75v16.5A1.75 1.75 0 0120.25 22H3.75A1.75 1.75 0 012 20.25V3.75zm1.75-.25a.25.25 0 00-.25.25v16.5c0 .138.112.25.25.25h16.5a.25.25 0 00.25-.25V3.75a.25.25 0 00-.25-.25H3.75z"></path></svg></span><b>Software engineers</b> looking to learn ML and become even better software engineers. ML is integrated into increasingly more products so it's important to know how ML systems operate.</li>
                    <li><span class="twemoji mr-1"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill-rule="evenodd" d="M8.114 2.094a.75.75 0 01.386.656V9h1.252a.75.75 0 110 1.5H5.75a.75.75 0 010-1.5H7V4.103l-.853.533a.75.75 0 01-.795-1.272l2-1.25a.75.75 0 01.762-.02zm4.889 5.66a.75.75 0 01.75-.75h5.232a.75.75 0 01.53 1.28l-2.776 2.777c.55.097 1.057.253 1.492.483.905.477 1.504 1.284 1.504 2.418 0 .966-.471 1.75-1.172 2.27-.687.511-1.587.77-2.521.77-1.367 0-2.274-.528-2.667-.756a.75.75 0 01.755-1.297c.331.193.953.553 1.912.553.673 0 1.243-.188 1.627-.473.37-.275.566-.635.566-1.067 0-.5-.219-.836-.703-1.091-.538-.284-1.375-.443-2.471-.443a.75.75 0 01-.53-1.28l2.643-2.644h-3.421a.75.75 0 01-.75-.75zM7.88 15.215a1.4 1.4 0 00-1.446.83.75.75 0 01-1.37-.61 2.9 2.9 0 012.986-1.71 2.565 2.565 0 011.557.743c.434.446.685 1.058.685 1.778 0 1.641-1.254 2.437-2.12 2.986-.538.341-1.18.694-1.495 1.273H9.75a.75.75 0 010 1.5h-4a.75.75 0 01-.75-.75c0-1.799 1.337-2.63 2.243-3.21 1.032-.659 1.55-1.031 1.55-1.8 0-.355-.116-.584-.26-.732a1.068 1.068 0 00-.652-.298z"></path></svg></span><b>Data scientists</b> who want to want to go way beyond developing models in a notebook to wrapping them around robust workflows that enable ML systems to improve over time.</li>
                    <li><span class="twemoji mr-1"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill-rule="evenodd" d="M12.292 2.06a.75.75 0 00-.584 0L.458 6.81a.75.75 0 000 1.38L4.25 9.793v3.803a2.901 2.901 0 00-1.327.757c-.579.58-.923 1.41-.923 2.43v4.5c0 .248.128.486.335.624.06.04.117.073.22.124.124.062.297.138.52.213.448.149 1.09.288 1.925.288s1.477-.14 1.925-.288c.223-.075.396-.15.52-.213a2.11 2.11 0 00.21-.117A.762.762 0 008 21.28v-4.5c0-1.018-.344-1.85-.923-2.428a2.9 2.9 0 00-1.327-.758v-3.17l5.958 2.516a.75.75 0 00.584 0l5.208-2.2v4.003a2.552 2.552 0 01-.079.085 4.057 4.057 0 01-.849.65c-.826.488-2.255 1.021-4.572 1.021-.612 0-1.162-.037-1.654-.1a.75.75 0 00-.192 1.487c.56.072 1.173.113 1.846.113 2.558 0 4.254-.592 5.334-1.23.538-.316.914-.64 1.163-.896a2.84 2.84 0 00.392-.482h.001A.75.75 0 0019 15v-4.892l4.542-1.917a.75.75 0 000-1.382l-11.25-4.75zM5 15c-.377 0-.745.141-1.017.413-.265.265-.483.7-.483 1.368v4.022c.299.105.797.228 1.5.228s1.201-.123 1.5-.228V16.78c0-.669-.218-1.103-.483-1.368A1.431 1.431 0 005 15zm7-3.564L2.678 7.5 12 3.564 21.322 7.5 12 11.436z"></path></svg></span><b>College graduates</b> looking to learn ML and become even better software engineers. ML is integrated into increasingly more products so it's important to know how ML systems operate.</li>
                    <li><span class="twemoji mr-1"><svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" width="24" height="24"><path fill-rule="evenodd" d="M12 2.5c-3.81 0-6.5 2.743-6.5 6.119 0 1.536.632 2.572 1.425 3.56.172.215.347.422.527.635l.096.112c.21.25.427.508.63.774.404.531.783 1.128.995 1.834a.75.75 0 01-1.436.432c-.138-.46-.397-.89-.753-1.357a18.354 18.354 0 00-.582-.714l-.092-.11c-.18-.212-.37-.436-.555-.667C4.87 12.016 4 10.651 4 8.618 4 4.363 7.415 1 12 1s8 3.362 8 7.619c0 2.032-.87 3.397-1.755 4.5-.185.23-.375.454-.555.667l-.092.109c-.21.248-.405.481-.582.714-.356.467-.615.898-.753 1.357a.75.75 0 01-1.437-.432c.213-.706.592-1.303.997-1.834.202-.266.419-.524.63-.774l.095-.112c.18-.213.355-.42.527-.634.793-.99 1.425-2.025 1.425-3.561C18.5 5.243 15.81 2.5 12 2.5zM9.5 21.75a.75.75 0 01.75-.75h3.5a.75.75 0 010 1.5h-3.5a.75.75 0 01-.75-.75zM8.75 18a.75.75 0 000 1.5h6.5a.75.75 0 000-1.5h-6.5z"></path></svg></span><b>Product managers</b> who want to develop a technical foundation in MLOps so they can effectively communicate with their technical team and help develop and iterate on applications.</li>
                </ul>
            </div>
            </div>
        </div>
        <div class="card">
            <div class="card-header collapsed" id="heading3" data-toggle="collapse" data-target="#collapse3" aria-expanded="true" aria-controls="collapse3">
            <h5 class="my-0" style="display: inline-block;">What are the prerequisites?</h5>
            <span class="faq-toggle" aria-hidden="true" style="float:right;"></span>
            </div>
            <div id="collapse3" class="collapse" aria-labelledby="heading3" data-parent="#faq-accordion">
            <div class="card-body">
                <p>You should know how to code in Python and the basics of machine learning.</p>
                <ul>
                    <li>Python (variables, lists, dictionaries, functions, classes)</li>
                    <li>Scientific computing (NumPy, Pandas)</li>
                    <li>ML/DL (basics of regression, training etc. with scikit-learn)</li>
                </ul>
                <p>You will <b>not</b> need to know any deep learning topics or related libraries (PyTorch, Tensorflow, etc.) as this course is largely model-agnostic and the focus will be on how to responsible deliver value with <b>any</b> kind of machine learning model.
            </div>
            </div>
        </div>
        <div class="card">
            <div class="card-header collapsed" id="heading2" data-toggle="collapse" data-target="#collapse2" aria-expanded="true" aria-controls="collapse2">
            <h5 class="my-0" style="display: inline-block;">Why should I take this course now?</h5>
            <span class="faq-toggle" aria-hidden="true" style="float:right;"></span>
            </div>
            <div id="collapse2" class="collapse" aria-labelledby="heading2" data-parent="#faq-accordion">
            <div class="card-body">
                Machine learning is increasingly incorporated into many products and so companies are looking for people with increasingly deeper knowledge on not only modeling, but how to operationalize it (MLOps). It's a major advantage to understand the fundamentals of this field at this nascent stage so you can responsibly deliver value with ML as a foundational developer in your industry.
            </div>
            </div>
        </div>
        <div class="card">
            <div class="card-header collapsed" id="heading5" data-toggle="collapse" data-target="#collapse5" aria-expanded="true" aria-controls="collapse5">
            <h5 class="my-0" style="display: inline-block;">Can I do the course part-time?</h5>
            <span class="faq-toggle" aria-hidden="true" style="float:right;"></span>
            </div>
            <div id="collapse5" class="collapse" aria-labelledby="heading5" data-parent="#faq-accordion">
            <div class="card-body">
                Absolutely, this course is meant for busy people who are in school or working full-time. You can go through the weekly structure when you choose and attend any/all of the live Q&A and reading sessions which are offered multiple times a week across different timezones.
            </div>
            </div>
        </div>
    </div>
    <div class="col-md-6" data-aos="fade-left">
        <div class="card">
            <div class="card-header collapsed" id="heading7" data-toggle="collapse" data-target="#collapse7" aria-expanded="true" aria-controls="collapse7">
                <h5 class="my-0" style="display: inline-block;">What is the time commitment?</h5>
                <span class="faq-toggle" aria-hidden="true" style="float:right;"></span>
            </div>
            <div id="collapse7" class="collapse" aria-labelledby="heading7" data-parent="#faq-accordion">
                <div class="card-body">
                    Every week, we'll provide a strcutured list of todo items that will consist of reading a set of lessons on your own time and completing the corresponding code components alongside. If you have questions, you can attend the live Q&A sessions, post your question on the private community forumn or reach out to the instructors and TAs directly.
                </div>
            </div>
        </div>
        <div class="card">
            <div class="card-header collapsed" id="heading8" data-toggle="collapse" data-target="#collapse8" aria-expanded="true" aria-controls="collapse8">
            <h5 class="my-0" style="display: inline-block;">What happens after the course?</h5>
            <span class="faq-toggle" aria-hidden="true" style="float:right;"></span>
            </div>
            <div id="collapse8" class="collapse" aria-labelledby="heading8" data-parent="#faq-accordion">
            <div class="card-body">
                After the course, you'll always have access to our private community where you can connect with alumni and meet future cohorts as well. You can continue to ask questions about the topics (especially as new tools enter the market), get feedback on your work, etc.
            </div>
            </div>
        </div>
        <div class="card">
            <div class="card-header collapsed" id="heading10" data-toggle="collapse" data-target="#collapse10" aria-expanded="true" aria-controls="collapse10">
            <h5 class="my-0" style="display: inline-block;">Is this course fully remote?</h5>
            <span class="faq-toggle" aria-hidden="true" style="float:right;"></span>
            </div>
            <div id="collapse10" class="collapse" aria-labelledby="heading10" data-parent="#faq-accordion">
            <div class="card-body">
                Yes, this course is 100% remote which means no travel but you'll meet fellow students from around the world and learn from each other.
            </div>
            </div>
        </div>
        <div class="card">
            <div class="card-header collapsed" id="heading11" data-toggle="collapse" data-target="#collapse11" aria-expanded="true" aria-controls="collapse11">
            <h5 class="my-0" style="display: inline-block;">What is the refund policy?</h5>
            <span class="faq-toggle" aria-hidden="true" style="float:right;"></span>
            </div>
            <div id="collapse11" class="collapse" aria-labelledby="heading11" data-parent="#faq-accordion">
            <div class="card-body">
                If you follow along the weekly structure and complete the iterative deliverables and if you're not 100% satisfied by the end of the first 30 days, we'll refund 100% of the cost.
            </div>
            </div>
        </div>
    </div>
</div>
</div>
</section>

<div class="row mt-3 mb-0">
    <div class="col-md-12">
        <div class="admonition question">
            <p class="admonition-title">More questions?</p> <p>Feel free to send us an <a href="mailto:goku@madewithml.com" target="_blank">email</a> with all your additional questions and we'll get back to you very soon.</p>
        </div>
    </div>
</div>

<hr style="margin-top: 2rem; margin-bottom: 2rem;">

<!-- Citation -->
To cite this content, please use:

```bibtex linenums="1"
@misc{madewithml,
    author       = {Goku Mohandas},
    title        = {Made With ML},
    howpublished = {\url{https://madewithml.com/}},
    year         = {2021}
}
```