---
layout: post
title: All
lang: en
ref: all
---

<div class="home">


  <h1 class="content-listing-header sans">Artigos</h1>
  <ul class="content-listing ">
  {% assign posts=site.posts | sort: 'lang' %}
    {% for post in posts %}
        <li class="listing">
          <hr class="slender">
          <a href="{{ post.url | prepend: site.baseurl }}"><h3 class="contrast">{{ post.title }}</h3></a>
          <br><span class="smaller">{{ post.date | date: "%d/%m/%Y" }}</span>  <br/>
        </li>
    {% endfor %}
  </ul>

</div>
