---
layout: default
title: CEO DU
videos: true
image: /blog/shook-1.jpg
---
<html>
{% include showcase.html %}
</html>


<div class="container">
<h1>Featured Blogs</h1>
<div class="posts">


{% assign portfolio = site.portfolio | sort: 'order' %}

  {% for project in portfolio %}
        <div class="project-section">
        {% if project.video != nil %}
        <div class="youtube-player" data-id="{{ project.video }}" data-thumb="{{ project.image }}"></div>
        {% else %}
        <img src="{{ project.image | relative_url }}">
        {% endif %}
        <a href="{{ project.link }}"><span class="title">{{ project.title }}</span></a>
        <p> {{ project.description }}<br>
        {% if project.partner != nil %}<span class="partner">Made with {{ project.partner }}</span>{% endif %}
        {% for press in project.press %}
        <a href="{{ press.article_link }}" class="press">{{ press.name }}{% if forloop.last == false %},{% else %}.{% endif %}</a>
        {% endfor %}
        </p>

  </div>
  {% endfor %}
</div>


<hr>
<h1>Further Reading</h1>
{% for post in site.posts %}

{% if post.featured %}
  <div class="post">


    <h1 class="post-title" style="margin-bottom: 0rem;"><a href="{{ post.url }}">{{ post.title }}</a></h1>
    {% if post.description %}<p class="post-description">{{ post.description }}…</p>{% endif %}

  </div>
  {% endif %}
{% endfor %}
<hr>
</div>
