---
layout: page
title: Leetcode
description: leetcode coding notes
keywords: leetcode, coding, data struture, algorithms
comments: true
menu: Leetcode
permalink: /leetcode/
---
# Connect
<div class="btn-inline">
{% for website in site.data.social %}
<a href="{{ website.url }}" class="btn btn-outline" type="button">{{ website.sitename }}</a>
{% endfor %}
</div>

# Skill Keywords
{% for category in site.data.skills %}
### {{ category.name }}
<div class="btn-inline">
{% for keyword in category.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}
