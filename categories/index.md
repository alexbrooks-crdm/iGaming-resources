---
layout: default
title: "iGaming Categories"
description: "Browse iGaming articles, guides and resources by category, covering casino technology, online gaming, payments and industry trends."
permalink: /categories/
---

<section class="section">
  <div class="container">

    <div class="section-heading">

      <h1>iGaming Categories</h1>

      <p>
        Explore practical articles, guides and resources organised by
        iGaming topic.
      </p>

    </div>

    {% if site.categories %}

      {% for category in site.categories %}

        {% assign category_name = category[0] %}
        {% assign category_posts = category[1] %}

        <section
          class="category-section"
          id="{{ category_name | slugify }}"
          aria-labelledby="category-{{ category_name | slugify }}"
        >

          <div class="category-heading">

            <h2 id="category-{{ category_name | slugify }}">
              {{ category_name }}
            </h2>

            <p>
              Explore {{ category_posts.size }}
              {% if category_posts.size == 1 %}
                article
              {% else %}
                articles
              {% endif %}
              about {{ category_name | downcase }}.
            </p>

          </div>

          <div class="article-grid">

            {% for post in category_posts %}

              <article class="article-card">

                <h3>
                  <a href="{{ post.url | relative_url }}">
                    {{ post.title }}
                  </a>
                </h3>

                {% if post.description %}

                  <p>
                    {{ post.description }}
                  </p>

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

        </section>

      {% endfor %}

    {% else %}

      <p>
        No categories are available yet.
      </p>

    {% endif %}

  </div>
</section>
