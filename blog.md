---
layout: default
title: Blog
---
<div class="container" style="margin-top:80px">
<h1>Top posts</h1>

{% for post in site.posts %}

{% if post.featured %}
  <div class="post">


    <h1 class="post-title" style="margin-bottom: 0rem;"><a href="{{ post.url }}">{{ post.title }}</a></h1>
    {% if post.description %}<p class="post-description">{{ post.description }}…</p>{% endif %}

  </div>
  {% endif %}
{% endfor %}

<h1>All posts</h1>


{% for post in paginator.posts %}


{% if post.featured %}
{% else %}

  <div class="post">



    <h1 class="post-title" style="margin-bottom: 0rem;"><a href="{{ post.url }}">{{ post.title }}</a></h1>
    {% if post.description %}<p class="post-description">{{ post.description }}…</p>{% endif %}


  </div>
  {% endif %}
{% endfor %}
{% if paginator.total_pages > 1 %}
<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path | relative_url }}">&laquo; Prev</a>
  {% else %}
    <span>&laquo; Prev</span>
  {% endif %}

  {% for page in (1..paginator.total_pages) %}
    {% if page == paginator.page %}
      <em>{{ page }}</em>
    {% elsif page == 1 %}
      <a href="/">{{ page }}</a>
    {% else %}
      <a href="{{ site.paginate_path | relative_url | replace: ':num', page }}">{{ page }}</a>
    {% endif %}
  {% endfor %}

  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path | relative_url }}">Next &raquo;</a>
  {% else %}
    <span>Next &raquo;</span>
  {% endif %}
</div>
{% endif %}
</div>
