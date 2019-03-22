---
layout: post
title: All
lang: en
ref: all
---

<div class="home">


  <h1 class="content-listing-header sans">Articles</h1>
  <ul class="content-listing">
  {% assign posts=site.posts | where:"lang", "pt-br" %}
  {% for default in posts %}
  {% assign translation = site.posts | where:"ref", default.ref | where:"lang", "en" %}
  {% if translation[0] %}
    <li class="listing">
      <hr class="slender">
      <a href="{{ translation[0].url | prepend: site.baseurl }}"><h3 class="contrast">{{ translation[0].title }}</h3></a>
      <br><span class="smaller">{{ post.date | date: "%d/%m/%Y" }}</span>  <br/>
    </li>
  {% else %}
    <li class="listing">
      <hr class="slender">
      <a href="{{ default.url | prepend: site.baseurl }}"><h3 class="contrast">{{ default.title }}</h3></a> [pt-br] 
      <br><span class="smaller">{{ post.date | date: "%d/%m/%Y" }}</span>  <br/>
    </li>
  {% endif %}
  {% endfor %}
  </ul>
  <!--<ul class="content-listing ">
  {% assign posts=site.posts | where:"lang", en %}
    {% for post in posts %}
        <li class="listing">
          <hr class="slender">
          <a href="{{ post.url | prepend: site.baseurl }}"><h3 class="contrast">{{ post.title }}</h3></a>
          <br><span class="smaller">{{ post.date | date: "%d/%m/%Y" }}</span>  <br/>
        </li>
    {% endfor %}
  </ul>-->

</div>
