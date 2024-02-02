---
layout: default
title:
description:
---

{% assign organizers = site.data.people | where:'role', 'organizer' | sort: "nick" %}

{% assign presenters2023sep = site.data.people | where_exp: "person", "person.role contains 'presenter-2023-09'" | sort: "nick" %}
{% assign panelists2023sep = site.data.people | where_exp: "person", "person.role contains 'panelist-2023-09'" | sort: "nick" %}


# Organizers
---
{% for person in organizers %}

  {% include person.html %}

{% endfor %}


# September 2023 Seminar
---

## Presenters

{% for person in presenters2023sep %}

  {% include person.html %}

{% endfor %}

<!-- ## Panelists

{% for person in panelists2023sep %}

  {% include person.html %}

{% endfor %} -->
