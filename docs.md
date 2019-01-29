---
layout: page
permalink: /docs/
title: Documentation
---

{% for doc in site.docs %}
[{{ doc.title }}]({{doc.url}})
{% endfor %}