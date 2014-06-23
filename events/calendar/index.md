---
layout: default
title: Calendar of Events
extra_css: |
    <link rel="stylesheet" href="//cdnjs.cloudflare.com/ajax/libs/fullcalendar/2.0.1/fullcalendar.css">
    <link rel="stylesheet" href="//cdnjs.cloudflare.com/ajax/libs/fullcalendar/2.0.1/fullcalendar.print.css">
extra_js: |
    <script src="//cdnjs.cloudflare.com/ajax/libs/moment.js/2.6.0/moment.min.js"></script>
    <script src="//cdnjs.cloudflare.com/ajax/libs/fullcalendar/2.0.1/fullcalendar.min.js"></script>
    <script type="text/javascript">
    $(function () {
        $('#calendar').fullCalendar(window.calendarOptions());
    });
    </script>
---


<script type="text/javascript">
    window.calendarOptions = function () {
        var opts = {};
        opts.events = [
            {% for event in site.categories.calendar %}
            {
                title: {{event.title | jsonify }},
                start: "{{event.date | date: "%F" }}T" + {{event.start | jsonify}},
                end: "{{event.date | date: "%F" }}T" + {{event.end | jsonify}},
                url: {{event.url | jsonify }}
            }
            {% if forloop.last == false %},{% endif %}
            {% endfor %}
        ];
        return opts;
    };
</script>

<div id="calendar"></div>
