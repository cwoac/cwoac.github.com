---
layout: default
title: index
---
#{{ page.title }}

Frankly, this is just test data while I (@cwoac) get to grips with the github pipeline.

{% for post in site.posts %}
* [{{ post.title }}]({{ post.url}}) : {{ post.excerpt }}
{% endfor %}
