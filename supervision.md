---
layout: default
title: "Encadrement"
permalink: /supervision/
---

<section class="page-section">
  <h1 class="section-title">Encadrement</h1>

  {% assign supervised = site.data.supervision | sort: "year" | reverse %}

  <table class="supervision-table">
    <thead>
      <tr>
        <th>Année</th>
        <th>Étudiant·e</th>
        <th>Niveau</th>
        <th>Sujet</th>
        <th>Établissement</th>
        <th>Rapport</th>
      </tr>
    </thead>
    <tbody>
      {% for s in supervised %}
      <tr>
        <td>{{ s.year }}</td>
        <td>{{ s.name }}</td>
        <td><span class="tag">{{ s.level }}</span></td>
        <td>
          {{ s.topic }}
          {% if s.co_supervisor %}
            <span class="co-sup">(co-enc. {{ s.co_supervisor }})</span>
          {% endif %}
        </td>
        <td>{{ s.institution }}</td>
        <td>
          {% if s.report %}
            <a href="{{ s.report | relative_url }}" class="btn-small" target="_blank">PDF</a>
          {% else %}
            —
          {% endif %}
        </td>
      </tr>
      {% endfor %}
    </tbody>
  </table>
</section>
