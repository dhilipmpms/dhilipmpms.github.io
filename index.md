---
layout: default
title: Home
---

<div class="container">

# Welcome 🚀

I write about **Linux**, **FOSS**, and **Django**.

---

## 📝 Latest Posts

{% for post in site.posts %}
<a href="{{ post.url }}" class="resource-link" style="margin-bottom: 16px;">
  <span class="link-icon">📄</span>
  <span>
    <strong>{{ post.title }}</strong><br>
    <small style="color: var(--text-muted);">📅 {{ post.date | date: "%B %d, %Y" }}</small>
  </span>
</a>
{% endfor %}

</div>
