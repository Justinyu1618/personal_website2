---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: default
title: Blog
permalink: /blog/
---

<div id="blog">
<div id="page-header">
  <p>In 2022, I started a habit of obssessively writing all of my thoughts down. <br/>
  Here's a loose collection of what I'm thinking about</p>
</div>

<div id="post-list-container">
  {% for post in site.posts %}
  {% assign currentdate = post.date | date: "%Y" %}
  {% if currentdate != date %}
    <h4 id="y{{currentdate}}">{{ currentdate }}</h4>
    {% assign date = currentdate %}
    {% endif %}
    <div id="post-li">
      <a href="{{site.url}}{{site.baseurl}}{{post.url}}">
        <h5>{{post.title}}</h5>
        <i> {{ post.date | date: "%b %-d" }} | {% for category in post.categories %} #{{category}}  {% endfor %} </i>
      </a>
    </div>

{% endfor %}

</div>
</div>
