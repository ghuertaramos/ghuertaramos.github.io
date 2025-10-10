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

{%- comment -%} Sort all pubs by date (newest first) {%- endcomment -%}
{%- assign pubs_sorted = site.publications | sort:"date" | reverse -%}

{%- comment -%} Group by year and show only last 5 years {%- endcomment -%}
{%- assign groups = pubs_sorted | group_by:"year" | sort:"name" | reverse -%}

{%- assign printed_any = false -%}
{%- for g in groups -%}
  {%- assign y = g.name | plus: 0 -%}
  {%- if y >= cutoff_year -%}
    {%- assign printed_any = true -%}
<h2 id="y{{ y }}">{{ y }}</h2>
{%- comment -%} highlighted first {%- endcomment -%}
{%- for post in g.items -%}{% if post.selected %}{% include archive-single.html %}{% endif %}{%- endfor -%}
{%- comment -%} then the rest {%- endcomment -%}
{%- for post in g.items -%}{% unless post.selected %}{% include archive-single.html %}{% endunless %}{%- endfor -%}
  {%- endif -%}
{%- endfor -%}

{%- unless printed_any -%}
<p><em>No publications in the last 5 years. Ensure each item has <code>year: YYYY</code> and <code>date: YYYY-MM-DD</code>.</em></p>
{%- endunless -%}

