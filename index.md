---
layout: default
title: "Home"
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




<div class="container" style="padding-top: 2rem">
	<h1>All fruits</h1>
	<div class="row">

{% for fruit in site.data.fruits %}

<div class="col-lg-3 col-md-6 col-sm-12 pb-4" >
  <div class="card" >
    <img src="{{ fruit.image | prepend: "/images/"}}" class="card-img-top" alt="photo of {{ fruit.fruit }}">
    <div class="card-body">
      <h5 class="card-title">{{ fruit.fruitname }}</h5>
      <p class="card-text">{{ fruit.blurb }}</p>
    </div>
    <div class="card-footer">
      {% assign link = fruit.fruitname | remove: " " | downcase | prepend: "/fruits/"| append: ".html" %}
      <a href="{{ link }}" class="btn btn-primary">Details <i class="fas fa-chevron-right"></i></a>
    </div>
  </div>
</div>

{% endfor %}

	</div>
</div>
