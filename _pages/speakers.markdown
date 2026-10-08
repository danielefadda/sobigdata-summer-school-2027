---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default-full
title: "Speakers"
show_sidetoc: true
subtitle: "20-25 June 2027 – Baratti (Piombino) – TUSCANY (Italy)"
header_title: "Complex Social Systems<br> in the Age of AI"
---

<div class="full-width-wrapper">
    <img src="{{ '/assets/images/header.svg' | relative_url }}" alt="sbd-pattern" class="full-width-image">
</div>

<div class="registration">
    <div class="container">
        <div class="row pt-2 ">
            <div class="col-md-8 offset-md-2 col-sm-12">
                <h2>Speakers</h2>
                <hr>
                <p class="lead">
                    Our program features an international panel of researchers, academics, and industry professionals. During the morning sessions, these experts will guide attendees through state-of-the-art methodologies, addressing the empirical analysis, modelling and design of socio-technical systems in which humans and AI coevolve.
                </p>
                <hr>
                {% if site.data.speaker-cards.size == 0 %}
                <p><em>The list of speakers will be announced soon.</em></p>
                {% endif %}
                <div class="container py-3" id="speakers-container">
                {% assign sorted_speakers = site.data.speaker-cards | sort: "day" %}
                {% for day_info in site.data.school-info.days %}
                    {% assign day_index = forloop.index %}
                    {% assign day_speakers = "" | split: "" %}
                    {% assign home_speakers = "" | split: "" %}
                    {% for speaker in sorted_speakers %}
                        {% if speaker.program and speaker.day == day_index %}
                            {% if speaker.home %}
                                {% assign home_speakers = home_speakers | push: speaker %}
                            {% else %}
                                {% assign day_speakers = day_speakers | push: speaker %}
                            {% endif %}
                        {% endif %}
                    {% endfor %}
                    {% assign day_speakers = home_speakers | concat: day_speakers %}
                    {% if day_speakers.size > 0 %}
                    <div class="day-section">
                        <h3 class="day-title">{{ day_info.day }}</h3>
                        {% for speaker in day_speakers %}
                        <div class="row py-3 my-3 project" >
                            <div class="col-md-4">
                                <div class="project-img"><img src="{{ speaker.img_url | relative_url }}" alt="{{ speaker.name }}" style="width:100%"></div>
                            </div>
                            <div class="col-md-8">
                                <div class="project-body">
                                    <h5>{{ speaker.name }} {{ speaker.surname }}</h5>
                                    <p><strong> {{ speaker.institution }}</strong></p>
                                    <p>{{ speaker.bio }}</p>
                                    {% assign topics = speaker.topics | split: "," %}
                                </div>
                            </div>
                        </div>
                        {% endfor %}
                    </div>
                    {% endif %}
                {% endfor %}

</div>
            </div>
        </div>
    </div>

</div>



<div class="registration">
    <div class="container">
        <div class="row pt-2 ">
            <div class="col-md-8 offset-md-2 col-sm-12">
                <h2>Tutors</h2>
                <hr>
                <p class="lead">
                    Students will have the opportunity to interact with tutors during the afternoon sessions, which will be dedicated to hands-on activities and project work. These tutors will provide guidance and support as students apply the concepts learned in the morning sessions to real-world challenges.
                </p>
                <hr>
                {% if site.data.tutors-cards.size == 0 %}
                <p><em>The list of tutors will be announced soon.</em></p>
                {% endif %}
                <div class="container py-3" id="speakers-container">
                    <div class="day-section">
                        <h3 class="day-title">{{ day_info.day }}</h3>
                        {% for tutor in site.data.tutors-cards %}
                        <div class="row py-3 my-3 project" >
                            <div class="col-md-4">
                                <div class="project-img"><img src="{{ tutor.img_url | relative_url }}" alt="{{ tutor.name }}" style="width:100%"></div>
                            </div>
                            <div class="col-md-8">
                                <div class="project-body">
                                    <h5>{{ tutor.name }} {{ tutor.surname }}</h5>
                                    <p><strong> {{ tutor.institution }}</strong></p>
                                    <p>{{ tutor.bio }}</p>
                                    {% assign topics = tutor.topics | split: "," %}
                                </div>
                            </div>
                        </div>
                        {% endfor %}
                    </div>
                </div>
            </div>
        </div>
    </div>

</div>

<script>
document.addEventListener('DOMContentLoaded', function() {
  const headings = document.querySelectorAll('h1, h2, h3, h4, h5, h6');
  headings.forEach(function(heading) {
    if (!heading.id) {
      let text = heading.textContent.trim();
      let id = text
        .toLowerCase()
        .replace(/[^\w\s-]/g, '') 
        .replace(/\s+/g, '-')
        .replace(/-+/g, '-');
      heading.id = id;
    }
  });
});
</script>
