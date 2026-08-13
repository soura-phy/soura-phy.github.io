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

<style>
  .photo-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(240px, 1fr));
    gap: 20px;
    margin-top: 20px;
  }
  .photo-card {
    border: 1px solid #e2e8f0;
    border-radius: 8px;
    overflow: hidden;
    text-decoration: none !important;
    color: inherit;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
    display: flex;
    flex-direction: column;
    background: #fff;
  }
  .photo-card:hover {
    transform: translateY(-4px);
    box-shadow: 0 6px 16px rgba(0,0,0,0.1);
  }
  .photo-card img {
    width: 100%;
    height: 180px;
    object-fit: cover;
    display: block;
  }
  .photo-card-info {
    padding: 12px;
  }
  .photo-card-title {
    font-weight: bold;
    display: block;
    font-size: 1rem;
    color: #222;
  }
  .photo-card-date {
    font-size: 0.85rem;
    color: #666;
  }
</style>

<div class="photo-grid">
  {% for item in site.photo_diary %}
    <a href="{{ base_path }}{{ item.url }}" class="photo-card">
      {% if item.header.teaser %}
        <img src="{{ base_path }}{{ item.header.teaser }}" alt="{{ item.title }}">
      {% elsif item.teaser %}
        <img src="{{ base_path }}{{ item.teaser }}" alt="{{ item.title }}">
      {% endif %}
      <div class="photo-card-info">
        <span class="photo-card-title">{{ item.title }}</span>
        {% if item.date %}
          <span class="photo-card-date">{{ item.date | date: "%B %d, %Y" }}</span>
        {% endif %}
      </div>
    </a>
  {% endfor %}
</div>