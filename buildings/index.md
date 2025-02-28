---
layout: default
title: 建筑成品展示
---

# 建筑成品展示

欣赏来自雾锁王国玩家们的精美建筑作品，获取灵感与创作动力。

## 分类浏览

<div class="row mb-4">
  <div class="col-md-6">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">生存向建筑</h5>
        <p class="card-text">实用性与美观并重的生存模式建筑。</p>
        <a href="{{ '/buildings/survival/' | relative_url }}" class="btn btn-primary">浏览生存向</a>
      </div>
    </div>
  </div>
  <div class="col-md-6">
    <div class="card">
      <div class="card-body">
        <h5 class="card-title">纯建筑</h5>
        <p class="card-text">注重美观的创造模式建筑作品。</p>
        <a href="{{ '/buildings/creative/' | relative_url }}" class="btn btn-primary">浏览纯建筑</a>
      </div>
    </div>
  </div>
</div>

## 最新建筑作品

<div class="row">
  {% assign building_posts = site.posts | where_exp: "post", "post.categories contains 'buildings'" | limit: 9 %}
  {% for post in building_posts %}
    <div class="col-md-4 mb-4">
      <div class="card">
        {% if post.thumbnail %}
        <img src="{{ post.thumbnail | relative_url }}" class="card-img-top" alt="{{ post.title }}">
        {% endif %}
        <div class="card-body">
          <h5 class="card-title">{{ post.title }}</h5>
          <p class="card-text small">
            {% if post.building_type %}类型: {{ post.building_type }} | {% endif %}
            {% if post.building_style %}风格: {{ post.building_style }}{% endif %}
          </p>
          <p class="card-text">{{ post.excerpt | strip_html | truncatewords: 20 }}</p>
          <a href="{{ post.url | relative_url }}" class="btn btn-primary">查看详情</a>
        </div>
      </div>
    </div>
  {% endfor %}
</div>