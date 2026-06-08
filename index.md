---
layout: default
title: Home
---

# Probably Fair

Hi, I'm Ryan. This is my learning archive for probability, statistics, mathematics, and the theory behind machine learning. I write only to clarify ideas, collect intuitions, and track my progress over time.

## Recent posts

{% if site.posts.size > 0 %}
  {% for post in site.posts limit:6 %}
- **{{ post.date | date: "%Y-%m-%d" }}** — [{{ post.title }}]({{ post.url | relative_url }})
  {% endfor %}
{% else %}
No posts yet.
{% endif %}

[View all posts →]({{ '/archive/' | relative_url }})

## What I write about

- Probability
- Statistics
- Mathematical thinking
- Machine learning theory
- Optimization
- Paper notes
- Learning logs