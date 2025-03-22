---
title: "What's On in Balham"
description: "See what’s on in Balham — gigs, markets, comedy, and more happening near you."
permalink: /events/
layout: single
---

<ul>
  {% for event in site.data.events %}
    <li>
      <h2>{{ event.name }}</h2>
      <p><strong>Date:</strong> {{ event.date }}</p>
      <p><strong>Location:</strong> {{ event.location }}</p>
      <p>{{ event.description }}</p>
      {% if event.link %}
        <p><a href="{{ event.link }}" target="_blank">More info</a></p>
      {% endif %}
    </li>
    <hr>
  {% endfor %}
</ul>

