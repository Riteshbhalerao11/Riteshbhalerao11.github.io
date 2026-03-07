---
layout: page
title: Writing
permalink: /writing/
main_nav: true
---

Everything I write — blog posts, research notes, and other musings.

<div class="writing-section">
  <h2>Blog</h2>
  <ul class="writing-list">
    {% assign blog_posts = site.posts | where_exp: "post", "post.categories contains 'life' or post.categories contains 'tech'" %}
    {% for post in blog_posts %}
    <li>
      <span>
        <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
        {% for cat in post.categories %}
        <span class="category-tag">{{ cat }}</span>
        {% endfor %}
      </span>
      <span class="date">{{ post.date | date: "%b %Y" }}</span>
    </li>
    {% endfor %}
    {% if blog_posts.size == 0 %}
    <li>Coming soon.</li>
    {% endif %}
  </ul>
</div>

<div class="writing-section">
  <h2>Research</h2>
  <ul class="writing-list">
    {% assign research_posts = site.posts | where_exp: "post", "post.categories contains 'research'" %}
    {% for post in research_posts %}
    <li>
      <span>
        <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </span>
      <span class="date">{{ post.date | date: "%b %Y" }}</span>
    </li>
    {% endfor %}
    {% if research_posts.size == 0 %}
    <li>Coming soon.</li>
    {% endif %}
  </ul>
</div>

<div class="writing-section">
  <h2>Notes</h2>
  <ul class="writing-list">
    {% assign note_posts = site.posts | where_exp: "post", "post.categories contains 'notes'" %}
    {% for post in note_posts %}
    <li>
      <span>
        <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
      </span>
      <span class="date">{{ post.date | date: "%b %Y" }}</span>
    </li>
    {% endfor %}
    {% if note_posts.size == 0 %}
    <li>Coming soon.</li>
    {% endif %}
  </ul>
</div>
