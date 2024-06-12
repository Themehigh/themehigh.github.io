---
layout: default
---
<header class="header">
  <div class="header-title">
    <a href="{{ site.url }}{{ site.baseurl }}">{{ site.name }}</a>
  </div>
</header>

<div class="list">
  {% if site.posts.size == 0 %}
    <h2>No post found</h2>
  {% else %}
  <h2>Posts</h2>
  <ul>
  {% for post in site.posts %}
  <li>
      {% if post.link %}
      <a href="{{ post.link }}">
      {% else %}
      <a href="{{ post.url | prepend: site.baseurl }}">
      {% endif %}
          {{ post.title }}
      </a>
   </li>   
  {% endfor %}
  </ul>
  {% endif %}
</div>

<div class="list">
  {% if site.best-practices.size == 0 %}
    <h2>No Best Practices Found</h2>
  {% else %}
  <h2>Best Practices</h2>
  <ul>
  {% for best-practice in site.best-practices %}
  <li>
      {% if best-practice.link %}
      <a href="{{ best-practice.link }}">
      {% else %}
      <a href="{{ best-practice.url | prepend: site.baseurl }}">
      {% endif %}
          {{ best-practice.title }}
      </a>
   </li>   
  {% endfor %}
  </ul>
  {% endif %}
</div>

<div class="list">
  {% if site.email-customizer.size == 0 %}
    <h2>No post found</h2>
  {% else %}
  <h2>Email Customizer</h2>
  <ul>
  {% for post in site.email-customizer %}
  <li>
      {% if post.link %}
      <a href="{{ post.link }}">
      {% else %}
      <a href="{{ post.url | prepend: site.baseurl }}">
      {% endif %}
          {{ post.title }}
      </a>
   </li>   
  {% endfor %}
  </ul>
  {% endif %}
</div>
