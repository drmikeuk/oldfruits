---
layout: default
title: "Home"
nav: "yes"
sortTitle: "a"
---

<div class="container" style="padding-top: 2rem">

	<h1>Categories</h1>

	<ul>
	<!-- 'map' so only category property + 'uniq' to remove duplicates => simple list of cats -->
	{% assign cats = (site.data.fruits | map: "category"| uniq | sort ) %}
	{% for cat in cats %}
		<!-- remove spaces + top & tail => /category/<thiscat>.html -->
		{% assign link = cat | remove: " " | prepend: "/category/" | append: ".html" %}
		<li><a href="{{link}}">{{cat | capitalize }}</a></li>
	{% endfor %}
	</ul>

</div>
