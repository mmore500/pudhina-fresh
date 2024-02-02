---
layout: page
full_logo: true
title:
subtitle:
description:
sitemap:
  priority: 1.0
---

***bI/O*** is a prison seminar outreach program coordinated by scientists at the [University of Michigan](https://umich.edu) to engage with the Parnall Correctional Facility in Jackson, MI.
We work with prison officials to schedule sessions 2-3 times per semester.
Each session, a panel of 3 researchers present a **15-20 minute talk about their science and career path** in a **seminar-style format**.
Organizers workshop presentation materials with presenters to make sure it is accessible and follows the strict guidelines of the correctional facility.
After the talks, we open up for a **discussion panel** where incarcerated students will be able to ask us further **questions about science, careers, etc.**

*See below for a listing of our past and upcoming seminars and presenters.*

{% assign seminars = site.data.presentations | sort: "seminar" | map: "seminar" | uniq %}

{% for seminar in seminars %}
  <h1> {{ seminar }} </h1>
  ---

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
