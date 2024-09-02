---
layout: page
title: Archive
---

#

Browse all posts by month and year.

{% assign postsByYearMonth = site.posts | group_by_exp: "post", "post.date | date: '%Y-%m'" %}
{% for yearMonth in postsByYearMonth %}
  <h2 class="monospace">{{ yearMonth.name }}</h2>
  <ul>
    {% for post in yearMonth.items %}
      <li><span class="monospace">{{post.date | date: '%d'}}</span> - <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
{% endfor %}
