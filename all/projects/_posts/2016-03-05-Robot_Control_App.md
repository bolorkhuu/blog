---
published: true
layout: default
title: Robot Control App
---

During my studies at TU-Dresden i've been working on these projects below and also developed my favorite robot-project **Balancing Robot** called **MarBot** with the great help of the control system department TU-Dresden.

<div id="home">
  <ul class="posts">
    {% for post in site.categories.projects %}
      <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
</div>

<p class="publish_date"> updated: 12.09.2016</p>

This is a android app for bluetooth remote controlling for my self balancing robot **MarBot** written in java using android studio. I made it with my friend Dmitry.


<img src="{{ site.baseurl }}/images/marbot/app/img1.jpg" alt="Drawing" style="width: 500px;"/>

<img src="{{ site.baseurl }}/images/marbot/app/img2.jpg" alt="Drawing" style="width: 500px;"/>

Source code is downloadable on my [GitHub repository](https://github.com/bolorkhuu/marbot-control).