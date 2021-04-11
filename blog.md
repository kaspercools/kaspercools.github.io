---
layout: page
title: Blog
subtitle: lorem  
---

<div>
{% assign postsCategory = site.posts | group_by_exp:"post", "post.categories"  %}
<!-- {% for category in postsCategory %} -->
<!-- <h4 class="post-teaser__month">
<strong>
{% if category.name %} 
- - - - -  {{ category.name | array_to_sentence_string }} - - - - - 
{% else %} 
{{ Print }} 
{% endif %}
</strong>
</h4> -->
<ul class="list-posts">
{% for post in category.items %}
<li class="post-teaser">
    <a href="{{ post.url | prepend: site.baseurl }}">
    <span class="post-teaser__title">{{ post.title }}</span>
    <span class="post-teaser__date">{{ post.date | date: "%d %B %Y" }}</span>
    <div class="post-teaser__excerpt">
        {{ post.excerpt }}
    </div>
</a>
<strong class="post-cat">
{% if category.name %} 
{{ category.name | array_to_sentence_string }} 
{% else %} 
{{ Print }} 
{% endif %}
</strong>
</li>
{% endfor %}
</ul>
<!-- {% endfor %} -->
</div>