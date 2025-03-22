---
title: "Welcome to Balham.org - Your Local SW12 Guide"
description: "Explore the best of Balham — local businesses, events, and stories from SW12."
layout: single
permalink: /
classes: wide
---

![Map of Balham](/images/map.png){: .responsive-map }

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

{% assign featured_businesses = site.data.featured.businesses %}
{% assign featured_events = site.data.featured.events %}

{% for biz_name in featured_businesses %}
  {% assign biz = site.data.businesses | where: "name", biz_name | first %}
  {% if biz %}
  ### 🏪 [{{ biz.name }}](/directory/#{{ biz.name | slugify }})
  {{ biz.description }}
  {% endif %}
{% endfor %}

{% for event_name in featured_events %}
  {% assign event = site.data.events | where: "name", event_name | first %}
  {% if event %}
  ### 🎉 [{{ event.name }}](/events/#{{ event.name | slugify }})
  {{ event.description }}
  {% endif %}
{% endfor %}

---

## 📬 Get Involved

Got a business to list? An event to share? A bit of Balham history to
contribute? [Email us](mailto:hello@balham.org) — we’d love to hear from
you.

---

We’re just getting started. Stick around as we continue building the best
little local site Balham has ever seen.

