---
title:  "Blog"
layout: archive
permalink: /blog/
author_profile: true
comments: false
---

My knowledge, revised and presented with the key information for you in a beautiful blog post.

<input type="text" id="search-input" placeholder="search posts..">
<br/>
<div id="results-container"></div>

<ul>
  {% for post in site.posts %}
    {% unless post.next %}
      <font color="#373e5e"><h2>{{ post.date | date: '%Y %b' }}</h2></font>
    {% else %}
      {% capture year %}{{ post.date | date: '%Y %b' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y %b' }}{% endcapture %}
      {% if year != nyear %}
        <font color="#373e5e"><h2>{{ post.date | date: '%Y %b' }}</h2></font>
      {% endif %}

    {% endunless %}
   {% include archive-single.html %}
  {% endfor %}
</ul>
