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
<p class="publish_date"> 12.11.2014</p>

A balancing robot is a interesting example in field of control system. Marbot is a half autonomous robot with 2, 12V DC maxon geared motors and a IMU (Accelerometer + Gyroscope) that can go forward, backward and turn while balancing. 

Some movies of Marbot in motion:

<iframe width="600" height="400" src="https://www.youtube.com/embed/AHVHEc2nqg0" frameborder="0" allowfullscreen></iframe>


<p></p><p></p>
<p></p><p></p>

State control simulation:

<p> <img src="{{ site.url }}{{ site.baseurl }}/images/pendel4g.gif" style="width:480px;height:360px;border:solid 9px #e3e3e3;" />
</p>
<!-- <p> <img src="{{ site.url }}{{ site.baseurl }}/images/pendel5g.gif" style="width:480px;height:360px;border:solid 9px #e3e3e3;" />
</p> -->
<p> <img src="{{ site.url }}{{ site.baseurl }}/images/pendel7g.gif" style="width:480px;height:360px;border:solid 9px #e3e3e3;" />
</p>

<!-- 

<p> <img src="{{ site.url }}{{ site.baseurl }}/images/marbot/o1.gif" style="width:480px;height:325px;border:solid 9px #e3e3e3;" />
<p> <img src="{{ site.url }}{{ site.baseurl }}/images/marbot/o2.gif" style="width:480px;height:325px;border:solid 9px #e3e3e3;" />
 -->