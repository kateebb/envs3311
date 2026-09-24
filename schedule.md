---
layout: default
title: Schedule
---

<style>
  /* ---- Unit banner colors: banners cycle through these 5 in order ----
     Change any color code to adjust it, or set "unit_color:" on a unit
     in _data/schedule.yml to override the color of that one banner. */
  .schedule .unit-1 td { background: #2f6b4f; }  /* forest green */
  .schedule .unit-2 td { background: #0b6e79; }  /* teal */
  .schedule .unit-3 td { background: #5c5a8a; }  /* muted violet */
  .schedule .unit-4 td { background: #a4461d; }  /* rust */
  .schedule .unit-0 td { background: #4a5a6a; }  /* slate (5th unit) */

  .schedule .unit-row td { color: #ffffff; padding: 12px 14px; border-bottom: none; }
  .schedule .unit-row .unit-title { font-family: var(--font-heading, inherit); font-weight: 700; font-size: 1.08em; }
  .schedule .unit-row .unit-desc { font-size: 0.9em; opacity: 0.92; }
  .schedule tr.unit-row:not(:first-child) td { border-top: 18px solid var(--bg, #fff); }

  /* Spring break / no-class rows */
  .schedule .break-row td { background: #e9ece4; color: #5a6659; font-style: italic; font-weight: 600; }
</style>

Schedule is subject to change. (To edit, update `_data/schedule.yml`.)

<div class="table-scroll">
<table class="schedule">
  <thead>
    <tr><th>Wk</th><th>Date</th><th>Topic</th><th>Materials</th><th>Reading</th><th>Due</th></tr>
  </thead>
  <tbody>
  {% assign u = 0 %}
  {% for c in site.data.schedule %}
    {% if c.unit and c.unit != "" %}
    {% assign u = u | plus: 1 %}
    <tr class="unit-row unit-{{ u | modulo: 5 }}">
      <td colspan="6"{% if c.unit_color and c.unit_color != "" %} style="background: {{ c.unit_color }};"{% endif %}>
        <span class="unit-title">{{ c.unit }}</span>
        {% if c.unit_desc and c.unit_desc != "" %}<br><span class="unit-desc">{{ c.unit_desc }}</span>{% endif %}
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
