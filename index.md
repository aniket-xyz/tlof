---
layout: base
title: Home
slug: home
---
### Recent writings

<ul class="block-list list matrix two-cols">
{% for post in site.posts %}
{% capture hour %}{{ post.date | date: '%H' }}{% endcapture %}
<li{% if post.categories == 'rhapsody' %} class="all-cols"{% endif %}>
<a class="block-list__link" href="{{ post.url }}">
  <span class="title">{{ post.title }}</span>
  <span class="info milli">
    <date>{{ post.date | date: '%d %b' }}</date> &ndash;
    <time>{% if hour < '12' && hour >= '6' %}Morning{% elsif hour < '18' && hour >= '12' %}Afternoon{% elsif hour >= '18' && hour < '0' %}Night{% elsif hour >= '0' && hour < '6' %}Sleep Time{% endif %}</time>
  </span>
</a>
</li>
{% endfor %}
</ul>