---
layout: profile
permalink: /
title: "Kiljae Lee's Website"
description: "Statistics Ph.D. candidate at The Ohio State University working on data-centric AI, explainable AI, LLM evaluation, and uncertainty quantification."
redirect_from:
  - /about/
  - /about.html
---

<section class="home-hero" aria-labelledby="home-title">
  <div class="home-hero__copy">
    <div class="home-hero__credentials">
      <p class="eyebrow">Statistics Ph.D. Candidate · The Ohio State University</p>
      <p class="home-hero__graduation">Expected to graduate in 2027 Summer</p>
    </div>
    <h1 id="home-title">Statistical foundations for<br>reliable and accountable AI</h1>
    <p class="home-hero__lead">{{ site.data.profile.summary }}</p>

    <div class="home-hero__actions">
      <a class="profile-button profile-button--primary" href="{{ '/publications/' | relative_url }}">Explore my research</a>
      <a class="profile-button profile-button--secondary" href="{{ '/files/KiljaeLee_CV.pdf' | relative_url }}">View CV</a>
    </div>

    <ul class="profile-links" aria-label="Academic and professional profiles">
      <li><a href="mailto:{{ site.author.email }}">Email</a></li>
      <li><a href="{{ site.author.googlescholar }}" target="_blank" rel="noopener">Google Scholar</a></li>
      <li><a href="https://github.com/{{ site.author.github }}" target="_blank" rel="noopener">GitHub</a></li>
      <li><a href="https://www.linkedin.com/in/{{ site.author.linkedin }}" target="_blank" rel="noopener">LinkedIn</a></li>
    </ul>
  </div>

  <aside class="home-hero__profile" aria-label="Portrait of Kiljae Lee">
    <div class="portrait-frame">
      <img src="{{ '/images/kiljae.jpg' | relative_url }}" alt="Portrait of Kiljae Lee" width="2906" height="3310">
    </div>
  </aside>
</section>

<section class="profile-section profile-section--tinted" aria-labelledby="research-focus-title">
  <div class="section-heading">
    <div>
      <p class="section-kicker">Research focus</p>
      <h2 id="research-focus-title">Making modern AI systems more reliable</h2>
    </div>
    <p>My research studies how data, contributors, predictions, and preferences should be valued when structure and strategic behavior matter.</p>
  </div>

  <div class="focus-grid">
    {% for focus in site.data.profile.research_focus %}
      <article class="focus-card">
        <h3 class="focus-card__heading"><span class="focus-card__number">{{ forloop.index }}.</span> {{ focus.title }}</h3>
        <p>{{ focus.description }}</p>
      </article>
    {% endfor %}
  </div>
</section>

<section class="profile-section" aria-labelledby="featured-work-title">
  <div class="section-heading section-heading--compact">
    <div>
      <p class="section-kicker">Selected work</p>
      <h2 id="featured-work-title">Featured publications</h2>
    </div>
    <a class="section-link" href="{{ '/publications/' | relative_url }}">All publications <span aria-hidden="true">→</span></a>
  </div>

  {% assign featured_publications = site.publications | where: "featured", true | sort: "featured_order" %}
  <div class="publication-grid">
    {% for post in featured_publications %}
      {% include publication-card.html post=post featured=true %}
    {% endfor %}
  </div>
</section>

<section class="profile-section profile-section--tinted" aria-labelledby="recognition-title">
  <div class="section-heading">
    <div>
      <p class="section-kicker">Recognition</p>
      <h2 id="recognition-title">Recent honors and service</h2>
    </div>
    <p>Recognition for research contributions and peer review across the machine learning community.</p>
  </div>

  <div class="recognition-grid">
    {% for honor in site.data.profile.honors limit:3 %}
      <article class="recognition-card">
        <span class="recognition-card__year">{{ honor.year }}</span>
        <h3>{{ honor.title }}</h3>
        <p class="recognition-card__organization">{{ honor.organization }}</p>
        {% if honor.description %}<p>{{ honor.description }}</p>{% endif %}
      </article>
    {% endfor %}
  </div>
</section>

<section class="profile-section profile-section--split" aria-labelledby="experience-title">
  <div>
    <p class="section-kicker">Experience</p>
    <h2 id="experience-title">Research grounded in practice</h2>
    <p class="section-copy">Alongside theoretical research, I work on statistical and machine learning problems in industry and interdisciplinary consulting.</p>
  </div>
  <div class="compact-timeline">
    {% for item in site.data.profile.professional_experience %}
      <article class="compact-timeline__item">
        <div>
          <h3>{{ item.role }}</h3>
          <p>{{ item.organization }} · {{ item.location }}</p>
        </div>
        <span>{{ item.dates }}</span>
      </article>
    {% endfor %}
    {% for item in site.data.profile.research_appointments limit:1 %}
      <article class="compact-timeline__item">
        <div>
          <h3>{{ item.role }}</h3>
          <p>{{ item.organization }} · {{ item.location }}</p>
        </div>
        <span>{{ item.dates }}</span>
      </article>
    {% endfor %}
  </div>
</section>
