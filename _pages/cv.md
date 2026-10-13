---
layout: page
permalink: /cv/
title: CV
nav: true
nav_order: 5
description: Education, experience, publications, and research interests / 教育背景、工作经历、论文发表与研究方向
toc:
  sidebar: left
_styles: |
  .cv-content { font-size: 1rem; line-height: 1.65; }
  .cv-content h2 { font-size: 1.35rem; font-weight: 600; margin-bottom: 1rem; }
  .cv-entry-title { font-size: 1.05rem; font-weight: 600; line-height: 1.45; margin-bottom: 0.45rem; }
  .cv-content p { margin-bottom: 0.55rem; }
  .cv-entry { margin-bottom: 1.4rem; }
  .cv-period { font-size: 0.9rem; opacity: 0.8; margin-bottom: 0.5rem; }
---

{% if site.data.socials.cv_pdf %}
<p><a href="{{ site.data.socials.cv_pdf | relative_url }}" target="_blank" rel="noopener noreferrer">Download CV / 下载简历</a></p>
{% endif %}

<div class="cv-content">
{% for section in site.data.personal.cv_sections %}
<section class="card mt-3 p-3">
  <h2>{{ section.title | escape }}</h2>
  {% if section.entries.size > 0 %}
    {% for entry in section.entries %}
    <div class="cv-entry">
      {% if entry.label %}
      <div class="cv-entry-title">{% if entry.url %}<a href="{{ entry.url | escape }}">{{ entry.label | escape }}</a>{% else %}{{ entry.label | escape }}{% endif %}</div>
      {% endif %}
      {% if entry.period %}<p class="cv-period">{{ entry.period | escape }}</p>{% endif %}
      {% if entry.details %}<p lang="en">{{ entry.details | escape }}</p>{% endif %}
      {% if entry.translation %}<p lang="zh-CN">{{ entry.translation | escape }}</p>{% endif %}
    </div>
    {% endfor %}
  {% else %}
  <p>To be updated / 待更新</p>
  {% endif %}
</section>
{% endfor %}
</div>
