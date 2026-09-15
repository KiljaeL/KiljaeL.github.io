---
layout: profile
title: "Curriculum Vitae"
permalink: /cv/
description: "Academic curriculum vitae of Kiljae Lee, Statistics Ph.D. candidate at The Ohio State University."
redirect_from:
  - /resume
---

<header class="page-intro page-intro--cv">
  <div>
    <p class="eyebrow">Curriculum Vitae</p>
    <h1>Kiljae Lee</h1>
    <p>Statistics Ph.D. Candidate at The Ohio State University, working at the intersection of statistical machine learning, data-centric AI, explainable AI, LLM evaluation, and uncertainty quantification.</p>
  </div>
  <div class="cv-download">
    <span>Academic CV</span>
    <strong>Updated September 2026</strong>
    <a class="profile-button profile-button--primary" href="{{ '/files/KiljaeLee_CV.pdf' | relative_url }}">View PDF <span aria-hidden="true">↗</span></a>
  </div>
</header>

<div class="cv-layout">
  <aside class="cv-index" aria-label="CV sections">
    <span>On this page</span>
    <a href="#education">Education</a>
    <a href="#publications">Publications</a>
    <a href="#honors">Honors</a>
    <a href="#appointments">Appointments</a>
    <a href="#experience">Experience</a>
    <a href="#teaching">Teaching</a>
    <a href="#talks">Talks</a>
    <a href="#service">Service</a>
    <a href="#skills">Skills</a>
  </aside>

  <div class="cv-content">
    <section id="education" class="cv-section">
      <p class="section-kicker">Education</p>
      <h2>Academic training</h2>
      <div class="cv-entry-list">
        {% for item in site.data.profile.education %}
          <article class="cv-entry">
            <div class="cv-entry__main">
              <h3>{{ item.degree }}</h3>
              <p class="cv-entry__organization">{{ item.school }} · {{ item.location }}</p>
              {% if item.details %}<p>{{ item.details }}</p>{% endif %}
              {% if item.note %}<p>{{ item.note }}</p>{% endif %}
            </div>
            <span class="cv-entry__date">{{ item.dates }}</span>
          </article>
        {% endfor %}
      </div>
    </section>

    <section id="publications" class="cv-section">
      <p class="section-kicker">Publications</p>
      <h2>Research output</h2>
      {% for category in site.publication_category %}
        {% assign category_posts = site.publications | where: "category", category[0] | reverse %}
        {% if category_posts.size > 0 %}
          <h3 class="cv-subheading">{{ category[1].title }}</h3>
          <div class="cv-publication-list">
            {% for post in category_posts %}
              <article class="cv-publication">
                <p class="cv-publication__authors">{{ post.authors }}</p>
                <h4><a href="{{ post.paperurl | default: post.url }}">{{ post.title }}</a></h4>
                <p>{{ post.venue }}{% if post.cv_note %}. {{ post.cv_note }}{% else %}, {{ post.date | date: "%Y" }}{% endif %}</p>
              </article>
            {% endfor %}
          </div>
        {% endif %}
      {% endfor %}
    </section>

    <section id="honors" class="cv-section">
      <p class="section-kicker">Honors</p>
      <h2>Honors and fellowships</h2>
      <div class="cv-entry-list">
        {% for item in site.data.profile.honors %}
          <article class="cv-entry cv-entry--compact">
            <div class="cv-entry__main">
              <h3>{{ item.title }}</h3>
              <p class="cv-entry__organization">{{ item.organization }}</p>
              {% if item.description %}<p>{{ item.description }}</p>{% endif %}
            </div>
            <span class="cv-entry__date">{{ item.year }}</span>
          </article>
        {% endfor %}
      </div>
    </section>

    <section id="appointments" class="cv-section">
      <p class="section-kicker">Appointments</p>
      <h2>Research appointments</h2>
      <div class="cv-entry-list">
        {% for item in site.data.profile.research_appointments %}
          <article class="cv-entry">
            <div class="cv-entry__main">
              <h3>{{ item.role }}</h3>
              <p class="cv-entry__organization">{{ item.organization }} · {{ item.location }}</p>
              <p>{{ item.description }}</p>
            </div>
            <span class="cv-entry__date">{{ item.dates }}</span>
          </article>
        {% endfor %}
      </div>
    </section>

    <section id="experience" class="cv-section">
      <p class="section-kicker">Experience</p>
      <h2>Professional experience</h2>
      <div class="cv-entry-list">
        {% for item in site.data.profile.professional_experience %}
          <article class="cv-entry">
            <div class="cv-entry__main">
              <h3>{{ item.role }}</h3>
              <p class="cv-entry__organization">{{ item.organization }} · {{ item.location }}</p>
              <p>{{ item.description }}</p>
            </div>
            <span class="cv-entry__date">{{ item.dates }}</span>
          </article>
        {% endfor %}
      </div>
    </section>

    <section id="teaching" class="cv-section">
      <p class="section-kicker">Teaching</p>
      <h2>Teaching experience</h2>
      <div class="cv-entry-list">
        {% for item in site.data.profile.teaching %}
          <article class="cv-entry">
            <div class="cv-entry__main">
              <h3>{{ item.role }}</h3>
              <p class="cv-entry__organization">{{ item.organization }}</p>
              <p>{{ item.description }}</p>
            </div>
            <span class="cv-entry__date">{{ item.dates }}</span>
          </article>
        {% endfor %}
      </div>
    </section>

    <section id="talks" class="cv-section">
      <p class="section-kicker">Talks</p>
      <h2>Invited talks</h2>
      <div class="cv-entry-list">
        {% for item in site.data.profile.talks %}
          <article class="cv-entry cv-entry--compact">
            <div class="cv-entry__main">
              <h3>{{ item.title }}</h3>
              <p class="cv-entry__organization">{{ item.venue }} · {{ item.location }}</p>
              <p>{{ item.type }}</p>
            </div>
            <span class="cv-entry__date">{{ item.date }}</span>
          </article>
        {% endfor %}
      </div>
    </section>

    <section id="service" class="cv-section">
      <p class="section-kicker">Service</p>
      <h2>Academic service and leadership</h2>
      <div class="service-block">
        <h3>Conference reviewer</h3>
        <p>{{ site.data.profile.service.reviewer }}</p>
        <h3>Leadership</h3>
        <ul>
          {% for item in site.data.profile.service.leadership %}<li>{{ item }}</li>{% endfor %}
        </ul>
      </div>
    </section>

    <section id="skills" class="cv-section">
      <p class="section-kicker">Skills</p>
      <h2>Technical skills</h2>
      <dl class="skills-list">
        {% for group in site.data.profile.skills %}
          <div><dt>{{ group.label }}</dt><dd>{{ group.items }}</dd></div>
        {% endfor %}
      </dl>
    </section>
  </div>
</div>
