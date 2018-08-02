---
layout: default
published: true
---

<div class="posts">
  {% for post in site.posts %}
    <article class="post">
      
      <div class="entry">
        {{ post.excerpt }}
        <a href="{{ site.baseurl }}{{ post.url }}">Read more...</a>
        <br/><br/>
      </div>

    </article>
  {% endfor %}
</div>
