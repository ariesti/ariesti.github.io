---
layout: default
title: Her Writings
---

<h1>{{ page.title }}</h1>
	<ul class="posts">

	  {% for post in site.contents %}
	    <li><span>{{ content.date | date_to_string }}</span> » <a href="{{ content.url }}" title="{{ content.title }}">{{ content.title }}</a></li>
	  {% endfor %}
	</ul>
