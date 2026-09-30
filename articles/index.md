---
layout: default
title: Articles
description: "Browse all iGaming articles, guides and resources."
permalink: /articles/
---

<section class="section">
  <div class="container">

    <div class="section-heading">
      <h1>iGaming Articles</h1>
      <p>
        Explore our latest articles, guides and resources covering the
        iGaming industry, casino technology, payments and gaming trends.
      </p>
    </div>

    <div class="article-grid">

      {% for post in site.posts %}

        <article class="article-card">

          {% if post.categories %}
            <div class="category">
              {{ post.categories | first }}
            </div>
          {% endif %}

          <h3>
            <a href="{{ post.url | relative_url }}">
              {{ post.title }}
            </a>
          </h3>

          {% if post.description %}
            <p>{{ post.description }}</p>
          {% else %}
            <p>
              {{ post.excerpt | strip_html | truncate: 160 }}
            </p>
          {% endif %}

          <div class="article-date">
            {{ post.date | date: "%d %B %Y" }}
          </div>

        </article>

      {% else %}

        <p>No articles published yet.</p>

      {% endfor %}

    </div>

  </div>
</section>
