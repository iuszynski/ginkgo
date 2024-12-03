---
layout: page
title:
permalink: /people/
---

{% assign people_sorted = (site.people | sort: 'joined' %}
{% assign people_array = "pi|postdoc|gradstudent|engineer|alumni" | split: "|" %}

{% for item in people_array %}

<div class="pos_header">
{% if item == 'postdoc' %}
    <h3>Postdoctoral Fellows</h3>
{% elsif item == 'pi' %}
    <h3>Principal Investigators</h3>
{% elsif item == 'gradstudent' %}
    <h3>Graduate Students</h3>
{% elsif item == 'engineer' %}
    <h3>Research Engineers</h3>
{% elsif item == 'visiting' %}
    <h3>Visiting Scholars</h3>
{% elsif item == 'alumni' %}
    <h3>Alumni</h3>
{% endif %}
</div>

<div class="content list people">
  {% for profile in people_sorted %}
    {% if profile.position contains item %}
    <div style="text-align: left; padding-left: 5em;">
        <a class="name" href="{{site.url}}/{{site.baseurl}}/{{ profile.url }}">{{ profile.name }}</a>
    </div>
    {% endif %}
  {% endfor %}
</div>
<hr>

{% endfor %}
