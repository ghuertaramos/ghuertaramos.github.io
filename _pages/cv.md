---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

<h1>Publications</h1>
{% assign pubs = site.publications | sort:"date" | reverse %}

<ul class="bibliography">
{% for post in pubs %}
  <li>
    {{ post.citation | default: post.title }}
  </li>
{% endfor %}
</ul>

  
Education
======
* Ph.D in Evolutionary Biology, UNAM (Soon)
* M.S. in Systematics, INECOL A.C.
* B.S. in Biology, BUAP

Mentoring
======
* B.S. — **Karen Daneb Pérez Arroyo** (2024). Thesis: “Pollinator dependence and autonomous reproduction along the elevation gradient of Nevado de Colima”.  Co-advised with Silvana Martén-Rodríguez, Ph.D
  [TESIUNAM](https://hdl.handle.net/20.500.14330/TES01000864396){:target="_blank" rel="noopener"}

Teaching
======
**ENES–Morelia, UNAM — Ecology B.Sc. program**

**Course Instructor**
- Field Ecology II (2025)
- Forest Ecology (2025)
- Systematics (2023, 2025)
- Biodiversity V: Plant Biology (2023)

**Teaching Assistant**
- Functional Ecology: Selected Topics (2024)
- Field Ecology II (2023, 2024)
- Systematics (2019, 2024)
- Biodiversity V: Plant Biology (2018, 2019, 2020, 2024, 2025)
  
Skills
======
* **Molecular laboratory**
  * DNA extraction and PCR amplification
  * Illumina library preparation and analysis
  * Fluorescence microscopy sample preparation and visualization
* **Informatics**
  * Command line
  * R programming
  * Markdown
  * Version control (Git)
  * High-performance computing
* **Field biology**
  * Plant collection and identification
  * Experimental pollination biology

Courses and Workshops
======
* Molecular Dating — INECOL (Xalapa, Mexico)
* Statistics in R — INECOL (Xalapa, Mexico)
* Pollination Evolutionary Ecology — INECOL (Xalapa, Mexico)
* Bioinformatics for Landscape Genomics — ENES-Morelia
* Multivariate Analysis in R — IIES (Morelia, Mexico)
* Introduction to bioinformatics and reproducible research for genetic analysis — Instituto de Ecología (Mexico City, Mexico)
* Introduction to the analysis of microbial gene sequences and metagenomics — IIES (Morelia, Mexico)
* Using Geiger, Phytools, and other tools for macroevolution on phylogenies — Transmitting Science (Barcelona, Spain)

 
Scientific societies
======
* [SORTEE — Society for Open, Reliable, and Transparent Ecology and Evolution](https://sortee.org/){:target="_blank" rel="noopener"}
* [Red Mexicana de Biología Evolutiva (REMBE)](https://mexevol.com/){:target="_blank" rel="noopener"}
* [North American Pollinator Protection Campaign (NAPPC)](https://www.pollinator.org/){:target="_blank" rel="noopener"} — Climate Change Task Force
* [The Convolvulaceae Network](https://sites.google.com/view/theconvolvulaceaenetwork){:target="_blank" rel="noopener"}
* [Convolvulaceae Taxonomic Expert Network (TEN)](https://about.worldfloraonline.org/tens/convolvulaceae){:target="_blank" rel="noopener"}

