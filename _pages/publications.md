----
title: "Publications"
permalink: /publications/
layout: archive
author_profile: true
entries_layout: list
---

{% include base_path %}

{%- comment -%} Rango: del año actual hacia atrás 4 (p. ej., 2025 → 2021–2025) {%- endcomment -%}
{% assign current_year = site.time | date: "%Y" | plus: 0 %}
{% assign cutoff_year  = current_year | minus: 4 %}

{%- comment -%} Colección, visibles y solo últimos 5 años {%- endcomment -%}
{% assign pubs_all    = site.publications | where_exp:"p","p.published != false" %}
{% assign pubs_recent = pubs_all | where_exp:"p","p.year >= cutoff_year" %}

{%- comment -%} Destacados primero, todo por fecha desc {%- endcomment -%}
{% assign pubs_selected = pubs_recent | where:"selected", true | sort:"date" | reverse %}
{% assign pubs_other    = pubs_recent | where_exp:"p","p.selected != true" | sort:"date" | reverse %}

{%- if pubs_selected != empty -%}
<h2>Highlighted (last 5 years)</h2>
{% for post in pubs_selected %}
  {% include archive-single.html %}
{% endfor %}
<hr/>
{%- endif -%}

{%- comment -%} Agrupar por año (orden de grupos: desc); dentro ya vienen por date desc {%- endcomment -%}
{% assign groups = pubs_other | group_by:"year" | sort:"name" | reverse %}
{% for g in groups %}
  {% if g.name %}
  <h2 id="y{{ g.name }}">{{ g.name }}</h2>
    {% for post in g.items %}
      {% include archive-single.html %}
    {% endfor %}
  {% endif %}
{% endfor %}
