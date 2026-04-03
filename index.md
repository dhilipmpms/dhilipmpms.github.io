---
layout: default
title: Home
---

# Home

Welcome to my blog 🚀  
I write about Linux, FOSS, and Django.

---

## 📝 Latest Posts

{% raw %}
{% for post in site.posts %}
### [{{ post.title }}]({{ post.url }})

📅 {{ post.date | date: "%B %d, %Y" }}

{{ post.excerpt }}

---
{% endfor %}
{% endraw %}
