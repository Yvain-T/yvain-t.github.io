---
layout: archive
title: "Projects"
permalink: /projects/
---


{% assign sorted_projects = site.projects | sort: "index" %}

{% for project in sorted_projects %}
  <div>
    <h2><a href="{{ project.url }}">{{ project.title }}</a></h2>
    <img src="{{ project.image }}" alt="{{ project.title }}" style="max-width: 200px;">
    <p>{{ project.abstract }}</p>
  </div>
{% endfor %}
