---
layout: default
title: index
---
#{{ page.title }}

Frankly, this is just test data while [I][cwoac] get to grips with the github pipeline.

{% for post in site.posts %}
* [{{ post.title }}]({{ post.url}}) : {% if post.excerpt %}{{ post.excerpt }}{% else %}&quot;{{ post.content | strip_html | truncatewords:10 }}&hellip;&quot;{% endif %}
{% endfor %}


[cwoac]: https://github.com/cwoac
