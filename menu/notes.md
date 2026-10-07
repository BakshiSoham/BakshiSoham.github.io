---
layout: default
title: Notes
permalink: /notes
---

<h1>Research Notes</h1>

<p>Working notes on the problems behind my papers: definitions, short derivations,
conventions and open questions. They are less polished than a paper and may be
revised as the work develops.</p>

<ul class="note-list">
  {%- assign notes = site.notes | sort: "date" | reverse %}
  {%- for note in notes %}
  <li>
    <span class="post-date">{{ note.date | date: "%b %-d, %Y" }}</span>
    <a href="{{ site.github.url }}{{ note.url }}">{{ note.title }}</a>
    {%- if note.description %}
    <p>{{ note.description }}</p>
    {%- endif %}
  </li>
  {%- endfor %}
</ul>
