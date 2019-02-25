---
layout: single
title: "PhD Students"
permalink: /team/phd
sidebar:
        nav: "foo"
feature_row:
  - image_path: assets/images/portrait-placeholder.png
    alt: "Pau Bosch Santos"
    title: "Pau Bosch Santos"
    url: /team/pau-bosch/

  - image_path: /assets/images/ana-kvirikashvili.jpg
    alt: "Ana Kvirikashvili"
    title: "Ana Kvirikashvili"
    url: /team/ana-kvirikashvili/

  - image_path: /assets/images/aina-vidal.jpg
    alt: "Aina Vidal Pérez"   
    title: "Aina Vidal Pérez"
    url: /team/aina-vidal/

  - image_path: /assets/images/elisabet-carbo.jpg
    alt: "Elisabet Carbó Catalan"   
    title: "Elisabet Carbó"
    url: /team/elisabet-carbo/
---
<section class="entries-grid">
{% if include.id %}
  {% assign feature_row = page[include.id] %}
{% else %}
  {% assign feature_row = page.feature_row %}
{% endif %}

{% for f in feature_row %}

<div class="grid__item" style="width: 160px">

    {% if f.url contains "://" %}
      {% capture f_url %}{{ f.url }}{% endcapture %}
    {% else %}
      {% capture f_url %}{{ f.url | relative_url }}{% endcapture %}
    {% endif %}

      <div class="archive__item-team">
       <a href="{{ f_url }}">

       <img src=
              {% if f.image_path contains "://" %}
                "{{ f.image_path }}"
              {% else %}
                "{{ f.image_path | relative_url }}"
              {% endif %}
            alt="{% if f.alt %}{{ f.alt }}{% endif %}">

         <h2 class="archive__item-title" style="clear: both">{{ f.title }}</h2>

     </a>

        {% if f.excerpt %}
         <div class="archive__item-excerpt">
         {{ f.excerpt | markdownify }}
         </div>
        {% endif %}



      </div>
</div>
{% endfor %}
</section>
