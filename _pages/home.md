---
layout: single
classes: wide
title: <span style="color:orange;font-size:40px">Alessandro Regorda</span><br><span style="color:gray;font-size:30px">Postdoctoral researcher</span>
author_profile: true
permalink: /docs/home/
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/sfondo.JPG

---

# <span style="color:orange;font-size:24px">About me</span>

<small>I was awarded a Ph.D. in Earth Sciences in co-tutorship between the University of Milan (Italy) and the University of Nice-Sophia Antipolis (France), with a thesis that involved thermo-mechanical modelling applied to ocean/continent subduction systems in comparison with natural P-T data related to Variscan metamorphism in the Alps and in the French Massif Central.
During my Post-doc at the University of Milan I focused my research on the analysis of metamorphic facies and deformation fabrics within subduction complexes by means of the numerical code *SubMar*. I also developed and fully benchmarked a brand new 2D FEM code in Fortran coined <a href="/falcon/" target=_blank><span style="color:orange">FALCON</span></a> (<span style="color:orange">F</span>em <span style="color:orange">AL</span>gorithm for <span style="color:orange">CO</span>mputational a<span style="color:orange">N</span>alisys) characterised by a non-linear visco-plastic behaviour, which allowed me to publish a paper on the behaviour of extensional settings on Venus and, more recently, to study in detail the thermo-mechanical effects of the subduction of micro-continents in ocean-continent subduction systems.</small>

{% if paginator %}
  {% assign posts = paginator.posts %}
{% else %}
  {% assign posts = site.posts %}
{% endif %}

{% assign entries_layout = page.entries_layout | default: 'list' %}
<div class="entries-{{ entries_layout }}">
  {% for post in posts %}
    {% include archive-single.html type=entries_layout %}
  {% endfor %}
</div>

{% include paginator.html %}