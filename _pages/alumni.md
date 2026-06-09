---
layout: page
permalink: /alumni/
title: alumni
description: previous members of the lab
nav: true
nav_order: 8
---


{% assign phd = site.data.alumni_phd %}
{% assign msc = site.data.alumni_msc %}

## Alumni

<div style="
  margin-bottom: 20px;
  padding: 12px 16px;
  border-left: 4px solid #4c72b0;
  background-color: #f8f9fa;
">

<strong>Supervision Summary</strong><br>

- 🎓 PhD students: <strong>{{ phd.size }}</strong>  
- 📘 MSc students: <strong>{{ msc.size }}</strong>

</div>


## PhD Alumni

<div style="margin-top: 20px;">

{% assign phd = site.data.alumni_phd | sort: "end" | reverse %}

{% for s in phd %}

<div style="margin-bottom: 14px;">
  <strong> 
{% assign total = phd.size %}

<span style="display:inline-block; width: 2.2em; color:#888;">
  {{ total | minus: forloop.index0 }}.
</span>
</strong>
  <strong style="color:#4c72b0;">
    {{ s.start }}{% if s.end %}–{{ s.end }}{% endif %}
  </strong> — {{ s.name }}

  <div style="font-size: 0.95em;">
    {% if s.link %}
      <a href="{{ s.link }}">{{ s.title }}</a>
    {% else %}
      {{ s.title }}
    {% endif %}
    <br>
    <em>({{ s.role }})</em>
  </div>
</div>

{% endfor %}

</div>

---

## MSc Alumni
<div style="margin-top: 20px;">

{% assign all_msc = site.data.alumni_msc | sort: "year" | reverse %}

<ul style="list-style: none; padding-left: 0;">

{% for s in all_msc %}

<li style="margin-bottom: 10px;">
  <strong> 
{% assign total = msc.size %}

<span style="display:inline-block; width: 2.2em; color:#888;">
  {{ total | minus: forloop.index0 }}.
</span></strong>

  <span style="color:#4c72b0;">{{ s.year }}</span> — {{ s.name }}<br>

  <span style="font-size: 0.95em;">
    {% if s.link %}
      <a href="{{ s.link }}">{{ s.title }}</a>
    {% else %}
      {{ s.title }}
    {% endif %}
    <br>
    <em>({{ s.role }})</em>
  </span>
</li>

{% endfor %}

</ul>

</div>