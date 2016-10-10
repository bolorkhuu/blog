---
published: true
layout: default
title: Robot Control Board
---

During my studies at TU-Dresden i've been working on these projects below and also developed my favorite robot-project **Balancing Robot** called **MarBot** with the great help of the control system department TU-Dresden.

<div id="home">
  <ul class="posts">
    {% for post in site.categories.projects %}
      <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
</div>
<p class="publish_date"> updated: 22.08.2016</p>
