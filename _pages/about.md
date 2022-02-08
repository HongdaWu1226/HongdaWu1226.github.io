---
permalink: /
title: "About Me"
excerpt: "About Me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

I'm a third-year PhD candidate of dept. [EECS](http://www.eecs.yorku.ca/) at [York University](http://yorku.ca), advised by [Ping Wang](https://scholar.google.com/citations?user=3sIHxrcAAAAJ&hl=en) (IEEE Fellow). My research interests lie in the prinicple of federated learning and its applications for wireless communication systems. I am also very interested in reinforcement learning.  


 I obtained M.A.Sc degree in Electrical Engineering from Communication University of China, Beijing, where I focused on physical layer problems of wireless communication.

 I am a sport fan and a tireless traveller.



# Recent News
{% include base_path %}
{% assign news = site.news | reverse %}
{% assign first_post = news | first %}
{% assign first_year = first_post.date | date: '%Y' %}
{% assign first_day = first_post.date | date: '%j' %}
{% assign post_count = 0 %}
{% for post in news %}
  {% assign cyear = post.date | date: '%Y' %}
  {% assign cday = post.date | date: '%j' %}
  {% if cyear != first_year %}
    {% assign ellapsed_days = first_year | minus:cyear | times:365 | plus:first_day | minus:cday %}
  {% else %}
    {% assign ellapsed_days = first_day | minus:cday %}
  {% endif %}
  
  {% if ellapsed_days > 365 and post_count > 3 %}
    {% break %}
  {% endif %}
  {% include archive-single.html %}
  {% assign post_count = post_count | plus: 1 %}
{% endfor %}

---

For more news see [here](/news/).
