---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default-full
title: "Home"
show_sidetoc: true
subtitle: "21-27 June 2026 – Baratti (Piombino) – TUSCANY (Italy)"
header_type: hero #base, post, hero,image, splash
header_img: assets/images/poggio.jpg
header_title: "Data Analysis and AI <br>in Sport, Health and Wellbeing"

---

<div class="full-width-wrapper">
    <img src="{{ site.baseurl }}/assets/images/header.svg" alt="sbd-pattern" class="full-width-image">
</div>

<div class="venue">
    <div class="container">
        <div class="row pt-2 ">
            <div class="col-md-8 offset-md-2 col-sm-12">
                <h3>Social program </h3>
                <p class="lead" style="text-align:justify">The social program is structured as follows:</p>
                    <ul>
                        <li>A welcome cocktail on Sunday late afternoon 21 June 2026</li>
<li>Visit to the award-winning <a href="https://www.petrawine.it/en/home-english/" target="_blank"> Petra Winery</a>: a guided tour of the vineyards and the winery designed by architect Mario Botta and a dinner with wine tasting.</li>
<li>A dj-set night with pizza to celebrate the end of the school in an informal setting within the Poggio all’Agnello venue</li>
                    </ul>
            </div>
        </div>
    </div>
</div>

<div class="container">
{% assign surrounding = "
                    /assets/images/social/baratti6.jpeg,
                    /assets/images/social/baratti7.jpeg,
                    /assets/images/social/baratti9.jpeg,
                    /assets/images/social/baratti10.jpeg,
                    /assets/images/social/petra1.jpeg,
                    /assets/images/social/petra-2.webp,
                    /assets/images/social/petra-3.jpeg,
                    /assets/images/social/petra-4.jpeg,
                    /assets/images/social/baratti10.jpeg,
                    /assets/images/social/restaurant2.webp,
                    "
                    %}

                {% include_cached snippets/masonry.html external=surrounding %}
</div>
