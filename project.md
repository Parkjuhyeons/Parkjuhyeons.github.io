---
layout: default
title: Project Long Haul
---

<div class="home" id="home">
  <h1 class="pageTitle">Recent Project</h1>
<!--
    <ul class="posts noList">
        <li>
            <h4>Hello, I am Ju Hyeon who is trying to be a great developer. This blog posts a project or course of study that I've been preparing for. Please give us a lot of feedback and attention.</h4>
        </li>
    </ul>
-->
  <ul class="posts noList">
    {% for post in paginator.posts %}
      <li>
        <span class="date">{{ post.date | date: '%B %d, %Y' }}</span>
        <h3><a class="post-link" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></h3>
        <p>{% if post.description %}{{ post.description }}{% else %}{{ post.excerpt | strip_html }}{% endif %}</p>
      </li>
    {% endfor %}
  </ul>
  <!-- Pagination links -->
  <div class="pagination">
    {% if paginator.previous_page %}
      <a href="{{ paginator.previous_page_path | prepend: site.baseurl }}" class="previous button__outline">Newer Posts</a> 
    {% endif %}
    {% if paginator.next_page %}
      <a href="{{ paginator.next_page_path | prepend: site.baseurl }}" class="next button__outline">Older Posts</a>
    {% endif %}
  </div>
</div>
