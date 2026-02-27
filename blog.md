---
layout: default
title: Blog
permalink: /blog/
---

<div class="posts-list">
  {% for post in site.posts %}
    <article class="post-card">
      {% if post.thumbnail %}
        <div class="card-cover" style="background-image: url('{{ site.baseurl }}{{ post.thumbnail }}')"></div>
      {% else %}
        <div class="card-cover no-image" style="display:flex; align-items:center; justify-content:center; font-size:48px; color:#9faec5; font-weight:bold;">
           {{ post.title | slice: 0 }}
        </div>
      {% endif %}
      
      <div class="card-content">
        <div class="post-meta">
          <span>{{ post.date | date: "%Y-%m-%d" }}</span>
          {% if post.categories.size > 0 %}
            <span style="color: #4a90e2; font-weight:500;">{{ post.categories | first }}</span>
          {% endif %}
        </div>
        
        <h3 class="post-title">
          <a href="{{ site.baseurl }}{{ post.url }}" style="position:relative; z-index:2;">{{ post.title }}</a>
        </h3>
        
        <div class="post-excerpt">
          {{ post.excerpt | strip_html | truncate: 80 }}
        </div>
        
        <div class="card-tags" style="position:relative; z-index:2;">
          {% for tag in post.tags limit:3 %}
            <a href="{{ site.baseurl }}/tags/#{{ tag }}" class="tag">#{{ tag }}</a>
          {% endfor %}
        </div>
      </div>
      <!-- 整个卡片可点击 -->
      <a href="{{ site.baseurl }}{{ post.url }}" style="position:absolute; top:0; left:0; width:100%; height:100%; z-index:1;"></a>
    </article>
  {% endfor %}
</div>

<script>
  document.addEventListener("DOMContentLoaded", function() {
    const observerOptions = {
      threshold: 0.1,
      rootMargin: "0px 0px -50px 0px"
    };

    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add("visible");
          observer.unobserve(entry.target);
        }
      });
    }, observerOptions);

    const cards = document.querySelectorAll('.post-card');
    cards.forEach((card, index) => {
      // 错落动画延迟
      card.style.transitionDelay = (index % 3) * 0.15 + 's';
      observer.observe(card);
    });
  });
</script>
