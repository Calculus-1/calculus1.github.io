---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% assign last_year = "" %}
{% for post in site.publications reversed %}
{% capture current_year %}{{ post.date | default: "1900-01-01" | date: "%Y" }}{% endcapture %}
{% if current_year != last_year %}

<h2 class="archive__item-pub-year">
{{ post.date | default: "1900-01-01" | date: "%Y" }}
</h2>

{% endif %}
{% include archive-single.html %}
{% capture last_year %}{{ post.date | default: "1900-01-01" | date: "%Y" }}{% endcapture %}
{% endfor %}
