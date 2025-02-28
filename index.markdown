---

---

---
layout: default
title: 首页
---

<div class="jumbotron p-4 bg-light">
  <h1 class="display-4">欢迎来到雾锁王国建筑攻略社区</h1>
  <p class="lead">这里收集了游戏中最实用的建筑技巧、灵感和成品展示</p>
</div>

## 推荐作品

<div class="row">
  {% assign featured_buildings = site.posts | where_exp: "post", "post.categories contains 'buildings'" | where: "featured", true | limit: 6 %}
  {% for post in featured_buildings %}
    <div class="col-md-4 mb-4">
      <div class="card">
        {% if post.thumbnail %}
        <img src="{{ post.thumbnail | relative_url }}" class="card-img-top" alt="{{ post.title }}">
        {% endif %}
        <div class="card-body">
          <h5 class="card-title">{{ post.title }}</h5>
          <p class="card-text">{{ post.excerpt | strip_html | truncatewords: 20 }}</p>
          <a href="{{ post.url | relative_url }}" class="btn btn-primary">查看详情</a>
        </div>
      </div>
    </div>
  {% endfor %}
</div>

<div class="text-center mb-5">
  <a href="{{ '/buildings/' | relative_url }}" class="btn btn-outline-secondary">查看全部建筑作品</a>
</div>

## 最新上传

<div class="row">
  {% assign latest_posts = site.posts | limit: 6 %}
  {% for post in latest_posts %}
    <div class="col-md-4 mb-4">
      <div class="card">
        {% if post.thumbnail %}
        <img src="{{ post.thumbnail | relative_url }}" class="card-img-top" alt="{{ post.title }}">
        {% endif %}
        <div class="card-body">
          <h5 class="card-title">{{ post.title }}</h5>
          <p class="card-text small text-muted">{{ post.date | date: "%Y-%m-%d" }}</p>
          <p class="card-text">{{ post.excerpt | strip_html | truncatewords: 20 }}</p>
          <a href="{{ post.url | relative_url }}" class="btn btn-primary">查看详情</a>
        </div>
      </div>
    </div>
  {% endfor %}
</div>

<div class="text-center">
  <a href="{{ '/buildings/' | relative_url }}" class="btn btn-outline-secondary">查看全部建筑作品</a>
</div>
