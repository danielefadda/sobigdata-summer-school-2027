---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default-full
title: "Home"
show_sidetoc: false
subtitle: "21-27 June 2026 – Baratti (Piombino) – TUSCANY (Italy)"
header_type: hero #base, post, hero,image, splash
header_img: assets/images/pool-1.jpg
header_title: "Data Analysis and AI<br> in Sport, Health and Wellbeing"
---

<div class="full-width-wrapper">
    <img src="{{ site.baseurl }}/assets/images/header.svg" alt="sbd-pattern" class="full-width-image">
</div>

<div class="introduction">
    <div class="container">
        <div class="row pt-2">
            <div class="col-md-8 offset-md-2 col-sm-12">
               <h3>
The Summer School aims to equip researchers, data scientists and social scientists with the methodologies and insights necessary to address complex societal challenges.
</h3>
            </div>
        </div>
    </div>
</div>
<div class="container-fluid my-3 py-5 full-width-wrapper bg-color-full bg-color">
 <h4 class="mb-5 text-white text-center text-uppercase"><strong>The school is organised in four thematic days</strong></h4>
{% include img-gallery-cards.html 
    datasource='school-days'
    img_url='image'
    name='day'
    description='description'
    container='fluid' 
%}
</div>


<div class="introduction">
    <div class="container">
        <div class="row pt-2">
            <div class="col-md-8 offset-md-2 col-sm-12">
                <p>
                The Summer School provides a unique <strong>interdisciplinary mixture</strong> where participants can explore state-of-the-art tools in <strong>data analysis, machine learning, and artificial intelligence</strong>. The school will have lessons from experts during the morning and will leave the afternoon to <strong>group work guided by dedicated tutors</strong> helping them in defining and developing their project which will be evaluated at the end of the school by a panel of experts.</p>
                <hr>
                <p>
                <strong>Expert-led lectures</strong> will guide attendees through real-world applications of big data and AI, fostering innovative solutions. Alongside technical skill-building, participants engage in <strong>ethical and governance discussions</strong> that highlight the responsible use of data.
                </p>
            </div>
        </div>
    </div>

</div>


<div class="where">
    <div class="container">
        <div class="row pt-2 ">
            <div class="col-md-6 col-sm-12">
               <img src="{{ site.baseurl }}/assets/images/venue/poggio3.jpeg" alt="Poggio all'Agnello">
            </div>
        <div class="col-md-6 col-sm-12">
            <h3>WHERE</h3>
            <p class="lead">Nested in the gulf of Baratti on the “Etruscan Coast” in Tuscany (Italy), <a href="{{ site.baseurl }}{% link _pages/venue.markdown %}.html">Poggio all’Agnello </a> is a fully equipped resort that will host the 2026 edition of the SoBigData Summer school.
            </p>
            <h3>Registration & Deadline</h3>
            <p>Early registration until {{ site.data.school-info.registration.early.deadline }}.</p>
            <p><strong>Late registration between {{ site.data.school-info.registration.late.start }} and {{ site.data.school-info.registration.late.deadline }} will have an additional cost.</strong></p>
            </div>
        </div>
    </div>
</div>

<div class="aim mt-5">
    <div class="container">
        <div class="row pt-2 ">
        <div class="col-md-6 col-sm-12">
            <h3>AIM OF THE SCHOOL</h3>
                <p>
                {{ site.data.school-info.aim }}
                </p>
                <p>
                    {{ site.data.school-info.aim_extended }}
                </p>
            </div>
            <div class="col-md-6 col-sm-12">
            <div class="project lead px-3 py-1">
               <h3>Topics</h3>
                <ul>
                {% for topic in site.data.school-info.topics %}
                    <li>{{ topic }}</li>
                {% endfor %}
                </ul>
            </div>
            <div class="project lead px-3 py-1 mt-2">   
                <h3>Target attendees</h3>
                <ul>
                {% for attendee in site.data.school-info.target_attendees %}
                    <li>{{ attendee }}</li>
                {% endfor %}
                </ul>
            </div>
        </div>
    </div>
</div>

<div class=" container-fluid my-5 pt-2 pb-5 bg-color-full bg-color">
    <div class="container">
        <div class="row">
            <div class="col-md-12">
                <h3 class="text-white">Keynote Speakers</h3>
                <hr>
            </div>
        </div>
    </div>
{% include img-home-cards.html  
    datasource='speaker-cards' 
    url='img_url' 
    name='name' 
    surname='surname'
    description='institution' 
    container='fluid' 
%}
</div>

<div class="container cta">
        <div class="row py-5">
            <div class="col-md-12">
                <div>
                    <h3>Interested in attending?</h3>
                    <a href="{{site.baseurl}}{% link _pages/registration.markdown %}.html" class="btn btn-primary">Register now</a>
                </div>
            </div>
        </div>
</div>

<div class="container credits pt-5">
    <div class="row">
        <div class="col-md-12">
            <h5>This summer school is organized and supported by</h5>
        <div class="logo-grid">
                    <a href="http://sobigdata.eu" target="_blank" title="SoBigData RI"><img src="{{ site.baseurl }}/assets/images/Logo_SoBigData_RI_560_X_100.png" alt="SoBigData RI" ></a>
                    <a href="https://www.fondazionearea.org/home-page" target="_blank" title="Fondazione AREA"><img src="{{ site.baseurl }}/assets/images/fondazioneAREA.png" alt="Fondazione area" ></a>
                    <a href="https://consorzioquinn.it/" target="_blank" title="Consorzio Quin"><img src="{{ site.baseurl }}/assets/images/Logo_consorzio-quin-logo.svg" alt="Consorzio Quin" ></a>
                    <a href="https://www.phd-ai.it/" target="_blank" title="PhD AI"><img src="{{ site.baseurl }}/assets/images/Logo_phd-ai.png" alt="phd-ai" ></a>
        </div>
        </div>
    </div>
</div>
