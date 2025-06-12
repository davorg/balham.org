---
title: "Business Directory"
permalink: /directory/
layout: single
description: "Discover great cafés, shops, and services in Balham — all in one place."
---

---
title: "Business Directory"
permalink: /directory/
layout: single
description: "Discover great cafés, shops, and services in Balham — all in one place."
---

<p><strong>Show categories:</strong></p>
<form id="category-filter">
  {% assign sorted_biz = site.data.businesses | sort: "name" %}
  {% assign categories = sorted_biz | map: "category" | uniq | sort %}
  {% for cat in categories %}
    <label style="margin-right: 1em;">
      <input type="checkbox" checked data-category="{{ cat | slugify }}"> {{ cat }}
    </label>
  {% endfor %}
</form>

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
    const checkboxes = document.querySelectorAll('#category-filter input[type="checkbox"]');
    const categoryBlocks = document.querySelectorAll('.biz-category');

    checkboxes.forEach(checkbox => {
      checkbox.addEventListener('change', () => {
        const category = checkbox.getAttribute('data-category');
        const block = document.querySelector(`.biz-category[data-category="${category}"]`);
        if (checkbox.checked) {
          block.style.display = '';
        } else {
          block.style.display = 'none';
        }
      });
    });
  });
</script>

