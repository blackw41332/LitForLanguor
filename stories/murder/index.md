---
title: Murder
layout: default
---

# Murder Stories

<ul class="list">
{% assign files = site.static_files | where_exp: "f", "f.path contains '/stories/murder/'" %}
{% for f in files %}
  {% unless f.name == 'index.md' %}
    <li><a href="{{ f.path | relative_url }}">{{ f.name }}</a></li>
  {% endunless %}
{% endfor %}
</ul>
{% assign files = site.static_files | where_exp: "f", "f.path contains '/stories/murder/' and f.extname == '.docx'" %}

