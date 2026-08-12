---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
* 博士在读，控制科学与工程专业，西北工业大学 航天学院，2026.09.01 - 今
* 本科，航空航天工程专业，西北工业大学 航天学院，2022.09.01 - 2026.06.30

Research Interests
======
* 具身智能
* 肌肉骨骼机器人
* 强化学习

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>

Teaching
======
  <ul>{% for post in site.teaching reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
