---
layout: single
title: Books and Edited Collections
permalink: /publications/
classes: wide
entries_layout: grid
sidebar:
        nav: pubs
pub-type: books
---
{% assign type = page.pub-type %}
{% assign publications = site.data.publications[type] | reverse  %}

<div class="grid-entries">

{% for pub in publications %}
<div class="grid__item-adjust">
   <div class="archive__item">
      {% if pub.image %}
         {% if pub.image contains "://" %}
            {% assign pub-img = book.image %}
         {% else %}
            {% assign pub-img = pub.image | relative_url %}
         {% endif %}
      {% else %}
         {% assign pub-img = "assets/images/portrait-placeholder.png" | relative_url %}
      {% endif %}

      {% if pub.url %}
         <a href="{{ pub.url }}" target="_blank" rel="noopener noreferrer">
         <img src="{{ pub-img }}" style="max-height:13em">
         <p style="font-size: 0.65em"><em>{{ pub.title }}</em></p>
         </a>
      {% else %}
         <img src="{{ pub-img }}" style="height=auto; max-height:13em">
         <p style="font-size: 0.65em"><em>{{ pub.title }}</em></p>
      {% endif %}
      <p style="font-size: 0.61em">
         {% if pub.responsible %}
            by <span style="color:lightslategray"><strong>{{ pub.responsible }}</strong></span>
         {% endif %}
         <br>
         {% if pub.date %}
            {% if pub.place and pub.publisher %}
               {{ pub.place }}: {{ pub.publisher }}, {{ pub.date }}
            {% elsif pub.place or pub.publisher %}
               {{ pub.place }}{{ pub.publisher }}, {{ pub.date }}
            {% else %} {{ pub.date }}
            {% endif %}
         {% elsif pub.place and pub.publisher %}
            {{ pub.place }}: {{ pub.publisher }}
            {% else %} {{ pub.place }} {{ pub.publisher }}
         {% endif %}
      </p>

   </div>
</div>
{% endfor %}
</div>
