---
layout: page
title: "文章归档"
desc: Find an archive of all our posts here. Every year I try to write more and more useful content on WebJeda. So this is where you can see what all the things I wrote on every single year!
permalink: /archive/
adallow: 0
---

<section id="archive">
<h2>Articles from this year</h2>
{% for post in site.posts %}
  {% unless post.next %}

  <ul class="this">
  {% else %}
  {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
  {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
  {% if year != nyear %}
  </ul>
  <h2>{{ post.date | date: '%Y' }}</h2>

  <ul class="past">
  {% endif %}
  {% endunless %}
  {%if post.o_link %}
 <li class="arch-list"><a href="{{ post.o_link }}" target="_blank">{{ post.title }}</a>&nbsp;<time>{{ post.date | date:"%d %b" }}</time></li>
  {%else%}
 <li class="arch-list"><a href="{{site.baseurl}}{{ post.url }}">{{ post.title }}</a>&nbsp;<time>{{ post.date | date:"%d %b" }}</time></li>
 {% endif %}
{% endfor %}
  </ul>
</section>