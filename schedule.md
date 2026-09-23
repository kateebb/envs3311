---
layout: default
title: Schedule
---

Edit `_data/schedule.yml` to update this table. Schedule is subject to change.

<div class="table-scroll">
<table class="schedule">
  <thead>
    <tr><th>Wk</th><th>Date</th><th>Topic</th><th>Materials</th><th>Reading</th><th>Due</th></tr>
  </thead>
  <tbody>
  {% for c in site.data.schedule %}
    <tr>
      <td>{{ c.week }}</td>
      <td class="nowrap">{{ c.date }}</td>
      <td>{{ c.topic }}</td>
      <td>
        {% if c.notes != "" %}<a href="{{ c.notes | relative_url }}">Notes</a>{% endif %}
        {% if c.slides != "" %}<a href="{{ c.slides | relative_url }}">Slides</a>{% endif %}
      </td>
      <td>{{ c.reading }}</td>
      <td>{% if c.due != "" %}<span class="due">{{ c.due }}</span>{% endif %}</td>
    </tr>
  {% endfor %}
  </tbody>
</table>
</div>
