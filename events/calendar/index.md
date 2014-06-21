---
layout: default
title: Calendar of Events
extra_css: |
    <link rel="stylesheet" href="//cdnjs.cloudflare.com/ajax/libs/fullcalendar/1.6.4/fullcalendar.css">
    <link rel="stylesheet" href="//cdnjs.cloudflare.com/ajax/libs/fullcalendar/1.6.4/fullcalendar.print.css">
extra_js: |
    <script src="//cdnjs.cloudflare.com/ajax/libs/fullcalendar/1.6.4/fullcalendar.min.js"></script>
    <script type="text/javascript">
    $(function () {
        $('#calendar').fullCalendar({});
    });
    </script>
---

{% for event in site.categories.calendar %}
    {{event.title}} - {{event.venue}}
{% endfor %}

<div id="calendar"></div>
