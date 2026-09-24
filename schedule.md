---
layout: default
title: Schedule
---

Schedule is subject to change. (To edit, update `_data/schedule.yml`.)

<div class="table-scroll">
<table class="schedule">
  <thead>
    <tr><th>Wk</th><th>Date</th><th>Topic</th><th>Materials</th><th>Reading</th><th>Due</th></tr>
  </thead>
  <tbody>
  {% for c in site.data.schedule %}
    {% if c.unit and c.unit != "" %}
    <tr class="unit-row">
      <td colspan="6">
        <strong>{{ c.unit }}</strong>
        {% if c.unit_desc and c.unit_desc != "" %}<span>{{ c.unit_desc }}</span>{% endif %}
      </td>
    </tr>
    {% endif %}
    {% if c.type == "break" %}
    <tr class="break-row">
      <td>{{ c.week }}</td>
      <td class="nowrap">{{ c.date }}</td>
      <td colspan="4">{{ c.topic }}</td>
    </tr>
    {% else %}
    <tr>
      <td>{{ c.week }}</td>
      <td class="nowrap">{{ c.date }}</td>
      <td>{{ c.topic }}</td>
      <td>
        {% if c.notes and c.notes != "" %}<a href="{{ c.notes | relative_url }}">Notes</a>{% endif %}
        {% if c.slides and c.slides != "" %}<a href="{{ c.slides | relative_url }}">Slides</a>{% endif %}
      </td>
      <td>{{ c.reading }}</td>
      <td>{% if c.due and c.due != "" %}<span class="due">{{ c.due }}</span>{% endif %}</td>
    </tr>
    {% endif %}
  {% endfor %}
  </tbody>
</table>
</div>
