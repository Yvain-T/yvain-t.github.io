---
layout: default
title: "Projects"
permalink: /projects/
---

<h1>Projects</h1>

{% assign projects = "" | split: "," %}

<!-- Collect all unique projects -->
{% for post in site.publications %}
  {% for project in post.projects %}
    {% unless projects contains project %}
      {% assign projects = projects | push: project %}
    {% endunless %}
  {% endfor %}
{% endfor %}

<!-- Display projects and related publications -->
{% for project in projects %}
  <h2>{{ project }}</h2>
  <ul>
    {% for post in site.publications %}
      {% if post.projects contains project %}
        <li><a href="{{ post.url }}">{{ post.title }}</a></li>
      {% endif %}
    {% endfor %}
  </ul>
{% endfor %}
