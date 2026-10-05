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
                <h3>The venue</h3>
                <p class="lead" style="text-align:justify">Nested in the gulf of Baratti on the “Etruscan Coast” in Tuscany (Italy), <a href="https://www.poggioallagnello.it/en/">Poggio all’Agnello </a> is a fully equipped resort that will host the 2026 edition of the SoBigData Summer school.</p>
                <p>The venue has:</p>
                    <ul>
                        <li>Fully equipped conference rooms</li>
                        <li>Outside facilities for communal work in a 10 hectare-park</li>
                        <li>An Olympic size swimming pool and two smaller swimming pools</li>
                        <li>Facilities for children and families</li>
                        <li>Services and activities such as bike rental, sport facilities and more (https://www.poggioallagnello.it/en/services-and-activities/)</li>
                        <li>Access for those with impaired mobility</li>
                        <li>An animal-friendly policy</li>
                        <li>A restaurant that can accommodate menus for vegetarian, vegan, celiac and lactose-intolerant</li>
                        <li>Free charge for electric vehicles and solar panel system</li>
                    </ul>
            </div>
        </div>
    </div>
</div>


<div class="accommodation py-5">
    <div class="container">
        <div class="row pt-2 ">
            <div class="col-md-8 offset-md-2 col-sm-12">
                <h3>Accommodation</h3>
                <p class="lead" style="text-align:justify">The venue <a href="https://www.poggioallagnello.it/en/">Poggio all’Agnello </a> offers a variety of accommodation. For more informations you can visit Poggio all'Agnello website.</p>

                 {% assign accomodation = "
                    /assets/images/accomodation/room1.jpeg,
                    /assets/images/accomodation/room3.jpeg,
                    /assets/images/accomodation/room7.jpeg,
                    /assets/images/accomodation/room8.jpeg,
                    /assets/images/accomodation/room9.jpeg,
                    /assets/images/accomodation/room11.jpeg,
                    /assets/images/accomodation/room12.jpeg,
                    /assets/images/accomodation/room14.jpeg,
                    /assets/images/accomodation/room15.jpeg"
                    %}

                {% include_cached snippets/masonry.html external=accomodation %}
            </div>
        </div>
    </div>
</div>





<div id="surroundings">
    <div class="container">
        <div class="row pt-2 ">
            <div class="col-md-8 offset-md-2 col-sm-12">
                <h3>The surroundings</h3>
                <p>The Gulf of Baratti hosts the <a href="https://www.parchivaldicornia.it/en/archaeological-parks/archaeological-park-of-baratti-and-populonia/">Archaeological Park of Baratti and Populonia </a>, with a necropolis and acropolis across a site that is considered one of the most relevant Etruscan cities, the only one whose remains are on the Tyrrhenian Sea. The park’s protected area stretches over 80 hectares and comprises some of the most beautiful beaches and coves in Tuscany.</p>
<p>Moreover, the venue is located on the <a href="https://www.lastradadelvino.com/en/">Road of Wine and Oil</a>, an itinerary that comprises some of Tuscany’s most refined wineries and oil productors.</p>
                <p>
                The region also hosts numerous <a href="https://www.costadeglietruschi.eu/en/experience-eng/food-festivals-a-journey-through-the-flavours-of-the-etruscan-coast/">food festivals</a> comprising a variety of local products.</p>

                {% assign surrounding = "
                    /assets/images/surroundings/baratti5.jpeg,
                    /assets/images/surroundings/baratti8-scaled.jpeg,
                    /assets/images/surroundings/baratti10.jpeg,
                    /assets/images/surroundings/baratti11.jpeg,
                    /assets/images/surroundings/baratti13.jpeg,
                    /assets/images/surroundings/baratti14.jpeg"
                    %}

                {% include_cached snippets/masonry.html external=surrounding %}
            </div>
        </div>
    </div>
</div>





<div class="container">
{% include_cached snippets/masonry.html internal="surroundings" %}
</div>

<div id="reach-baratti">
    <div class="container">
        <div class="row pt-2 ">
            <div class="col-md-8 offset-md-2 col-sm-12">
                <h3>How to reach the venue</h3>
                    <p>
                    Poggio all’Agnello is a resort which is approximately one hour from Pisa Airport. From Pisa, the venue can be reached by car or by train, which stops in the nearby <a href="https://www.thetrainline.com/en/stations/populonia" target="_blank"> station of Populonia</a>.
Once at the Populonia train station, <a href="http://tinyurl.com/2x66rzn6"> venue is 500 metres away</a>
                    </p>
                    <ul>
                        <li><i class="fas fa-plane"></i> BY PLANE: The nearest airports are Pisa or Rome. From there you have to take a train or rent a car.</li>
                        <li><i class="fas fa-train"></i> BY TRAIN: The nearest train station is “Populonia”. You can buy your ticket for the train directly at “Pisa Centrale” or “Roma Termini” stations (or book it on</li> www.trenitalia.com two month before, otherwise it is not available on the website). 
                        <li><i class="fas fa-car"></i> BY CAR: The address is “Loc. Poggio all’Agnello, 31 · 57025 Piombino (LI) Tuscany”</li>
                    </ul>
                    {% assign venue = "
                    /assets/images/venue/2021-08-26.jpg,
                    /assets/images/venue/IMG_20190613_153137.jpg,
                    /assets/images/venue/Photo_3.webp,
                    /assets/images/venue/poggio3.jpeg,
                    /assets/images/venue/poggio5.jpeg,
                    /assets/images/venue/poggio9.jpeg,
                    /assets/images/venue/pool-1.jpg"
                    %}

                {% include_cached snippets/masonry.html external=venue %}
            </div>
        </div>
    </div>
</div>