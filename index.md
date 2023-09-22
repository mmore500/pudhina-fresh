---
layout: page
full_logo: true
title:
subtitle:
description: A minimal yet feature-rich Jekyll theme made for personal websites and blogs.
sitemap:
  priority: 1.0
---

A few words about the program.

{% assign seminars = site.data.presentations | sort: "seminar" | map: "seminar" | uniq %}

{% for seminar in seminars %}
  <h1> {{ seminar }} </h1>

  {% for presentation in site.data.presentations %}
    {% if seminar == presentation.seminar %}
      {% for person in site.data.people %}
        {% if person.key == presentation.person_key %}
{% include presentation.html %}
        {% endif %}
      {% endfor %}
    {% endif %}
  {% endfor %}
{% endfor %}
