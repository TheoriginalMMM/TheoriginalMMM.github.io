---
layout: single
title: "Projects"
permalink: /projects/
author_profile: true
---

The projects below combine doctoral research, industrial R&D and open-source academic work. Confidential industrial results are described without publishing restricted material.

<div class="portfolio-grid portfolio-grid--page">
{% assign ordered_projects = site.projects | sort: "order" %}
{% for project in ordered_projects %}
  <article class="portfolio-card">
    {% if project.teaser %}
    <a class="portfolio-card__media" href="{{ project.url | relative_url }}">
      <img src="{{ project.teaser | relative_url }}" alt="Illustration for {{ project.title }}" loading="lazy">
    </a>
    {% endif %}
    <p class="project-domain">{{ project.domain }}</p>
    <h2><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h2>
    <p>{{ project.excerpt }}</p>
    <p class="project-stack">{{ project.stack }}</p>
    <a class="project-link" href="{{ project.url | relative_url }}">View project →</a>
  </article>
{% endfor %}
</div>

Additional public code is available on [GitHub](https://github.com/TheoriginalMMM?tab=repositories). Selected technical reports can be shared on request when their dissemination is permitted.

