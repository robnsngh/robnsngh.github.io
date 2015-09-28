---
layout: page
title: Archive
---

<h3> Timeline </h3>


{% comment %}
  {% for post in site.posts %}
      {% capture month %}{{ post.date | date: '%m%Y' }}{% endcapture %}
      {% capture nmonth %}{{ post.next.date | date: '%m%Y' }}{% endcapture %}
          {% if month != nmonth %}
              {% if forloop.index != 1 %}</ul>{% endif %}
              <h3>{{ post.date | date: '%B %Y' }}</h3><ul>
          {% endif %}
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
      <time>{{ post.date | date: "%e %B %Y" }}</time>
  {% endfor %}

{% endcomment %}


{% for post in site.posts %}
  {% capture month %}{{ post.date | date: '%m%Y' }}{% endcapture %}
  {% capture nmonth %}{{ post.next.date | date: '%m%Y' }}{% endcapture %}

  {% if month != nmonth %}
  {% if forloop.index != 1 %}  {% endif %}
    <h3>{{ post.date | date: '%B %Y' }}</h3>
  {% endif %}
  <li><a href="{{ post.url }}"> {{ post.title }} </li>
  <time> {{ post.date | date: '%e %B %Y'}} </time>
{% endfor %}
