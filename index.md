---
layout: default
title: Home
---

<div class="container">

<div class="blog-hero" style="text-align: center; border-bottom: none; display: flex; flex-direction: column; align-items: center;">
  <span class="blog-tag" style="background: rgba(129, 140, 248, 0.1); color: #818cf8; border-color: rgba(129, 140, 248, 0.2);">🚀 Welcome to my digital garden</span>
  <h1 class="blog-title" style="font-size: 3.5rem; margin-top: 16px; margin-bottom: 24px;">Dhilip's Space</h1>
  <p class="blog-subtitle" style="margin: 0 auto; line-height: 1.8;">
    I write about <strong style="color: var(--accent);">Linux</strong>, <strong style="color: var(--accent);">FOSS</strong>, and <strong style="color: var(--accent);">Django</strong>.<br>
    Exploring the depths of open-source technology, sharing my journey, and building things for the web.
  </p>
</div>

<hr style="margin: 20px 0 50px 0; border: none; height: 1px; background: linear-gradient(90deg, transparent, var(--border), transparent);" />

<div style="display: flex; align-items: center; justify-content: space-between; margin-bottom: 30px;">
  <h2 style="margin: 0; padding: 0; border: none; font-size: 1.8rem;">📝 Latest Posts</h2>
  <a href="/archive" style="color: var(--text-muted); font-size: 0.9rem; font-weight: 500;">View all archives →</a>
</div>

<div class="posts-grid" style="display: grid; gap: 24px; grid-template-columns: 1fr;">
{% for post in site.posts %}
  <a href="{{ post.url }}" class="card" style="text-decoration: none; margin: 0; padding: 32px; display: flex; flex-direction: column; transition: transform 0.3s ease, border-color 0.3s ease, box-shadow 0.3s ease;">
    <div class="card-accent"></div>
    <div style="display: flex; align-items: center; justify-content: space-between; margin-bottom: 16px;">
      <span class="blog-tag" style="margin: 0;">Article</span>
      <small style="color: var(--text-muted); font-size: 0.85rem; font-weight: 500; display: flex; align-items: center; gap: 6px;">
        <svg width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><rect x="3" y="4" width="18" height="18" rx="2" ry="2"></rect><line x1="16" y1="2" x2="16" y2="6"></line><line x1="8" y1="2" x2="8" y2="6"></line><line x1="3" y1="10" x2="21" y2="10"></line></svg>
        {{ post.date | date: "%B %d, %Y" }}
      </small>
    </div>
    
    <h3 style="color: var(--text-primary); font-size: 1.5rem; margin: 0 0 12px 0; font-weight: 700; line-height: 1.4;">{{ post.title }}</h3>
    
    <p style="color: var(--text-secondary); margin: 0 0 24px 0; font-size: 1rem; line-height: 1.6; display: -webkit-box; -webkit-line-clamp: 2; -webkit-box-orient: vertical; overflow: hidden;">
      {% if post.excerpt %}{{ post.excerpt | strip_html | truncatewords: 35 }}{% else %}Click to read more about this topic...{% endif %}
    </p>
    
    <div style="margin-top: auto; display: flex; align-items: center; gap: 8px; color: var(--accent); font-weight: 600; font-size: 0.95rem;">
      Read Post 
      <svg width="16" height="16" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" style="transform: translateY(1px);"><line x1="5" y1="12" x2="19" y2="12"></line><polyline points="12 5 19 12 12 19"></polyline></svg>
    </div>
  </a>
{% endfor %}
</div>

</div>
