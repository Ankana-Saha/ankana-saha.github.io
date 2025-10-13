---
layout: page
title: research
permalink: /research/
# description: A growing collection of your cool projects.
nav: true
nav_order: 3
# display_categories: [work, fun]
horizontal: false
---
<style>
.projects .card-text,
.projects .card-title {
  font-size: 1.3rem;
  font-weight: 800;
}
</style>

Most of my current work focuses on the nominal domain, investigating the semantics and pragmatics of referential expressions, anaphora, kind reference, the interpretation of bare nouns in classifier languages, and plurality. I’m also particularly interested in using insights from linguistics and experimental data to better inform our understanding of language models’ capabilities and limitations. 

Below are some of my ongoing research projects.

<!-- I'm a final year PhD candidate in the Department of Linguistics at Harvard University, and my dissertation is advised by Dr Gennaro Chierchia (co-chair) and Dr Kathryn Davidson (co-chair) and Dr Veneeta Dayal. My research lies at the intersection of semantics, pragmatics, and syntax, and asks how utterances acquire their meanings, and how those meanings interact with linguistic structure and discourse context. I approach these questions using tools from formal logic and mathematics, together with experimental methods and fieldwork. -->

<!-- Much of my work centers on the nominal domain, including the semantics of bare nouns in languages with and without determiners, kind reference, and the semantics and pragmatics of referring expressions such as definites, demonstratives, and anaphora. I explore these questions through a combination of experimentation, fieldwork, and formal theory.

A central theme of my dissertation is how typological differences across languages and modalities shape and constrain anaphoric reference in definites and demonstratives. I study how spoken languages rely on morphosyntactic strategies, how ASL partitions the anaphoric domain through loci and spatial structure, and how large language models (LLMs) approximate (or diverge from) human patterns. And in particular, I am interested in understanding the pragmatic constraints that cut across all of these systems and modalities.  This comparative perspective, spanning humans vs. machines and spoken vs. visual-gestural modalities aims to identify which constraints on anaphora are modality or system specific and which reflect a shared logical core, contributing to a more precise theory of definiteness, anaphoricity, and meaning. -->

<!-- I am an affiliate at the [Meaning & Modality Lab](https://meaningandmodality.github.io/site) and the The Institute for Quantitative Social Science at Harvard.

Before coming to Harvard, I completed my undergraduate studies in Physics, Chemistry, and Mathematics at Christ University (Bangalore, India) and my Master's degree in Linguistics at The English and Foreign Languages University (Hyderabad, India). -->

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-4">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-4">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
