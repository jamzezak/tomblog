---
layout: page
---

<p>This here will be a blog about some of the most random things I can think of.</p>

<p>Some of them will be poetry, some will be every day to day things, and what not.</p>

<p>Some will be emotionally charged, some will be stupid and silly.</p>

<h2>Posts</h2>

<ul class="post-list">
  {%- assign posts_desc = site.posts | sort: "date" | reverse -%}
  {%- for post in posts_desc -%}
    <li>
      <div class="post-meta">{{ post.date | date: "%b %d, %Y" }}</div>
      <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
      {%- if post.excerpt -%}
        <p>{{ post.excerpt | strip_html | truncate: 140 }}</p>
      {%- endif -%}
    </li>
  {%- endfor -%}
</ul>
