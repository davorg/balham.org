---
title: "Business Directory"
permalink: /directory/
layout: single
description: "Discover great cafés, shops, and services in Balham — all in one place."
---

<style>
#category-buttons {
  margin: 0.5rem 0 1rem;

  .category-toggle {
    background-color: #f0f0f0;
    border: 1px solid #ccc;
    color: #333;
    padding: 0.2em 0.6em;
    margin: 0.2em 0.3em 0.2em 0;
    border-radius: 4px;
    cursor: pointer;
    font-size: 0.8rem;
    line-height: 1.2;
  }

  .category-toggle.active {
    background-color: #007ACC;
    color: white;
    border-color: #007ACC;
  }

  .category-toggle:hover {
    opacity: 0.9;
  }
}

</style>

<p><strong>Show categories:</strong></p>
<div id="category-buttons">
  {% assign sorted_biz = site.data.businesses | sort: "name" %}
  {% assign categories = sorted_biz | map: "category" | uniq | sort %}
  {% for cat in categories %}
    <button class="category-toggle active" data-category="{{ cat | slugify }}">{{ cat }}</button>
  {% endfor %}
</div>

<hr>

<div id="business-list">
  {% for cat in categories %}
    <div class="biz-category" data-category="{{ cat | slugify }}">
      <h2>{{ cat }}</h2>
      <ul>
        {% for biz in sorted_biz %}
          {% if biz.category == cat %}
            <li id="{{ biz.name | slugify }}">
              <h3>{{ biz.name }}</h3>
              <p><strong>Address:</strong> {{ biz.address }}</p>
              {% if biz.website %}
                <p><a href="{{ biz.website }}" target="_blank">Visit Website</a></p>
              {% endif %}
              <p>{{ biz.description }}</p>
            </li>
          {% endif %}
        {% endfor %}
      </ul>
    </div>
  {% endfor %}
</div>

<script>
  document.addEventListener("DOMContentLoaded", function () {
    const buttons = document.querySelectorAll('.category-toggle');

    buttons.forEach(button => {
      button.addEventListener('click', function () {
        const category = this.getAttribute('data-category');
        const blocks = document.querySelectorAll(`.biz-category[data-category="${category}"]`);
        const isActive = this.classList.toggle('active');

        blocks.forEach(block => {
          block.style.display = isActive ? '' : 'none';
        });
      });
    });
  });
</script>

