---
layout: post
title: Todas as postagens, ordem cronológica
---

<div class="home">


  <h1 class="content-listing-header sans">Artigos</h1>
  <ul class="content-listing ">
    {% for post in site.posts %}
        <li class="listing">
          <hr class="slender">
          <a href="{{ post.url | prepend: site.baseurl }}"><h3 class="contrast">{{ post.title }}</h3></a>
          <br><span class="smaller">{{ post.date | date: "%B %-d, %Y" }}</span>  <br/>
        </li>
    {% endfor %}
  </ul>

</div>
