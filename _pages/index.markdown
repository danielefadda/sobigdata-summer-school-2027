---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default-full
title: "Home"
show_sidetoc: false
subtitle: "20-25 June 2027 – Baratti (Piombino) – TUSCANY (Italy)"
header_type: hero #base, post, hero,image, splash
header_img: assets/images/human-ai-coevolution.jpeg
header_title: "Complex Social Systems<br> in the Age of AI"
---

<div class="full-width-wrapper">
    <img src="{{ '/assets/images/header.svg' | relative_url }}" alt="sbd-pattern" class="full-width-image">
</div>

<div class="introduction">
    <div class="container">
        <div class="row pt-2">
            <div class="col-md-8 offset-md-2 col-sm-12">
               <h3>
Data, Models and Human–AI Coevolution: how algorithms and people shape each other, and how to steer this process towards collective wellbeing.
</h3>
            </div>
        </div>
    </div>
</div>
<div class="container-fluid my-3 py-5 full-width-wrapper bg-color-full bg-color">
 <h4 class="mb-5 text-white text-center text-uppercase"><strong>Four days of lectures, followed by the project presentations</strong></h4>
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
                The Summer School provides a unique <strong>interdisciplinary mixture</strong> where participants can explore state-of-the-art methods in <strong>data analysis, modelling and artificial intelligence</strong> applied to complex social systems. Lectures by experts take place in the morning, while the afternoon is dedicated to <strong>group work on project challenges, guided by dedicated tutors</strong>. Projects are presented on the last day and evaluated by a panel of experts.</p>
                <hr>
                <p>
                <strong>Expert-led lectures</strong> will guide attendees through the empirical analysis of coevolution patterns on online platforms, the computational modelling of socio-technical mechanisms, and the design of interventions and algorithms that reconcile individual goals with <strong>collective wellbeing</strong>.
                </p>
            </div>
        </div>
    </div>

</div>


<div class="where">
    <div class="container">
        <div class="row pt-2 ">
            <div class="col-md-6 col-sm-12">
               <img src="{{ '/assets/images/venue/poggio3.jpeg' | relative_url }}" alt="Poggio all'Agnello">
            </div>
        <div class="col-md-6 col-sm-12">
            <h3>WHERE</h3>
            <p class="lead">Nested in the gulf of Baratti on the “Etruscan Coast” in Tuscany (Italy), <a href="{{ '/venue.html' | relative_url }}">Poggio all’Agnello </a> is a fully equipped resort that will host the 2027 edition of the SoBigData Summer school.
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

{% assign home_speakers = site.data.speaker-cards | where: "home", true %}
<div class=" container-fluid my-5 pt-2 pb-5 bg-color-full bg-color">
    <div class="container">
        <div class="row">
            <div class="col-md-12">
                <h3 class="text-white">Keynote Speakers</h3>
                <hr>
                {% if home_speakers.size == 0 %}
                <p class="lead text-white">TBA</p>
                {% endif %}
            </div>
        </div>
    </div>
{% if home_speakers.size > 0 %}
{% include img-home-cards.html  
    datasource='speaker-cards' 
    url='img_url' 
    name='name' 
    surname='surname'
    description='institution' 
    container='fluid' 
%}
{% endif %}
</div>

<div class="container cta">
        <div class="row py-5">
            <div class="col-md-12">
                <div>
                    <h3>Interested in attending?</h3>
                    <a href="{{ '/registration.html' | relative_url }}" class="btn btn-primary">Register now</a>
                </div>
            </div>
        </div>
</div>

<div class="container credits pt-5">
    <div class="row">
        <div class="col-md-12">
            <h5>This summer school is organized and supported by</h5>
        <div class="logo-grid">
                    <a href="http://sobigdata.eu" target="_blank" title="SoBigData RI"><img src="{{ '/assets/images/Logo_SoBigData_RI_560_X_100.png' | relative_url }}" alt="SoBigData RI" ></a>
                    <a href="https://www.caio-project.it/" target="_blank" title="CAIO - City-AI Coevolution"><img src="{{ '/assets/images/logo_CAIO.svg' | relative_url }}" alt="CAIO" ></a>
        </div>
        </div>
    </div>
</div>
