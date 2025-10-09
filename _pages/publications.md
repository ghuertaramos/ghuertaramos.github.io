---
title: "Publications"
permalink: /publications/
layout: archive
author_profile: true
entries_layout: list
---

{% include base_path %}

{%- comment -%} Opcional: enlace a Google Scholar si está definido en _config.yml -> author.googlescholar {%- endcomment -%}
{% if author.googlescholar %}
<p>You can also find my articles on <u><a href="{{ author.googlescholar }}">my Google Scholar profile</a></u>.</p>
{% endif %}

{%- comment -%} 1) Tomar todas las publicaciones visibles {%- endcomment -%}
{% assign pubs_all = site.publications | where_exp: "p", "p.published != false" %}

{%- comment -%} 2) Pinned primero (selected: true), luego el resto {%- endcomment -%}
{% assign pubs_selected = pubs_all | where: "selected", true | sort: "year" | reverse %}
{% assign pubs_other = pubs_all | where_exp: "p","p.selected != true" | sort: "year" | reverse %}

{%- if pubs_all == empty -%}
<p><em>No publications yet.</em></p>
{%- endif -%}

{%- if pubs_selected != empty -%}
<h2>Highlighted</h2>
{% for post in pubs_selected %}
  {% include archive-single.html %}
{% endfor %}
<hr/>
{%- endif -%}

{%- comment -%} 3) Listado por año (descendente), dentro de cada año orden por date desc {%- endcomment -%}
{% assign pubs_sorted = pubs_other | sort: "date" | reverse %}
{% assign groups = pubs_sorted | group_by: "year" %}

{% for g in groups %}
  {% if g.name %}
  <h2 id="y{{ g.name }}">{{ g.name }}</h2>
    {% for post in g.items %}
      {% include archive-single.html %}
    {% endfor %}
  {% endif %}
{% endfor %}
