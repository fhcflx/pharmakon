---
layout: post
title: All
lang: en
ref: all
---

<div class="home">


  <h1 class="content-listing-header sans">Articles</h1>
  <ul class="content-listing ">
  {% assign posts=site.posts | where:"lang", page.lang %}
    {% for post in posts %}
        <li class="listing">
          <hr class="slender">
          <a href="{{ post.url | prepend: site.baseurl }}"><h3 class="contrast">{{ post.title }}</h3></a>
          <br><span class="smaller">{{ post.date | date: "%d/%m/%Y" }}</span>  <br/>
        </li>
    {% endfor %}
  </ul>

</div>
