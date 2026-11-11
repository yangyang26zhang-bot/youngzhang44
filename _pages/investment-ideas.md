---
layout: archive
title: "Investment Ideas"
permalink: /investment-ideas/
author_profile: true
---

Occasional notes on individual stocks, company fundamentals, and industry trends. I use this space to record my investment theses and revisit them as new information becomes available.

{% assign investment_posts = site.posts | where_exp: "post", "post.categories contains 'investment-ideas'" %}
{% for post in investment_posts %}
  {% include archive-single.html %}
{% else %}
  <p>No investment notes have been published yet.</p>
{% endfor %}
