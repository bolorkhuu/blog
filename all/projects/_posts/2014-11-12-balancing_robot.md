---
published: true
layout: default
title: Balancing Robot
---
<div id="home">
  <ul class="posts">
    {% for post in site.categories.projects %}
      <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
</div>
<p class="publish_date"> 2014.11.12</p>

A balancing robot is a common interesting example in field of control system. Marbot is a simple half autonomous robot with 2, 12V DC maxon geared motors and a IMU that can go forward, backward and turn while balancing. 

Some movies of Marbot in motion:

<iframe width="640" height="480" src="https://www.youtube.com/embed/eFX8kx1wI18" frameborder="0" allowfullscreen></iframe>
<iframe width="640" height="480" src="https://www.youtube.com/embed/su7aVd2Gg6g" frameborder="0" allowfullscreen></iframe>


State control simulation:

<p> <img src="{{ site.url }}{{ site.baseurl }}/images/pendel4g.gif" style="width:480px;height:360px;border:solid 9px #e3e3e3;" />
</p>
<p> <img src="{{ site.url }}{{ site.baseurl }}/images/pendel5g.gif" style="width:480px;height:360px;border:solid 9px #e3e3e3;" />
</p>
<p> <img src="{{ site.url }}{{ site.baseurl }}/images/pendel7g.gif" style="width:480px;height:360px;border:solid 9px #e3e3e3;" />
</p>
