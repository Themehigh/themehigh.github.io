---
layout: default
---

<header class="header">
  <div class="header-title">
    <a href="{{ site.url }}{{ site.baseurl }}">{{ site.name }}</a>
  </div>
  <nav class="header-nav">
    {% for nav in site.nav %}
    {% if nav.url contains 'http://' or nav.url contains 'https://' %}
    <a href="{{ nav.url }}">{{ nav.name }}</a>
    {% else %}
    <a href="{{ nav.url | prepend: site.baseurl }}">{{ nav.name }}</a>
    {% endif %}
    {% endfor %}
  </nav>
</header>

<div class="list">
  {% if site.email-customizer.size == 0 %}
    <h2>No post found</h2>
  {% else %}
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
