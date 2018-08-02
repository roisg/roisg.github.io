---
layout: default
published: true
---

<div class="posts">
  {% for post in site.posts %}
    <article class="post">

      <h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>
      <h3>Written on {{ post.date | date: '%B %d, %Y' }}</h3>

      <div class="entry">
        {{ post.content }}
      </div>

    </article>
  {% endfor %}
</div>
