---
layout: page
title: Home
---

{% include JB/setup %}

<h1>Posts</h1>

<div class="posts">
  {% for post in site.posts limit: 5  %}
    <article>
      <header style="clear: both; margin-bottom: 20px;">
        <h2 style="margin-right: 40px; margin-bottom: 0px;"><a href="{{BASE_PATH}}{{post.url}}">{{ post.title }}</a></h2>
        <span class="date"><i class="icon-time">&nbsp;</i><time datetime="{{post.date|date:"%F"}}">{{post.date|date:"%b %d, %Y"}}</time></span>
        <span class="category"><i class="icon-tag">&nbsp;</i> {{ post.categories | category_links }}</span>
      </header>
      <div class="entry">{{ post.excerpt }}</div>
    </article>
  {% endfor %}
</div>
