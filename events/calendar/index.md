---
layout: default
title: Calendar of Events
---

{% for event in site.categories.calendar %}
    {{event.title}} - {{event.venue}}
{% endfor %}
