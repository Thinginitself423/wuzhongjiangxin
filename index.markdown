---

---

---
---
layout: default
title: 首页
---

<div class="jumbotron mb-4">
  <div class="container">
    <h1 class="display-4">欢迎来到雾锁王国建筑攻略社区</h1>
    <p class="lead">这里收集了游戏中最实用的建筑技巧、灵感和成品展示</p>
    <hr class="my-4">
    <p>探索我们丰富的资源，从建材百科到精美的建筑成品展示。</p>
    <a class="btn btn-primary btn-lg" href="{{ '/tutorials/' | relative_url }}" role="button">开始学习</a>
  </div>
</div>

<h2 class="border-bottom pb-2 mb-4">推荐作品</h2>

<div class="row">
  {% assign featured_buildings = site.posts | where_exp: "post", "post.categories contains 'buildings'" | where: "featured", true | limit: 6 %}
  {% for post in featured_buildings %}
    <div class="col-md-4 mb-4">
      <div class="card h-100">
        {% if post.thumbnail %}
        <img src="{{ post.thumbnail | relative_url }}" class="card-img-top" alt="{{ post.title }}">
        {% endif %}
        <div class="card-body">
          <h5 class="card-title">{{ post.title }}</h5>
          <p class="card-text">{{ post.excerpt | strip_html | truncatewords: 20 }}</p>
        </div>
        <div class="card-footer bg-transparent border-top-0">
          <a href="{{ post.url | relative_url }}" class="btn btn-sm btn-primary">查看详情</a>
        </div>
      </div>
    </div>
  {% endfor %}
</div>

<div class="text-center mb-5">
  <a href="{{ '/buildings/' | relative_url }}" class="btn btn-outline-secondary">查看全部建筑作品</a>
</div>

<h2 class="border-bottom pb-2 mb-4">最新上传</h2>

<div class="row">
  {% assign latest_posts = site.posts | limit: 6 %}
  {% for post in latest_posts %}
    <div class="col-md-4 mb-4">
      <div class="card h-100">
        {% if post.thumbnail %}
        <img src="{{ post.thumbnail | relative_url }}" class="card-img-top" alt="{{ post.title }}">
        {% endif %}
        <div class="card-body">
          <h5 class="card-title">{{ post.title }}</h5>
          <p class="card-text small text-muted">{{ post.date | date: "%Y-%m-%d" }}</p>
          <p class="card-text">{{ post.excerpt | strip_html | truncatewords: 20 }}</p>
        </div>
        <div class="card-footer bg-transparent border-top-0">
          <a href="{{ post.url | relative_url }}" class="btn btn-sm btn-primary">查看详情</a>
        </div>
      </div>
    </div>
  {% endfor %}
</div>

<div class="text-center">
  <a href="{{ '/buildings/' | relative_url }}" class="btn btn-outline-secondary">查看全部文章</a>
</div>
