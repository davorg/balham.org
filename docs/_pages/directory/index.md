---
title: "Business Directory"
permalink: /directory/
layout: single
description: "Explore local businesses in Balham, including cafés, restaurants, shops, and services — all in one place."
---

<ul>
  {% for biz in site.data.businesses %}
    <li>
      <h2>{{ biz.name }}</h2>
      <p><strong>Category:</strong> {{ biz.category }}</p>
      <p><strong>Address:</strong> {{ biz.address }}</p>
      {% if biz.website and biz.website | site > 0 %}
        <p><a href="{{ biz.website }}" target="_blank">Visit Website</a></p>
      {% endif %}
      <p>{{ biz.description }}</p>
    </li>
    <hr>
  {% endfor %}
</ul>

