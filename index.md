---
layout: default
title: 
permalink: /
---
# Updates
<ul>
  {% for post in site.posts %}
    <li> 
      <a href="{{ post.url }}">{{ post.title }}</a>
      <span class="date">({{ post.date | date_to_string }})</span> 
      {{ post.content}}
    </li>
  {% endfor %}
</ul>
