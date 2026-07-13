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
