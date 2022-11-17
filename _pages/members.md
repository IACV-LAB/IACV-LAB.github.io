---
layout: page
title: members
permalink: /members/
description:
nav: true
display_categories: [faculty, current, alumni]
---
<div class="projects">
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->

  <div class="container mt-5">
    {%- for project in sorted_projects -%}
      {% include members_horizontal.html %}
    {%- endfor %}
  {% endfor %}
