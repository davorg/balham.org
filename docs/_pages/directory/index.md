---
title: "Business Directory"
permalink: /directory/
layout: single
description: "Discover great cafés, shops, and services in Balham — all in one place."
---

{% assign categories = site.data.businesses | map: "category" | uniq | sort %}
{% for cat in categories %}
  <h2>{{ cat }}</h2>
  <ul>
    {% for biz in site.data.businesses %}
      {% if biz.category == cat %}
        <li id="{{ biz.name | slugify }}">
          <h3>{{ biz.name }}</h3>
          <p><strong>Address:</strong> {{ biz.address }}</p>
          {% if biz.website != nil and biz.website != "" %}
            <p><a href="{{ biz.website }}" target="_blank">Visit Website</a></p>
          {% endif %}
          <p>{{ biz.description }}</p>
        </li>
      {% endif %}
    {% endfor %}
  </ul>
{% endfor %}
