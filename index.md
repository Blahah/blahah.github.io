---
layout: page
title: not finished
subtitle: this site is under development
---
{% include JB/setup %}

{% for post in site.posts %}
  <h1><a href="{{ post.url }}">{{ post.title }}</a> <small>({{ post.date | date_to_string }})</small></h1>
  <!-- very good post about date formatting in Jekyll: http://joshbranchaud.com/blog/2012/12/24/Date-Formatting-in-Jekyll.html -->
  {{ post.content | split: '<!-- more -->' | first }}
  <hr>
{% endfor %}
