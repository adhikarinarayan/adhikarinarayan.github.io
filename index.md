<div class="blog-heading">
    <h1>Posts</h1>
</div>

<ul class="blog-list">
{% for post in site.posts %}
    <li class="blog-item">
        <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
        <p class="post-meta">Posted on: {{ post.date | date: "%B %d, %Y" }}</p>
        <p class="excerpt">{{ post.excerpt }}</p>
        <a class="read-more-link" href="{{ post.url | relative_url }}">Read more</a>
     </li>
{% endfor %}
</ul>
