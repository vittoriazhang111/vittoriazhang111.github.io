---
layout: page
permalink: /publications/
title: publications
description: Publications / 论文发表
nav: true
nav_order: 2
show_publications: false # enable after replacing the example bibliography with your own papers
---

<!-- _pages/publications.md -->

<!-- Bibsearch Feature -->

{% if page.show_publications %}
{% include bib_search.liquid %}

<div class="publications">

{% bibliography %}

</div>
{% else %}

<p lang="en">Publications will be added here.</p>

<p lang="zh-CN">论文信息将在整理后更新。</p>

{% endif %}
