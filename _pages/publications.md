---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---


{% include base_path %}

<div class="pubs-layout">
  <div class="pubs-main">
    {% assign pubs_by_year = site.publications
       | group_by_exp: "pub", "pub.date | date: '%Y'"
       | sort: "name"
       | reverse %}

    {% for year in pubs_by_year %}
      <h2 id="year-{{ year.name }}">{{ year.name }}</h2>

      {% for pub in year.items %}
        {% assign post = pub %}
        {% include archive-single.html %}
      {% endfor %}

    {% endfor %}
  </div>

  <div class="pubs-sidebar">
    <ul class="pubs-year-list">
      {% for year in pubs_by_year %}
        <li>
          <a href="#year-{{ year.name }}">{{ year.name }}</a>
        </li>
      {% endfor %}
    </ul>
  </div>
</div>
