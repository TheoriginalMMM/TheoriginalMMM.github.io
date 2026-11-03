---
layout: splash
title: "Mohamed El Mehdi Makhlouf"
permalink: /
author_profile: false
header:
  overlay_color: "#0b2d45"
  actions:
    - label: "Explore my work"
      url: "/projects/"
    - label: "Download CV"
      url: "/assets/documents/CV_Mohamed_El_Mehdi_Makhlouf_EN.pdf"
    - label: "mehdi.makhlouf.pro@gmail.com"
      url: "mailto:mehdi.makhlouf.pro@gmail.com"
excerpt: >
  **AI/ML & Data R&D Engineer · PhD Candidate**  
  Self-supervised learning, scientific data and reproducible machine-learning systems.
intro:
  - excerpt: >
      I work across the complete applied-research cycle: scientific framing, data modelling,
      algorithm design, comparative experimentation, software delivery and communication.
      My experience spans telecommunications, energy and healthcare.
feature_row:
  - title: "Machine learning"
    excerpt: "Self-supervised, robust and transfer learning; deep learning, representation learning and machine unlearning."
  - title: "Signals & data"
    excerpt: "Wireless CSI, time series, computer vision, EEG, statistical analysis and scientific visualisation."
  - title: "Scientific engineering"
    excerpt: "Python/PyTorch pipelines, APIs, simulators, HDF5, Git, Linux and national HPC infrastructures."
feature_row_2:
  - title: "Research portfolio"
    excerpt: "Publications, selected open-source implementations and research deliverables."
    url: "/projects/"
    btn_label: "View projects"
    btn_class: "btn--primary"
  - title: "Available from March 2027"
    excerpt: "Open to R&D, AI/ML and Data opportunities in France and internationally."
    url: "/experience/"
    btn_label: "View experience"
    btn_class: "btn--primary"
---

{% include feature_row id="intro" type="center" %}

<section class="profile-intro">
  <img src="{{ '/assets/images/mohamed-makhlouf.jpg' | relative_url }}" alt="Portrait of Mohamed El Mehdi Makhlouf">
  <div>
    <p class="eyebrow">Research · Engineering · Collaboration</p>
    <h2>From scientific questions to usable, documented results</h2>
    <p>
      I am completing a PhD in computer science at Inria Lyon and INSA Lyon, where I develop
      self-supervised representations of radio measurements for channel charting, localisation,
      prediction and RIS control. I also bring applied R&D experience from TotalEnergies,
      ResilEyes Therapeutics and the Marc Jeannerod Institute of Cognitive Science.
    </p>
    <p>
      My work combines machine learning, signal processing, statistical modelling, reproducible
      experimentation and technical communication with scientific and industrial partners.
    </p>
    <div class="profile-actions">
      <a class="btn btn--primary" href="{{ '/experience/' | relative_url }}">Professional experience</a>
      <a class="btn btn--inverse" href="{{ '/publications/' | relative_url }}">Publications</a>
      <a class="btn btn--inverse" href="{{ '/talks/' | relative_url }}">Talks &amp; teaching</a>
    </div>
  </div>
</section>

<div class="section-heading">
  <p class="eyebrow">At a glance</p>
  <h2>Research profile and recognition</h2>
</div>

<div class="highlight-grid">
  <article class="highlight-card">
    <strong>2 peer-reviewed papers</strong>
    <span>EuCNC &amp; 6G Summit and Asilomar 2025, with another first-author manuscript in preparation.</span>
  </article>
  <article class="highlight-card">
    <strong>3 competition distinctions</strong>
    <span>1st place at the INSTINCT Summer School, 3rd place at ESIT-D2I 2026 and 5th place at Coding Battle 2023.</span>
  </article>
  <article class="highlight-card">
    <strong>3 applied domains</strong>
    <span>Telecommunications, renewable energy and healthcare, from scientific framing to documented software delivery.</span>
  </article>
</div>

{% include feature_row %}

<div class="section-heading">
  <p class="eyebrow">Selected work</p>
  <h2>Research and open-source projects</h2>
</div>

<div class="portfolio-grid">
{% assign selected_projects = site.projects | sort: "order" %}
{% for project in selected_projects limit: 6 %}
  <article class="portfolio-card">
    {% if project.teaser %}
    <a class="portfolio-card__media" href="{{ project.url | relative_url }}">
      <img src="{{ project.teaser | relative_url }}" alt="Illustration for {{ project.title }}" loading="lazy">
    </a>
    {% endif %}
    <p class="project-domain">{{ project.domain }}</p>
    <h3><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
    <p>{{ project.excerpt }}</p>
    <p class="project-stack">{{ project.stack }}</p>
    <a class="project-link" href="{{ project.url | relative_url }}">Read the case study →</a>
  </article>
{% endfor %}
</div>

<p class="centered-action"><a class="btn btn--primary" href="{{ '/projects/' | relative_url }}">Explore all projects</a></p>

{% include feature_row id="feature_row_2" %}

