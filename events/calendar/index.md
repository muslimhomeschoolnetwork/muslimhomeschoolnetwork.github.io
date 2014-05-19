---
layout: calendar
title: Calendar of Events
---

{% for event in site.categories.calendar %}
    {{event.title}} - {{event.venue}}
{% endfor %}

<div id="calendar"></div>