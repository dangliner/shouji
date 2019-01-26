---
layout: page
title: My Personal Blog
---


<section>
  <ul class="post-list">
    {% for post in site.posts %}
    {% if post.categories contains "blog" %}
    <li>
      <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a> <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%b %d, %Y" }}</time>
    </li>
    {% endif %}
    {% endfor %}
  </ul>
</section>