---
layout: archive
title: "Research"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

<h2>KIEP Publications</h2>
<p>Titles below link directly to the official publication pages at the Korea Institute for International Economic Policy (KIEP).</p>
{% for post in site.publications reversed %}
  {% if post.category == 'kiep_publication' %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}

<br>

<h2>JMP</h2>
{% for post in site.publications reversed %}
  {% if post.category == 'jmp' %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}

<br>

<h2>Working Papers</h2>
{% for post in site.publications reversed %}
  {% if post.category == 'working_paper' %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}
