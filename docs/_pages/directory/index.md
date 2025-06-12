---
title: "Business Directory"
permalink: /directory/
layout: single
description: "Discover great cafés, shops, and services in Balham — all in one place."
---

{% assign sorted_biz = site.data.businesses | sort: "name" %}
{% assign categories = sorted_biz | map: "category" | uniq %}
{% assign categories = categories | sort %}

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
