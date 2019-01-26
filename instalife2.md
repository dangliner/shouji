---
layout: page
title: My Personal Instalife
pagination:
    enabled: true
    collection: instalife
---

{% for post in paginator.posts %}
 <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y-%m-%d"}}</time>
<p>{{ post.content | markdownify }}</p>
{% unless forloop.last %}
<hr>
{% endunless %}
{% endfor %}

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
<div>
{% if paginator.page_trail %}
  {% for trail in paginator.page_trail %}
    <li {% if page.url == trail.path %} class="selected"{% endif %}>
        <a href="{{ trail.path | prepend: site.baseurl }}" title="{{trail.title}}">{{ trail.num }}</a>
    </li>
  {% endfor %}
{% endif %}
</div>