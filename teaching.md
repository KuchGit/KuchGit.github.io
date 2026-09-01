---
layout: page
title: Enseignement
description: Supports pédagogiques et activités d'enseignement.
permalink: /teaching/
---

<section class="page-section">
  <h1 class="section-title">Enseignement</h1>

  {% assign has_materials = site.data.courses | where_exp: "c", "c.materials.size > 0" %}
  {% if has_materials.size > 0 %}
  <h2 class="pub-section-title">Supports pédagogiques</h2>
  <div class="materials-grid">
    {% for course in site.data.courses %}
      {% if course.materials %}
        {% for mat in course.materials %}
        <a href="{{ mat.url }}" class="material-card" target="_blank" rel="noopener">
          <div class="material-label">{{ mat.label }}</div>
          <div class="material-course">{{ course.title }}</div>
          {% if mat.type %}<span class="tag">{{ mat.type }}</span>{% endif %}
        </a>
        {% endfor %}
      {% endif %}
    {% endfor %}
  </div>
  {% endif %}

  <h2 class="pub-section-title" style="margin-top:2.5rem;">Activités d'enseignement</h2>
  <ul class="course-list">
    {% assign courses_sorted = site.data.courses | sort: "year" | reverse %}
    {% for course in courses_sorted %}
    <li class="course-item">
      <div class="course-title">
        {% if course.url %}<a href="{{ course.url }}" target="_blank" rel="noopener">{{ course.title }}</a>
        {% else %}{{ course.title }}{% endif %}
      </div>
      <div class="course-meta">
        {{ course.level }}{% if course.institution %} &middot; {{ course.institution }}{% endif %}
        {% if course.hours %} &middot; {{ course.hours }}h{% endif %}
        {% if course.year %} &middot; {{ course.year }}{% endif %}
      </div>
      {% if course.description %}
      <p class="course-desc">{{ course.description }}</p>
      {% endif %}
      <div class="pub-links">
        {% if course.slides %}<a class="pub-link" href="{{ course.slides }}">Slides</a>{% endif %}
        {% if course.notes %}<a class="pub-link" href="{{ course.notes }}">Notes de cours</a>{% endif %}
        {% if course.code %}<a class="pub-link" href="{{ course.code }}">Code</a>{% endif %}
        {% if course.video %}<a class="pub-link" href="{{ course.video }}">Vidéo</a>{% endif %}
      </div>
    </li>
    {% endfor %}
  </ul>
</section>