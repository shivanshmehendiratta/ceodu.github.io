---
layout: default
title: Blog
---
<div class="container" style="margin-top:80px">
<h1>Top posts</h1>

{% for post in site.posts %}

{% if post.featured %}
  <div class="post post-web" >


    <h1 class="post-title post-title-web" style="margin-bottom: 0rem;"><a href="{{ post.url }}">{{ post.title }}</a></h1><br><div class=post-title-date-web> {{ page.date | date_to_string }} </div>
    {% if post.description %}<p class="post-description post-description-web">{{ post.description }}<br><a href="{{ post.url }}"><u>...Read more</u></a></p>{% endif %}

  </div>
  {% endif %}
{% endfor %}

<h1>All posts</h1>

{% for post in site.posts %}

{% if post.featured %}
{% else %}

  <div class="post post-web">



    <h1 class="post-title post-title-web" style="margin-bottom: 0rem;"><a href="{{ post.url }}">{{ post.title }}</a></h1>
    {% if post.description %}<p class="post-description post-description-web">{{ post.description }}<br><a href="{{ post.url }}"><u>...Read more</u></a></p>{% endif %}


  </div>
  {% endif %}
{% endfor %}
</div>
