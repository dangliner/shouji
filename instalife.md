---
layout: page
title: My Personal Instalife
---

<section>

  {% for post in site.posts %}
  {% if post.categories contains "insta" %}

  <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y-%m-%d"}}</time>
  <p>{{ post.content | markdownify }}</p>

  {% endif %}
  <hr>
  {% endfor %}

</section>