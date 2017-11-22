---
layout: page
title: blog
permalink: /blog
---

<ul>
{% for post in site.posts %}
<li><a href="{{ post.url }}">{{ site.title }}</a></li>
{% endfor %}
</ul>
