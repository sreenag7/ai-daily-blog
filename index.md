---
layout: default
---

<div class="home">
  <h1 class="page-heading">AI Daily Insights</h1>
  
  <p>Welcome to AI Daily Insights! This blog features daily posts about trending topics, automatically generated and curated by AI.</p>

  <div class="post-list">
    {% for post in site.posts limit:10 %}
      <article class="post-preview">
        <h2>
          <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title | escape }}</a>
        </h2>
        
        {% if post.image %}
        <img src="{{ post.image }}" alt="{{ post.title }}" style="width: 100%; max-width: 600px; height: auto; margin: 10px 0;">
        {% endif %}
        
        <p class="post-meta">
          <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
          {% if post.author %} • {{ post.author }}{% endif %}
        </p>
        
        {% if post.description %}
        <p>{{ post.description }}</p>
        {% endif %}
        
        <p><a href="{{ post.url | relative_url }}">Read more →</a></p>
      </article>
      <hr>
    {% endfor %}
  </div>

  <p class="rss-subscribe">Subscribe <a href="{{ "/feed.xml" | relative_url }}">via RSS</a></p>
</div>
