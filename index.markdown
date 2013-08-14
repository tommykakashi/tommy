---
layout: default
title: TommyKakashi's Blog
---
<h2>{{ page.title }}</h2>
<p>Welcome!</p>
<div id="entrance">
	<ul>
		<li>
			<a class="core-nav icon-quill-2" href="/blog" title="TommyKakashi - Blog"></a>
		</li>
		<li>
			<a class="core-nav icon-info-2" href="/about.html" title="TommyKakashi - About"></a>
		</li>
	</ul>
</div>

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