---
layout: default
title: Blog
permalink: /blog/
---

<div class="posts-list">
  {% for post in site.posts %}
    <article class="post post-card">
      <div class="post-meta">{{ post.date | date: "%B %d, %Y" }}</div>
      <h2><a class="post-link" href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h2>
      <div class="entry">
        {{ post.excerpt | strip_html | truncatewords: 50 }}
      </div>
      <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More &rarr;</a>
    </article>
  {% endfor %}
</div>
