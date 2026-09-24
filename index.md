---
layout: default
---

<section class="hero">
  <h1>{{ site.title }}</h1>
  <p class="lead">{{ site.tagline }}</p>
  <p class="meta">{{ site.term }} · {{ site.meeting }} · Instructor: {{ site.instructor }}</p>
</section>

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

## Announcements

- **Jan 10** — Welcome! Please read the [syllabus]({{ '/syllabus/' | relative_url }}) before the first class.
- **Jan 8** — Course website is live.

## Quick links

<div class="cards">
  
  <a class="card" href="{{ '/schedule/' | relative_url }}"><strong>Schedule</strong><span>Topics, readings, due dates</span></a>
  
  <a class="card" href="{{ '/assignments/' | relative_url }}"><strong>Assignments</strong><span>Homework & projects</span></a>
  
  <a class="card" href="{{ '/resources/' | relative_url }}"><strong>Resources</strong><span>Readings & tools</span></a>
  
  <a class="card" href="{{ '/staff/' | relative_url }}"><strong>Office hours</strong><span>Who to ask and when</span></a>
  
</div>

## Disclosure

The formatting and structure of this course website was created with the assistance of Claude Opus 5.5. 
