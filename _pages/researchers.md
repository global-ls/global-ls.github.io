---
title: "Researchers"
layout: single
permalink: /team/researchers/
classes: wide
sidebar:
        nav: team
feature_row:
   - image_path: /assets/images/diana-roig.jpg
     alt: "Diana Roig Sanz"
     title: "Diana Roig Sanz (PI)"
     url: team/researchers/diana-roig/
     excerpt: "Coordinator of GlobaLS - 2018 ERC Starting Grant holder - Ramon y Cajal Research Fellow (UOC) - PI of MapModern"
   - image_path: /assets/images/laura-folica.png
     alt: "Laura Fólica"
     title: "Laura Fólica"
     url: team/researchers/laura-folica/
     excerpt: "Postdoctoral researcher (UOC) - Assistant Professor at Universitat Pompeu Fabra (UPF)"
   - image_path: assets/images/marta-puxan.png
     alt: "Marta Puxan Oliva"
     title: "Marta Puxan Oliva"
     url: team/researchers/marta-puxan/
     excerpt: "Postdoctoral researcher (UOC) - Assistant Professor at the Universitat de Barcelona."
   - image_path: /assets/images/neus-rotger.jpg
     alt: "Neus Rotger"
     title: "Neus Rotger"
     url: team/researchers/neus-rotger/
     excerpt: "Associate Professor of Comparative Literature (UOC) - Guest Lecturer at Universitat Autònoma de Barcelona"
   - image_path: /assets/images/v-ikoff-bw.jpg
     alt: "Ventsislav Ikoff"
     title: "Ventsislav Ikoff"
     url: team/researchers/ventsislav-ikoff/
     excerpt: "Postdoctoral researcher (UOC)"
---
<section class="entries-grid">
{% if include.id %}
  {% assign feature_row = page[include.id] %}
{% else %}
  {% assign feature_row = page.feature_row %}
{% endif %}

{% for f in feature_row %}

   <div class="grid__item-adjust">

    {% if f.url contains "://" %}
      {% capture f_url %}{{ f.url }}{% endcapture %}
    {% else %}
      {% capture f_url %}{{ f.url | relative_url }}{% endcapture %}
    {% endif %}

      <article class="archive__item">
       <a href="{{ f_url }}">

       <img src=
              {% if f.image_path contains "://" %}
                "{{ f.image_path }}"
              {% else %}
                "{{ f.image_path | relative_url }}"
              {% endif %}
            alt="{% if f.alt %}{{ f.alt }}{% endif %}">

         <h2 class="archive__item-title">{{ f.title }}</h2>
         </a>

        {% if f.excerpt %}
         <div class="archive__item-excerpt">
         {{ f.excerpt | markdownify }}
         </div>
        {% endif %}

      </article>
   </div>
{% endfor %}
</section>
