---
layout: default
published: true
---

<div class="posts">
  {% for post in site.posts %}
    <article class="post">
	  <h4>Written on {{ post.date | date: '%B %d, %Y' }}</h4>
      <div class="entry">
        {{ post.excerpt }}
        <a href="{{ site.baseurl }}{{ post.url }}">Read more...</a>
        <br/>
      </div>

    </article>
  {% endfor %}
</div>
