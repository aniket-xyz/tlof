---
layout: base
title: Home
slug: home
---
[Why did I start this project?](/about).

<ul class="block-list list">
{% for post in site.posts %}
{% capture hour %}{{ post.date | date: '%H' }}{% endcapture %}
<li>
<a class="media block-list__link" href="{{ post.url }}">
  {% if post.no_image == true %}
  <img class="image media__img" src="/images/default.jpg">
  {% else %}
  <img class="image media__img" src="/images{{ post.url }}.jpg">
  {% endif %}
  <p class="media__body">
    <span class="gamma title">{{ post.title }}</span>
    <span class="info epsilon">
      <date>{{ post.date | date: '%d %b' }}</date> &ndash;
      <time>{% if hour < '12' && hour >= '6' %}Morning{% elsif hour < '18' && hour >= '12' %}Afternoon{% elsif hour >= '18' && hour < '0' %}Night{% elsif hour >= '0' && hour < '6' %}Sleep Time{% endif %}</time>
    </span>
  </p>
</a>
</li>
{% endfor %}
</ul>
