---
layout: default
title: Staff & Office Hours
---

<div class="staff">
{% for p in site.data.staff %}
  <div class="person">
    {% if p.photo != "" %}<img src="{{ p.photo | relative_url }}" alt="{{ p.name }}">{% else %}<div class="avatar">{{ p.name | slice: 0 }}</div>{% endif %}
    <div>
      <strong>{{ p.name }}</strong><br>
      <span class="role">{{ p.role }}</span><br>
      <a href="mailto:{{ p.email }}">{{ p.email }}</a><br>
      <span class="hours">{{ p.hours }}</span>
    </div>
  </div>
{% endfor %}
</div>
