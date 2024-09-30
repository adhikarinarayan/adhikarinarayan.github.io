---
layout: default
title: Projects
---

# Projects

{% for project in site.projects %}
  <article>
    <h2><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h2>
    <p>{{ project.excerpt }}</p>
    <p><a href="{{ project.url | relative_url }}">Learn more</a></p>
  </article>
{% endfor %}
