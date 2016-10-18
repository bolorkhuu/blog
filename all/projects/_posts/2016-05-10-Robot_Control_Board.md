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

This is a robot controller board **MarBoard v1**, a further development of the currently using board **MarBoard v0** on my self balancing robot **MarBot**. I have made many updates to my custom robot controller board recently. It does work very well. Unfortunately the micro usb socket has brocken newly, i cut the micro usb cabel and soldered it to the pins as you can see it in the pictures below.

<p> <img src="{{ site.url }}{{ site.baseurl }}/images/marbot/marboardv1.gif" style="width:550px;height:360px;border:solid 9px #e3e3e3;" />
</p>


This is an overview of the schematic:
<img src="{{ site.baseurl }}/images/marbot/sch.png" alt="Drawing" style="width: 600px;"/>

<img src="{{ site.baseurl }}/images/marbot/marboardv1sc.png" alt="Drawing" style="width: 550px;"/>

<img src="{{ site.baseurl }}/images/marbot/marboardv1_ov.jpg" alt="Drawing" style="width: 560px;"/>

