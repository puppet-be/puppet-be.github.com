---
layout: page 
title: Home
---

{% include JB/setup %}

<ul class="posts">
{% for post in site.posts limit: 5  %}
<article>
<header>
<h2><a href="{{BASE_PATH}}{{post.url}}">{{ post.title }}</a></h2>
<span class="date"><i class="icon-clock"></i><time datetime="{{post.date|date:"%F"}}">{{post.date|date:"%b %d, %Y"}}</time></span><br/>
<span class="category"><i class="icon-tag"></i> {{ post.categories | category_links }}</span><br/>
</header>
<div class="entry">{{ post.excerpt }}</div>
</article>
{% endfor %}
</ul>
