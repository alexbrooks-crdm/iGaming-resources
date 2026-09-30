---
layout: default
title: Categories
description: "Browse iGaming articles and resources by category."
permalink: /categories/
---

<section class="section">
  <div class="container">

    <div class="section-heading">
      <h1>iGaming Categories</h1>
      <p>
        Explore articles and resources organised by topic.
      </p>
    </div>

    {% if site.categories %}

      {% for category in site.categories %}

        {% assign category_name = category[0] %}
        {% assign category_posts = category[1] %}

        <div class="category-section">

          <h2>
            {{ category_name }}
          </h2>

          <div class="article-grid">

            {% for post in category_posts %}

              <article class="article-card">

                <h3>
                  <a href="{{ post.url | relative_url }}">
                    {{ post.title }}
                  </a>
                </h3>

                {% if post.description %}
                  <p>{{ post.description }}</p>
                {% else %}
                  <p>
                    {{ post.excerpt | strip_html | truncate: 140 }}
                  </p>
                {% endif %}

                <div class="article-date">
                  {{ post.date | date: "%d %B %Y" }}
                </div>

              </article>

            {% endfor %}

          </div>

        </div>

      {% endfor %}

    {% else %}

      <p>No categories available yet.</p>

    {% endif %}

  </div>
</section>
