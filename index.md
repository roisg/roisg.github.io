---
layout: default
published: true
---

<div class="posts">
  {% for post in site.posts %}
    <article class="post">

      <h1><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h1>
      <p>Written on {{ post.date | date: '%B %d, %Y' }}</p>

      <div class="entry">
        {{ post.content }}
      </div>

    </article>
  {% endfor %}
</div>
