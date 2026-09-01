---
layout: page
title: Publications
description: Articles, chapitres d'ouvrages et actes de conférences.
permalink: /publications/
---

{% assign pubs_sorted = site.data.publications | sort: "year" | reverse %}
{% assign chapters = site.data.publications | where: "type", "book_chapter" | sort: "year" | reverse %}
{% assign conferences = site.data.publications | where: "type", "conference" | sort: "year" | reverse %}

<section class="pub-section">
<h2 class="pub-section-title">Revues scientifiques à comité de lecture</h2>
<ul class="pub-list">
  {% for pub in pubs_sorted %}
  {% unless pub.type == "book_chapter" or pub.type == "conference" %}
  <li class="pub-item">
    <div class="pub-body">
      <div class="pub-title">{{ pub.title }}</div>
      <div class="pub-authors">{{ pub.authors }}</div>
      <div class="pub-venue">{{ pub.venue }}{% if pub.year %} ({{ pub.year }}){% endif %}</div>
      <div class="pub-links">
        {% if pub.pdf %}<a class="pub-link" href="{{ pub.pdf }}">PDF</a>{% endif %}
        {% if pub.doi %}<a class="pub-link" href="{{ pub.doi }}" target="_blank" rel="noopener">DOI</a>{% endif %}
        {% if pub.arxiv %}<a class="pub-link" href="{{ pub.arxiv }}">arXiv</a>{% endif %}
        {% if pub.code %}<a class="pub-link" href="{{ pub.code }}">Code</a>{% endif %}
        {% if pub.slides %}<a class="pub-link" href="{{ pub.slides }}">Slides</a>{% endif %}
        {% if pub.poster %}<a class="pub-link" href="{{ pub.poster }}">Poster</a>{% endif %}
      </div>
    </div>
  </li>
  {% endunless %}
  {% endfor %}
</ul>
</section>

<section class="pub-section">
<h2 class="pub-section-title">Chapitres de livre</h2>
<ul class="pub-list">
  {% for pub in chapters %}
  <li class="pub-item">
    <div class="pub-body">
      <div class="pub-title">{{ pub.title }}</div>
      <div class="pub-authors">{{ pub.authors }}</div>
      <div class="pub-venue">{{ pub.venue }}{% if pub.year %} ({{ pub.year }}){% endif %}</div>
      <div class="pub-links">
        {% if pub.pdf %}<a class="pub-link" href="{{ pub.pdf }}">PDF</a>{% endif %}
        {% if pub.doi %}<a class="pub-link" href="{{ pub.doi }}" target="_blank" rel="noopener">DOI</a>{% endif %}
      </div>
    </div>
  </li>
  {% endfor %}
</ul>
</section>

<section class="pub-section">
<h2 class="pub-section-title">Conférences avec évaluation par les pairs</h2>
<ul class="pub-list">
  {% for pub in conferences %}
  <li class="pub-item">
    <div class="pub-body">
      <div class="pub-title">{{ pub.title }}</div>
      <div class="pub-authors">{{ pub.authors }}</div>
      <div class="pub-venue">{{ pub.venue }}{% if pub.year %} ({{ pub.year }}){% endif %}</div>
      <div class="pub-links">
        {% if pub.pdf %}<a class="pub-link" href="{{ pub.pdf }}">PDF</a>{% endif %}
        {% if pub.doi %}<a class="pub-link" href="{{ pub.doi }}" target="_blank" rel="noopener">DOI</a>{% endif %}
        {% if pub.slides %}<a class="pub-link" href="{{ pub.slides }}">Slides</a>{% endif %}
        {% if pub.poster %}<a class="pub-link" href="{{ pub.poster }}">Poster</a>{% endif %}
      </div>
    </div>
  </li>
  {% endfor %}
</ul>
</section>