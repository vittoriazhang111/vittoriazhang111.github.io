---
layout: page
permalink: /people/
title: team
description: Collaborators and team members / 合作者与团队成员
nav: true
nav_order: 7
---

{% assign about_page = site.pages | where: "permalink", "/" | first %}

<section class="clearfix">
  <h2>{{ site.title | escape }}</h2>
  <p>{{ about_page.subtitle | escape }}</p>

{% if about_page.profile.image %}
    {% assign profile_image = about_page.profile.image | prepend: 'assets/img/' %}
    {% if about_page.profile.image_circular %}
      {% assign profile_class = 'img-fluid z-depth-1 rounded-circle' %}
    {% else %}
      {% assign profile_class = 'img-fluid z-depth-1 rounded' %}
    {% endif %}
    <div class="profile float-{{ about_page.profile.align }}">
      {% include figure.liquid loading="eager" path=profile_image title=site.title class=profile_class %}
      {% if about_page.profile.more_info != blank %}
      <div class="more-info">{{ about_page.profile.more_info }}</div>
      {% endif %}
    </div>
{% endif %}

  <p lang="en">{{ site.data.personal.biography.english | escape }}</p>
  <p lang="zh-CN">{{ site.data.personal.biography.chinese | escape }}</p>
</section>
