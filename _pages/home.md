---
layout: single
title: <span style="color:orange">Home</span>
author_profile: true
permalink: /docs/home/
header:
  overlay_color: "#000"
  overlay_filter: "0.5"
  overlay_image: /assets/images/sfondo.JPG
#  actions:
    #- label: "Learn More"
      #url: "/terms/"
  #caption: "Photo credit: [**Unsplash**](https://unsplash.com)"
#excerpt: <small>**<span style="color:orange">FALCON</span>** is a FEM code written in Fortran90 used to study large-scale geodynamics system, such as continental rifting and subductions. <a href="/assets/files/FALCON_Description.pdf" target="_blank"><span style="color:lightblue">Here</span></a> you can download the .pdf file with the complete description of all the fetures implemented in the code and all the benchmarks performed. The Gihub repository of this project can be found <a href="https://github.com/aleregorda/Code_description" target="_blank"><span style="color:lightblue">here</span></a> and you can download the .zip file containing all of the files at this <a href="https://github.com/aleregorda/Code_description/archive/refs/heads/main.zip" target="_blank"><span style="color:lightblue">link</span></a>.</small>
---

# Work in progress...

###### This is what happens if you stop watching Netflix

<!--- {{ content }}

<h3 class="archive__subtitle">{{ site.data.ui-text[site.locale].recent_posts | default: "This is what happens if you stop watching Netflix" }}</h3> -->

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