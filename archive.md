---
layout: main
title: Archive
permalink: /archive/
useInNav: true
---

<div class="home content-box clearfix">
	<section id="archive">
	  <h1> Archive </h1>
	  <h2>This year's posts</h2>
	  {%for post in site.posts %}
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
	      <li><time>{{ post.date | date:"%d %b" }}</time>&nbsp;:&nbsp;<a href="{{ post.url }}">{{ post.title }}</a></li>
	  {% endfor %}
	  </ul>
	</section>
</div>
