---
layout: default
title: Quotes
permalink: /quotes
---

<h1>Quotes</h1>

<p class="quotes-intro">Lines I keep coming back to.</p>

<ul class="quote-list">
  {%- for q in site.data.quotes %}
  <li>
    <blockquote class="quote">
      <p>{{ q.text | strip }}</p>
      <footer>&mdash; {{ q.author }}
        {%- if q.born %} ({{ q.born }}&ndash;{% if q.died %}{{ q.died }}{% endif %}){% endif %}
        {%- if q.note %}<span class="quote-note">{{ q.note }}</span>{% endif %}
      </footer>
    </blockquote>
  </li>
  {%- endfor %}
</ul>
