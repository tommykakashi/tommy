---
layout: default
title: My Blog
---
<h2>{{ page.title }}</h2>
<p>The latest articles</p>
<ul id="posts" class="index">
	{% for post in site.posts %}
　　　　<li>
 		<a href="{{ site.baseurl }}{{ post.url }}">{{ post.title | xml_escape }}</a>
 		<span>
 			<time datetime="{{ post.date | date: "%Y-%m-%d" }}">
 					{{ post.date | date: "%B %d, %Y" }}
 			</time>
 		</span>
	</li>
	{% endfor %}
</ul>