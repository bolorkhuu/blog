---
published: true
layout: default
title: Balancing Robot
---

During my studies at TU-Dresden i've been working on these projects below and also developed my favorite robot-project **Balancing Robot** called **MarBot** with the great help of the control system department TU-Dresden.


<div id="home">
  <ul class="posts">
    {% for post in site.categories.projects %}
      <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
</div>



<p class="publish_date"> updated: 01.10.2016</p>



A balancing robot is a interesting example in field of control system. Marmot-Robot briefly **MarBot** is a half autonomous robot with 2, 12V DC maxon geared motors with a quadrature encoder and a IMU (Accelerometer + Gyroscope) that can go forward, backward and turn while balancing. It uses 2 multidimensional Kalman-Filter to predict tilt angle of the robot and also the pose (acceleration, velocity, position) of the 2 wheels. I spent the last 3 years working on this project while studying. 

As yet i've built 6 MarBots. The TU-Dresden as well as the UMIT Hall in Tirol Austria own 2 exemplar of the MarBot as a test station for education purpose.

<p></p><p></p>

### MarBot in motion:
<iframe width="560" height="400" src="https://www.youtube.com/embed/hTNNsko_t8o" frameborder="0" allowfullscreen></iframe>

<p></p><p></p>
<p></p><p></p>


<iframe width="560" height="400" src="https://www.youtube.com/embed/jPH4uLOQLpM" frameborder="0" allowfullscreen></iframe>

<p></p><p></p>

### Parts list:

  * 1 x STM32F407 Microcontroller
  * 2 x XBee S2B ZigBee Pro 10mW
  * 2 x VNH5019 Motor Driver
  * 1 x IMU ADXL345 + IMU3000
  * 4 x Threaded Rod M3
  * 1 x 12V, 3800mAh NiMh Battery-Pack
  * 2 x Reely Balloon Tyre
  * 3 x Acrylic Glass
  * 2 x Maxon Geared Motor with a 2 Channel Quadrature Encoder 9W.


The Controller Motherboard **Marboard v0** below is currently being in use on the robot, which is created with KiCad:


<img src="{{ site.baseurl }}/images/marbot/marboardv01.png" alt="Drawing" style="width: 560px;"/>
<img src="{{ site.baseurl }}/images/marbot/project.png" alt="Drawing" style="width: 580px;"/>
<img src="{{ site.baseurl }}/images/marbot/marboardv0.png" alt="Drawing" style="width: 560px;"/>

The **MarBoard v0** has been further developed and will be replaced soon with **MarBoard v1**.

<img src="{{ site.baseurl }}/images/marbot/marboardv1_ov.jpg" alt="Drawing" style="width: 560px;"/>


### State control simulation:

I used **python** for the kinematic simulation with **numpy**, **sympy** and also **matplotlib**.

<p> <img src="{{ site.url }}{{ site.baseurl }}/images/pendel4g.gif" style="width:550px;height:360px;border:solid 9px #e3e3e3;" />
</p>

<p> <img src="{{ site.url }}{{ site.baseurl }}/images/pendel7g.gif" style="width:550px;height:360px;border:solid 9px #e3e3e3;" />
</p>

### Some pictures of the MarBot:

<img src="{{ site.baseurl }}/images/marbot/marbots_table.jpg" alt="Drawing" style="width: 550px;"/>
<img src="{{ site.baseurl }}/images/marbot/marbots_table1.JPG" alt="Drawing" style="width: 550px;"/>
<img src="{{ site.baseurl }}/images/marbot/marbots_table2.JPG" alt="Drawing" style="width: 550px;"/>
<img src="{{ site.baseurl }}/images/marbot/marbots_table3.jpeg" alt="Drawing" style="width: 550px;"/>

I'm a great fan of South Park. Therefore i've put a little suit on MarBot.

<img src="{{ site.baseurl }}/images/marbot/awesomo.jpg" alt="Drawing" style="width: 550px;"/>


### Some technical drawing of the MarBot:

<img src="{{ site.baseurl }}/images/marbot/drawing/MittlerePlatte.png" alt="Drawing" style="width: 600px;"/>
<img src="{{ site.baseurl }}/images/marbot/drawing/OberstePlatte.png" alt="Drawing" style="width: 600px;"/>
<img src="{{ site.baseurl }}/images/marbot/drawing/UnterePlatte.png" alt="Drawing" style="width: 600px;"/>
<img src="{{ site.baseurl }}/images/marbot/drawing/Motorhalterung.png" alt="Drawing" style="width: 600px;"/>


