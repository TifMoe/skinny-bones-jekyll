---
layout: archive
permalink: /
title: "Latest Posts"
---

<div class="page-lead" style="background-image:/images/steven-wang-421577.jpg)">
  <div class="wrap page-lead-content">
    <h1>Tiffany Moeller</h1>
    <h2>Data scientist</h2>
  </div>
</div>


<div class="tiles">
{% for post in site.posts %}
	{% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->
