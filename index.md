---
layout: home
permalink: /
image:
  feature: feature-image.jpg
  credit: Steven Wang 
  creditlink: https://unsplash.com/@smwangphoto 
  logo-center: #logo-transp.png
---

<div align='center'>
<h2>Check out my latest blogs:</h2>
<br>

{% for post in site.categories.blog %}
  {% include post-list.html %} 
{% endfor %}
</div>

<!---
<div class="tiles" align="center">

<div class="tile">
  <h2 class="post-title">Drawing Out The Story</h2>
  <p class="post-excerpt">Descriptive analytics can be used to tell a story about the way the world in in new and innovative ways.</p>
   
</div>

<div class="tile">
  <h2 class="post-title">Drawing Conclusions</h2>
  <p class="post-excerpt">Prescriptive analytics can help us understand what drives changes in patterns or trends we observe using descriptive analytics. </p>
</div><

<div class="tile">
  <h2 class="post-title">Drawing Up Future Plans</h2>
  <p class="post-excerpt">Predictive analytics - say some really cool stuff here</p>
</div>

</div> -->
