---
title: Murder
layout: default
---

# Murder Stories

Welcome to the Murder collection. Choose a story below:

<ul class="story-list">
{% assign files = site.static_files 
   | where_exp: "f", "f.path contains '/stories/murder/' and f.extname == '.docx'" 
   | sort: "name" %}
{% for f in files %}
  {% unless f.name == 'index.md' %}
    {% assign pretty = f.name 
       | remove: '.docx' 
       | replace: '_s', \"'s\" 
       | replace: '_', ' ' %}
    <li><a href="{{ f.path | relative_url }}">{{ pretty }}</a></li>
  {% endunless %}
{% endfor %}
</ul>

<style>
.story-list {
  list-style-type: none;
  padding-left: 0;
  margin-top: 1em;
}
.story-list li {
  margin: 0.4em 0;
}
.story-list a {
  text-decoration: none;
  color: #2c3e50;
  font-weight: 500;
  font-family: Georgia, serif;
}
.story-list a:hover {
  color: #e74c3c;
  text-decoration: underline;
}
</style>
