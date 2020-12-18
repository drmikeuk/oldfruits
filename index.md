---
layout: default
title: "Home"
---

<div class="container">
	<div class="row">

{% for fruit in site.data.fruits %}

<div class="col-lg-3 col-md-6 col-sm-12 pb-4" >
  <div class="card" >
    <img src="{{ fruit.image | prepend: "/images/"}}" class="card-img-top" alt="photo of {{ fruit.fruit }}">
    <div class="card-body">
      <h5 class="card-title">{{ fruit.fruit }}</h5>
      <p class="card-text">{{ fruit.blurb }}</p>
    </div>
<!--    <div class="card-footer">
      <a href="{{ city.Link }}" class="btn btn-primary">Project details <i class="fas fa-chevron-right"></i></a>
    </div>
-->
  </div>
</div>



{% endfor %}

	</div>
</div>
