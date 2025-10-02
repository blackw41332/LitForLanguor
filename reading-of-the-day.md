---
title: Reading of the Day
layout: default
permalink: /reading-of-the-day/
---

<h2>Random Reading</h2>
<div id="daily-reading"></div>

<script>
  var readings = [
    {% assign docs = site.static_files | where: "extname", ".docx" %}
    {% for f in docs %}
      "{{ f.path | relative_url }}"{% unless forloop.last %},{% endunless %}
    {% endfor %}
  ];
  var choice = readings[Math.floor(Math.random() * readings.length)];
  if (choice) {
    document.getElementById("daily-reading").innerHTML =
      '<a href="' + choice + '">Click here to read the random selection</a>';
  } else {
    document.getElementById("daily-reading").innerHTML =
      "Sorry, no readings available.";
  }
</script>
