---
title: "Researchers"
layout: single
permalink: /team/researchers/
classes: wide
sidebar:
        nav: "team"
team:
   - res: Diana Roig Sanz
   - res: Laura Fólica
   - res: Marta Puxan Oliva
   - res: Neus Rotger
   - res: Aurea Mota
   - res: Maud Gonne
   - res: Ventsislav Ikoff

---
<section class="entries-grid">
{%- assign team = page.team -%}

{%- for r in team -%}

   <div class="grid__item-adjust">
   {%- assign person = r.res -%}
   {%- assign person = site.data.team[person] -%}
    {%- if person.url contains "://" -%}
      {%- capture person_url -%}{{- person.url -}}{%- endcapture -%}
    {%- else -%}
      {%- capture person_url -%}{{- person.url | relative_url -}}{%- endcapture -%}
    {%- endif -%}

      <article class="archive__item">
      {%- if person.url -%}      
       <a href="{{- person_url -}}">
      {%- endif -%}       

       <img src="
              {%- if person.avatar contains "://" -%}
                {{- person.avatar -}}
              {%- else -%}
                {{- person.avatar | relative_url -}}
              {%- endif -%}"
            alt="{%- if person.name -%}{{- person.name -}}{%- endif -%}">

         <h2 class="archive__item-title">{{- person.name -}}</h2>
      {%- if person.url -%}
         </a>
      {%- endif -%}        

        {%- if person.bio-short -%}
         <div class="archive__item-excerpt">
         {{- person.bio-short | markdownify -}}
         </div>
        {%- endif -%}

      </article>
   </div>
{%- endfor -%}
</section>
