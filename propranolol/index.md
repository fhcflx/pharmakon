---
layout: page
title: Propranolol
---

<div>
<ul>
{% for post in site.tags.propranolol %}
  <li>
    {{ post.date | date: "%B %d, %Y" }}: <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
  </li>
{% endfor %}
</ul>
</div>
