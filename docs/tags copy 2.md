---
layout: null
---

{% assign tags_posts = site.posts | map: 'tags' | join: ',' | join: ',' | split: ',' | uniq | sort %} 



{% assign tags_pages = site.pages | map: 'tags' | join: ',' | join: ',' | split: ',' | uniq | sort %} 

{% assign combo = tags_posts | concat: tags_pages | uniq | sort %} 



[
    {% for tag in combo %}
    {"label": "[{{tag}}]",
    "value": "[{{tag}}]"}
    {% unless forloop.last %},{% endunless %}
  {% endfor %}
    ]

  
