---
layout: default
title: Recent Posts 
---


<div class="blog-heading"> <h1> My Thoughts </h1> </div>

{% for post in site.posts %}
  <article>
    <p class="post-meta">Posted on {{ post.date | date: "%B %d, %Y" }} {% if post.categories %} in {{ post.categories | join: ", " }} {% endif %}</p> 
    <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    <p>{{ post.excerpt }}</p>
    <p><a href="{{ post.url | relative_url }}" class="read-more-link">Read more</a></p>
  </article>
{% endfor %}
