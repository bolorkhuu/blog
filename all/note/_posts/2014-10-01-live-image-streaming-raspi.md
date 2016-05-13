---
published: true
layout: default
title: live image streaming via raspberry-pi 
---
<div id="home">
  <ul class="posts">
    {% for post in site.categories.projects %}
      <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
</div>
<p class="publish_date"> 2014.10.01</p>

<p>on Raspberry Pi Webserver WebCam Streaming.</p>
<p>It was being tested well on safari and firefox,</p>
<p>But it doesn't work on google chrome.</p>
<iframe src="http://141.30.229.247:8081/?action=stream" height="500" width="660" frameborder="0"></iframe>

vlc player supports image streaming like below.
<p></p>
<img src="{{ site.url }}{{ site.baseurl }}/images/vlc_webcam.png" style="width:426px;height:290px;border:solid 9px #e3e3e3;" />