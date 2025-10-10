---
title: "Publications"
permalink: /publications/
layout: archive
author_profile: true
entries_layout: list
---

{% include base_path %}

{%- comment -%} last 5 years (e.g., 2025 → 2021–2025) {%- endcomment -%}
{% assign current_year = site.time | date: "%Y" | plus: 0 %}
{% assign cutoff_year  = current_year | minus: 4 %}
{% assign cutoff_year_str = cutoff_year | append: "" %}

{%- comment -%} visible items only {%- endcomment -%}
{% assign pubs_all = site.publications | where_exp:"p","p.published != false" %}

{%- comment -%} keep only items that HAVE year and are >= cutoff; compare as strings to avoid type issues {%- endcomment -%}
{% assign pubs_recent = pubs_all | where_exp:"p","p.year and p.year >= cutoff_year_str" %}

{%- comment -%} order by date desc; split into highlighted and others {%- endcomment -%}
{% assign pubs_selected = pubs_recent | where:"selected", true | sort:"date" | reverse %}
{% assign pubs_other    = pubs_recent | where_exp:"p","p.selected != true" | sort:"date" | reverse %}

{%- if pubs_selected != empty -%}
<h2>Highlighted (last 5 years)</h2>
{% for post in pubs_selected %}
  {% include archive-single.html %}
{% endfor %}
<hr/>
{%- endif -%}

{%- comment -%} group others by year and show newest year first; items already sorted by date desc {%- endcomment -%}
{% assign groups = pubs_other | group_by:"year" | sort:"name" | reverse %}
{% for g in groups %}
  {% if g.name %}
  <h2 id="y{{ g.name }}">{{ g.name }}</h2>
    {% for post in g.items %}
      {% include archive-single.html %}
    {% endfor %}
  {% endif %}
{% endfor %}

{%- if pubs_recent == empty -%}
<p><em>No publications in the last 5 years. Check that each file has <code>year: YYYY</code> and a valid <code>date:</code>.</em></p>
{%- endif -%}

