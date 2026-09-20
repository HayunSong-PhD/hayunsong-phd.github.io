---
permalink: /
title: "About"
excerpt: "I am an econometrician at KIEP, focusing on econometric theory and Bayesian methods with applications to international macroeconomics and finance."
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---
<div class="home-intro">
  <p class="home-intro__eyebrow">Associate Research Fellow · KIEP</p>
  <p class="home-intro__lead">Econometrician.</p>
  <p>
    I work in the International Macroeconomics Team, Department of International Macroeconomics and Finance, at the <a href="https://www.kiep.go.kr/">Korea Institute for International Economic Policy (KIEP)</a>. My research focuses on econometric theory and Bayesian methods, with applications to international macroeconomics and finance.
  </p>
  <p>
    I received my Ph.D. in Economics from the University of Southern California in 2024 under the supervision of <a href="http://www.econ.cam.ac.uk/people/emeritus/mhp1">M. Hashem Pesaran</a>.
  </p>

  <div class="home-actions" aria-label="Primary links">
    <a class="home-action home-action--primary" href="/publications/">View research</a>
    <a class="home-action" href="/cv/">CV: Short &amp; Long</a>
    <a class="home-action" href="https://www.kiep.go.kr/expertsView.es?mid=a20108030000&amp;staff_seq=390">KIEP Profile</a>
  </div>
</div>

{% assign recent_presentations = site.data.presentations | sort: "date" | reverse %}
{% if recent_presentations.size > 0 %}
<section class="home-activity" aria-labelledby="recent-activity">
  <h2 id="recent-activity">Recent Activity</h2>
  {% for presentation in recent_presentations limit: 1 %}
  <p>
    <time datetime="{{ presentation.date }}">{{ presentation.date | date: "%B %Y" }}</time>
    <span>Presented <em>{{ presentation.title }}</em> at the {{ presentation.event }}.</span>
    <a href="/publications/#{{ presentation.id }}">Presentation details <span aria-hidden="true">&rarr;</span></a>
  </p>
  {% endfor %}
</section>
{% endif %}

<section class="home-section" aria-labelledby="research-interests">
  <h2 id="research-interests" class="home-section__title">Research Interests</h2>
  <ul class="home-topics">
    <li>Econometric theory</li>
    <li>Bayesian econometrics</li>
    <li>Machine learning</li>
    <li>Structural learning</li>
    <li>Conditional dependence</li>
    <li>International macroeconomics</li>
  </ul>
</section>

<section class="home-section" aria-labelledby="recent-publications">
  <div class="home-section__heading">
    <h2 id="recent-publications" class="home-section__title">Recent KIEP Publications</h2>
    <a href="/publications/#kiep-publications">View all research</a>
  </div>

  {% assign recent_kiep = site.publications | where: "category", "kiep_publication" | sort: "date" | reverse %}
  <div class="home-publications">
    {% for post in recent_kiep limit: 3 %}
      <article class="home-publication">
        <p class="home-publication__date">{{ post.date | date: "%B %Y" }}</p>
        <h3><a href="{{ post.external_url }}">{{ post.title }}</a></h3>
        <p class="home-publication__venue">{{ post.venue }}</p>
      </article>
    {% endfor %}
  </div>
</section>

<nav class="home-secondary-links" aria-label="Additional links">
  <a href="/portfolio/">Applied data projects</a>
  <a href="https://www.aieconlab.com/">AIEconLab blog <span aria-hidden="true">↗</span></a>
  <a href="/files/cv_hayunSong_long.pdf">Long CV with research abstracts</a>
  <a href="mailto:hayunsong@kiep.go.kr">Email</a>
</nav>
