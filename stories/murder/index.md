# Murder Stories

<ul class="list">
{% assign files = site.static_files | where_exp: "f", "f.path contains '/stories/Murder/'" %}
{% for f in files %}
  <li><a href="{{ f.path | relative_url }}">{{ f.name }}</a></li>
{% endfor %}
</ul>
