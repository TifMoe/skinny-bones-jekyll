---
layout: article
title: "Blog"
modified:
excerpt: "A collection of thoughts, mistakes, findings and lessons learned along the way."
tags: []
image:
  feature:
  teaser:
share: false
ads: false
---


{% for post in site.posts limit:1 %}
  <li style="list-style-type:none">
    <a href="{{ post.url }}">
    <h3 class="brand-blue">{{ post.title }}</h3>
    <p class="blogdate">{{ post.date | date: "%d %B %Y" }}</p>
    <div>{{ post.content }}</div>
    </a>
  </li>

  <footer class="page-footer">
  {% include page-author.html %}
    {% if page.share != false %}{% include share-this.html %}{% endif %}
    {% include page-meta.html %}
  </footer><!-- /.footer -->

{% endfor %}

<br> 
<br>

<h1>Recent Posts</h1>
{% for post in site.posts offset:1 limit:3 %}
  <li style="list-style-type:none">
    <a href="{{ post.url }}">
    <h3 class="brand-blue">{{ post.title }}</h3>
    <p class="blogdate">{{ post.date | date: "%d %B %Y" }}</p>
    <div>{{ post.content |truncatehtml | truncatewords: 60 }}
    <b> CLICK TO CONTINUE! </b>
    </div>
    
    </a>
  </li>
{% endfor %}

