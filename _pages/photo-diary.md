---
title: "Photo Diary"
permalink: /photo-diary/
layout: single
classes: wide
author_profile: true
redirect_from:
  - /photos
---

{% include base_path %}

<div class="grid__wrapper">
  {% for post in site.photo_diary %}
    {% include archive-single.html type="grid" %}
  {% endfor %}
</div>