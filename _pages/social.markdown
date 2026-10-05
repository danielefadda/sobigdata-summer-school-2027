---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default-full
title: "Home"
show_sidetoc: true
subtitle: "20-25 June 2027 – Baratti (Piombino) – TUSCANY (Italy)"
header_type: hero #base, post, hero,image, splash
header_img: assets/images/poggio.jpg
header_title: "Complex Social Systems<br> in the Age of AI"

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
                        <li>A welcome cocktail on Sunday late afternoon, 20 June 2027</li>
<li>Social event: TBA</li>
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
                    /assets/images/social/baratti10.jpeg,
                    /assets/images/social/restaurant2.webp,
                    "
                    %}

                {% include_cached snippets/masonry.html external=surrounding %}
</div>
