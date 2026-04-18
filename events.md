---
layout: default
title: Events
permalink: /events/
---

<a href="/"><img src="/img/java_forum_malmo_512x512.png" height="200"></a>

## Events

Javaforum Malmö arranges physical meetups with local and international speakers approximately once every quarter.
Join our [mailing list](https://groups.google.com/g/javaforum-malmo) or follow us on social media so you don't miss out on upcoming events.

{% assign today = site.time | date: "%Y-%m-%d" %}
{% assign upcoming = site.data.events | where_exp: "event", "event.date >= today" | sort: "date" %}
{% assign past = site.data.events | where_exp: "event", "event.date < today" | sort: "date" | reverse %}

{% if upcoming.size > 0 %}
### Upcoming Events

{% for event in upcoming %}
#### {{ event.title }}

| | |
|---|---|
| **Date** | {{ event.date | date: "%B %-d, %Y" }} |
| **Time** | {{ event.time }} |
| **Location** | {{ event.location }} |

{{ event.description }}

{% if event.speaker_name %}**{{ event.speaker_name }}** - {% endif %}{% if event.speaker_bio %} {{ event.speaker_bio }}{% endif %}

{% if event.registration_url %}[Register now]({{ event.registration_url }}){%- endif %}

---
{% endfor %}
{% else %}
*No upcoming events at the moment. Check back soon!*

---
{% endif %}

{% if past.size > 0 %}
### Past Events

{% for event in past %}
#### {{ event.title }}

| | |
|---|---|
| **Date** | {{ event.date | date: "%B %-d, %Y" }} |
| **Time** | {{ event.time }} |
| **Location** | {{ event.location }} |

{{ event.description }}

{% if event.speaker_name %}**{{ event.speaker_name }}** - {% endif %}{% if event.speaker_bio %} {{ event.speaker_bio }}{% endif %}

---
{% endfor %}
{% endif %}

[← Back to home](/)
