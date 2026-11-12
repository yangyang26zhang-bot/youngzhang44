---
layout: archive
title: "Animation Recommendations"
permalink: /animation/
author_profile: true
---

Animated series and films I recommend, alongside releases on my watchlist. Each entry includes a spoiler-free introduction.

<style>
.animation-list .animation-card { display: grid; grid-template-columns: minmax(140px, 200px) minmax(0, 1fr); gap: 1.5rem; padding: 1.5rem 0; border-bottom: 1px solid #d5d9dd; }
.animation-list .animation-visual { margin: 0; display: block; }
.animation-list .animation-visual img { display: block; width: 100%; height: auto; border-radius: 4px; }
.animation-list .animation-visual figcaption { font-size: 0.65em; line-height: 1.5; margin-top: 0.5rem; overflow-wrap: anywhere; }
.animation-list .animation-card h2 { margin-top: 0; }
.animation-list .animation-card p { font-size: 0.9em; }
.animation-list .animation-status { display: inline-block; margin: 0 0 0.75rem; padding: 0.2rem 0.6rem; border: 1px solid currentColor; border-radius: 4px; font-size: 0.75em; }
@media (max-width: 540px) {
  .animation-list .animation-card { grid-template-columns: 1fr; gap: 1rem; }
  .animation-list .animation-visual { width: min(100%, 240px); }
}
</style>

{% assign animation_posts = site.posts | where_exp: "post", "post.categories contains 'animation-recommendations'" %}
<div class="animation-list">
{% for post in animation_posts %}
  <article class="animation-card">
    {% if post.visual %}
      {% include animation-visual.html recommendation=post %}
    {% endif %}
    <div{% unless post.visual %} style="grid-column: 1 / -1;"{% endunless %}>
      <h2><a href="{{ post.url | relative_url }}">{{ post.title | escape }}</a></h2>
      {% if post.recommendation_status %}<span class="animation-status">{{ post.recommendation_status | escape }}</span>{% endif %}
      {{ post.excerpt | markdownify }}
      <p><a href="{{ post.url | relative_url }}">Read the introduction<span class="sr-only"> for {{ post.title | escape }}</span> &rarr;</a></p>
    </div>
  </article>
{% else %}
  <p>Recommendations will be added here over time.</p>
{% endfor %}
</div>
