---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
* B.S. in Biology, BUAP, 2011
* M.S. in Systematics, INECOL A.C., 2015
* Ph.D in Evolution, UNAM, 2021 (expected)
  
Skills
======
* Molecular laboratory
  * DNA extraction and PCR amplification
  * Illumina library preparation and analysis
  * Fluorescence microscopy sample preparation and visualization
  
* Informatics
  * Command line
  * R Programming 
  * Markdown
  * Version control (Git)
  
* Field biology
  * Plant collection and identification
  * Pollination biology experimentation
  
Publications
======
  <ul>{% for post in site.publications %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>  

Teaching
======
  <ul>{% for post in site.teaching %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>  
  
Talks
======
  <ul>{% for post in site.talks %}
    {% include archive-single-talk-cv.html %}
  {% endfor %}</ul>
