---
layout: page
title: Projets
description: Projets de recherche, logiciels et collaborations en cours ou achevés.
permalink: /projects/
---

{% assign active   = site.projects | where: "status", "actif" %}
{% assign finished = site.projects | where: "status", "terminé" %}

{% if active.size > 0 %}
## En cours

<ul class="project-list">
  {% for project in active %}
  <li class="project-item">
    <div class="project-title">
      <a href="{{ project.url | relative_url }}">{{ project.title }}</a>
    </div>
    {% if project.funding %}
    <div style="font-size:0.78rem;color:#888;margin:0.2rem 0;">{{ project.funding }}</div>
    {% endif %}
    <p class="project-desc">{{ project.description }}</p>
    <div class="project-tags">
      {% for tag in project.tags %}
      <span class="project-tag">{{ tag }}</span>
      {% endfor %}
    </div>
  </li>
  {% endfor %}
</ul>
{% endif %}

{% if finished.size > 0 %}
## Terminés

<ul class="project-list">
  {% for project in finished %}
  <li class="project-item">
    <div class="project-title">
      <a href="{{ project.url | relative_url }}">{{ project.title }}</a>
    </div>
    <p class="project-desc">{{ project.description }}</p>
    <div class="project-tags">
      {% for tag in project.tags %}
      <span class="project-tag">{{ tag }}</span>
      {% endfor %}
    </div>
  </li>
  {% endfor %}
</ul>
{% endif %}
