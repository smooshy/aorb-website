---
layout: page
title: Events
share-title: Events at Aikido of Red Bank
---

<!-- role="list" needed so that `list-style: none` in Safari doesn't remove the list semantics -->
<ul class="posts-list list-unstyled" role="list">
  {%- assign valid_events = site.posts | where_exp: 'item', 'item.event-date > site.time'  | sort: 'event-date' -%}
  {% for event in valid_events %}
  <li class="post-preview">
    <article>

      <h2 class="post-title">{{ event.title | strip_html }}</h2>

      <h3 class="post-subtitle">
        {{ event.event-date | date: "%B %-d, %Y" }}
      </h3>

      <div class="post-entry">
        <div class="container">
            <div class="row">
                <div class="col">
                    {{ event.content }}
                </div>
            </div>
            <div class="row">
                <div class="col">
                    <img src="{{ event.flyer-image | relative_url }}" alt="Flyer for {{ event.title }} event" />
                </div>
            </div>
        </div>
      </div>
    </article>
  </li>
  {% endfor %}
</ul>