---
layout: default
title: Search Results
---

<h1>Search Results for "{{ page.query }}"</h1>

<div class="search-results">
    {% assign results = site.products | where: "title", page.query %}
    {% if results.size > 0 %}
        {% for result in results %}
            <div class="result-item">
                <a href="{{ result.url }}">
                    <img src="{{ result.image }}" alt="{{ result.title }}">
                    <h3>{{ result.title }}</h3>
                </a>
                <p>{{ result.description | truncate: 100 }}</p>
                <p>Price: ${{ result.price }}</p>
            </div>
        {% endfor %}
    {% else %}
        <p>No results found.</p>
    {% endif %}
</div>
