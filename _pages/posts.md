---
title: "Posts"
permalink: /posts/
layout: archive
author_profile: true
---

{% include base_path %}

{%- assign posts = site.posts | sort: "date" | reverse -%}
{% for post in posts %}
  {% include archive-single.html %}
{% endfor %}
