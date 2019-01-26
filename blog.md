---
layout: page
title: My Personal Blog
pagination:
enabled: true
---


<section>
  <ul class="post-list">
    {% for post in site.posts %}
    <li>
      <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a> <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%b %d, %Y" }}</time>
    </li>
    {% endfor %}
  </ul>
</section>

{% if paginator.total_pages > 1 %}
<ul>
  {% if paginator.previous_page %}
  <li>
    <a href="{{ paginator.previous_page_path | prepend: site.baseurl }}">Newer</a>
  </li>
  {% endif %}
  {% if paginator.next_page %}
  <li>
    <a href="{{ paginator.next_page_path | prepend: site.baseurl }}">Older</a>
  </li>
  {% endif %}
</ul>
{% endif %}