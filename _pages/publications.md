---
layout: archive
title: "Research"
permalink: /publications/
author_profile: true
---

<p class="research-intro">My research spans international macroeconomics, econometric theory, and data-driven methods for learning economic dependence. KIEP titles link to the institute's official publication pages.</p>

{% if author.googlescholar %}
  <p>You can also find my articles on <a href="{{ author.googlescholar }}">Google Scholar</a>.</p>
{% endif %}

<nav class="research-jump" aria-label="Research sections">
  <a href="#kiep-publications">KIEP Publications</a>
  <a href="#selected-research">Selected Research</a>
  <a href="#working-papers">Working Papers</a>
  <a href="#presentations">Presentations &amp; Seminars</a>
</nav>

<section class="research-section" aria-labelledby="kiep-publications">
<h2 id="kiep-publications">KIEP Publications</h2>
{% for post in site.publications reversed %}
  {% if post.category == 'kiep_publication' %}
    {% include archive-single.html compact_abstract=true %}
  {% endif %}
{% endfor %}
</section>

<section class="research-section" aria-labelledby="selected-research">
<h2 id="selected-research">Selected Research</h2>
{% for post in site.publications reversed %}
  {% if post.category == 'jmp' %}
    {% include archive-single.html compact_abstract=true %}
  {% endif %}
{% endfor %}
</section>

<section class="research-section" aria-labelledby="working-papers">
<h2 id="working-papers">Working Papers</h2>
{% for post in site.publications reversed %}
  {% if post.category == 'working_paper' %}
    {% include archive-single.html compact_abstract=true %}
  {% endif %}
{% endfor %}
</section>

<section class="research-section" aria-labelledby="presentations">
<h2 id="presentations">Presentations &amp; Seminars</h2>
{% assign presentations = site.data.presentations | sort: "date" | reverse %}
{% assign presentation_years = presentations | group_by_exp: "item", "item.date | date: '%Y'" %}
{% for year in presentation_years %}
<div class="presentation-year">
  <h3 class="presentation-year__heading">{{ year.name }}</h3>
  <ol class="presentation-list">
    {% for presentation in year.items %}
    <li>
      <article class="presentation" id="{{ presentation.id }}">
        <time class="presentation__date" datetime="{{ presentation.date }}">{{ presentation.date | date: "%B %-d" }}</time>
        <div class="presentation__content">
          <h4 class="presentation__title">{{ presentation.title }}</h4>
          <p class="presentation__event">{{ presentation.event }} · {{ presentation.location }}</p>
          <p class="presentation__details">{{ presentation.session }}<br>{{ presentation.venue }}</p>
          <a class="presentation__program" href="{{ presentation.program_url }}">Conference program <span aria-hidden="true">&nearr;</span><span class="sr-only"> — {{ presentation.event }}</span></a>
          {% if presentation.program_title %}
          <p class="presentation__note">The program lists the earlier title <em>{{ presentation.program_title }}</em>.</p>
          {% endif %}
        </div>
      </article>
    </li>
    {% endfor %}
  </ol>
</div>
{% endfor %}
</section>
