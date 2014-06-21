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
        $('#calendar').fullCalendar(window.calendarOptions);
    });
    </script>
---


<script type="text/javascript">
    window.calendarOptions = {
        events: [
            {% for event in site.categories.calendar %}
            {
                title: {{event.title | jsonify }},
                start: {{event.date | jsonify }},
                end: "",
                url: {{event.url | jsonify }}
            }
            {% if forloop.last == false %},{% endif %}
            {% endfor %}
        ]
    };
</script>

<div id="calendar"></div>
