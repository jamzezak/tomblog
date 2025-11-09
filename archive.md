---
layout: page
title: Blog Archive
permalink: /archive.html
---

<div class="archive">
  <h1>Blog Archive</h1>
  <p class="archive-intro">Browse posts by month.</p>

  {%- assign posts_desc = site.posts | sort: "date" | reverse -%}
  {%- assign years = posts_desc | group_by_exp: "post", "post.date | date: '%Y'" -%}

  {%- for year in years -%}
    <h2 class="archive-year">{{ year.name }}</h2>

    {%- comment -%}
      Group by month using "MM-MonthName" so sorting is correct.
    {%- endcomment -%}
    {%- assign months = year.items | group_by_exp: "post", "post.date | date: '%m-%B'" -%}
    {%- assign months = months | sort: "name" | reverse -%}

    {%- for month in months -%}
      {%- assign parts = month.name | split: "-" -%}
      {%- assign month_num = parts[0] -%}
      {%- assign month_name = parts[1] -%}

      <h3 class="archive-month" id="{{ year.name }}-{{ month_num }}">{{ month_name }}</h3>
      <ul class="archive-list">
        {%- assign posts_in_month = month.items | sort: "date" | reverse -%}
        {%- for post in posts_in_month -%}
          <li>
            <a href="{{ post.url | relative_url }}">
              <span class="archive-date">{{ post.date | date: "%b %d" }}</span>
              <span class="archive-title">— {{ post.title }}</span>
            </a>
          </li>
        {%- endfor -%}
      </ul>
    {%- endfor -%}
  {%- endfor -%}
</div>
