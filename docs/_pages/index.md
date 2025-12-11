---
title: "Welcome to Balham.org - Your Local SW12 Guide"
description: "Explore the best of Balham — local businesses, events, and stories from SW12."
layout: single
permalink: /
classes: wide
redirect_from:
  - /category/nostalgia/
  - /comments/feed/
  - /old-index.html
  - /profiles/blogs/x-crossing
  - /2017/09/
  - /2017/09/french-cafe-closes/
  - /2017/09/queuing-for-milk/
toc: false
---

![Map of Balham](/images/map.webp){: .responsive-map }

Welcome to **Balham.org** — your independent guide to one of south-west
London's most vibrant neighbourhoods.

Whether you’re a long-time local, a new resident, or just passing through,
we’re here to help you discover the very best of Balham.

---

## 📍 What's Here

### 🛍️ [Business Directory](/directory/)
Explore independent shops, restaurants, cafés, and services — all located
in Balham.

### 📅 [Upcoming Events](/events/)
From comedy nights to craft fairs, here’s what’s on in Balham this week
and beyond.

### 🏛️ [A Short History of Balham](/history/)
Discover how Balham grew from a sleepy hamlet into the lively place it is
today.

---

## 🔥 Featured This Week in Balham

<div class="featured-grid">
  {% assign featured_businesses = site.data.featured.businesses %}
  {% assign featured_events = site.data.featured.events %}

  {% for biz_name in featured_businesses %}
    {% assign biz = site.data.businesses | where: "name", biz_name | first %}
    {% if biz %}
      <div class="featured-block">
        <h3><a href="/directory/#{{ biz.name | slugify }}">🏪 {{ biz.name }}</a></h3>
        <p>{{ biz.description }}</p>
      </div>
    {% endif %}
  {% endfor %}

  {% for event_name in featured_events %}
    {% assign event = site.data.events | where: "name", event_name | first %}
    {% if event %}
      <div class="featured-block">
        <h3><a href="/events/#{{ event.name | slugify }}">🎉 {{ event.name }}</a></h3>
        <p>{{ event.description }}</p>
      </div>
    {% endif %}
  {% endfor %}
</div>

---

## 📬 Get Involved

Got a business to list? An event to share? A bit of Balham history to
contribute? [Email us](mailto:hello@balham.org) — we’d love to hear from
you.

---

We’re just getting started. Stick around as we continue building the best
little local site Balham has ever seen.

