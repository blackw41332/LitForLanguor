---
title: Eldritch Horror
layout: default
---

# Eldritch Horror Stories

Welcome to the Eldritch Horror collection. Choose a story below:

<ul class="story-list">
{% assign files = site.static_files 
   | where_exp: "f", "f.path contains '/stories/eldritch-horror/' and f.extname == '.docx'" 
   | sort: "name" %}
{% for f in files %}
  {% assign base  = f.name | split: "." | first %}
  {% assign pretty = base 
     | replace: "_s", "'s" 
     | replace: "_", " " %}
  <li><a href="{{ f.path | relative_url }}">{{ pretty }}</a></li>
{% endfor %}
</ul>
