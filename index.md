---
layout: page
title: Home
slug: home
---
[Why did I start this project?](/about)

<ul class="block-list list">
{% for post in site.posts %}
{% capture hour %}{{ post.date | date: '%H' }}{% endcapture %}
<li>
<a class="block-list__link" href="{{ post.url }}">
  <div><img class="image img--center" src="{% if post.no_image == true %}/images/default.jpg{% else %}/images{{ post.url }}.jpg{% endif %}"></div><!--
  --><div class="text--center">
    <h2 class="gamma title">{{ post.title }}</h2>
    <span class="info epsilon">
      <date>{{ post.date | date: '%d %b' }}</date> &ndash;
      <time>{% if hour < '12' && hour >= '6' %}Morning{% elsif hour < '18' && hour >= '12' %}Afternoon{% elsif hour >= '18' && hour < '0' %}Night{% elsif hour >= '0' && hour < '6' %}Sleep Time{% endif %}</time>
    </span>
  </div>
</a>
</li>
{% endfor %}
</ul>