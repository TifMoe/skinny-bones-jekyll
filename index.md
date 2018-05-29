---
layout: home
permalink: /
image:
  feature: feature-image0.jpg
  credit: Steve Johnson 
  creditlink: https://unsplash.com/@steve_j 
  logo-center: drawing-logo.png
  teaser: site-teaser-logo.png
---

<div align='center'>
<h2>Check out my latest blogs:</h2>
<br>

{% for post in site.categories.blog %}
  {% include post-list.html %} 
{% endfor %}
</div>

