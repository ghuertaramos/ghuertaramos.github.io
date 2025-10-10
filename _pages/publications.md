---
title: "Publications"
permalink: /publications/
layout: archive
author_profile: true
entries_layout: list
---

{% include base_path %}

{%- assign current_year = site.time | date: "%Y" | plus: 0 -%}
{%- assign cutoff_year  = current_year | minus: 4 -%}

{%- comment -%}
Order everything by date (newest first), then group by year.
We'll filter groups < cutoff_year and print selected first within each year.
No where_exp needed (works on GH Pages).
{%- endcomment -%}
{% assign pubs_sorted = site.publications | sort:"date" | reverse %}
{% assign groups = pubs_sorted | group_by:"year" | sort:"name" | reverse %}

{%- assign any_printed = false -%}
{% for g in groups %}
  {% assign y = g.name | plus: 0 %}
  {% if y >= cutoff_year %}
    {% assign any_printed = true %}
    <h2 id="y{{ g.name }}">{{ g.name }}</h2>

    {# highlighted first #}
    {% for post in g.items %}
      {% if post.selected %}
        {% include archive-single.html %}
      {% endif %}
    {% endfor %}

    {# then the rest (already date-desc from pubs_sorted) #}
    {% for post in g.items %}
      {% unless post.selected %}
        {% include archive-single.html %}
      {% endunless %}
    {% endfor %}
  {% endif %}
{% endfor %}

{% unless any_printed %}
<p><em>No publications in the last 5 years. Ensure each item has <code>year: YYYY</code> and <code>date: YYYY-MM-DD</code>.</em></p>
{% endunless %}

{%- if pubs_recent == empty -%}
<p><em>No publications in the last 5 years. Check that each file has <code>year: YYYY</code> and a valid <code>date:</code>.</em></p>
{%- endif -%}

