---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

{% include base_path %}

<div class="project-grid">
  {% assign projects = site.projects | sort: "weight" %}
  {% for project in projects %}
    <a class="project-card" href="{{ project.url | relative_url }}">
      {% if project.logo %}
        <img src="{{ project.logo | relative_url }}" alt="{{ project.title }} logo" class="project-logo">
      {% endif %}
      <h2>{{ project.title }}</h2>
      <p>{{ project.excerpt }}</p>
    </a>
  {% endfor %}
</div>
