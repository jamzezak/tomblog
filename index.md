---
layout: page
title: Making Sense of The Senseless
---

This here will be a blog about some of the most random things I can think of.

Some of them will be poetry, some will be every day to day things, and what not.

Some will be emotionally charged, some will be stupid and silly.

## Posts

<ul class="post-list">
  {%- assign posts_desc = site.posts | sort: "date" | reverse -%}
  {%- for post in posts_desc -%}
    <li>
      <div class="post-meta">{{ post.date | date: "%b %d, %Y %H:%M" }}</div>
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      {%- if post.excerpt -%}
        <p>{{ post.excerpt | strip_html | truncate: 140 }}</p>
      {%- endif -%}
    </li>
  {%- endfor -%}
</ul>
