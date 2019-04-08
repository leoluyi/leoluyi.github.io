---
layout: default
title: Home
---

# <strong>Hi, I'm Leo Lu</strong>

<div class="avatar">
  <img class="img-circle" src="{{ site.baseurl }}public/img/{{ site.avatar }}" alt="Responsive image" width="180" height="auto">
</div>

<!-- <img src="./public/img/jn2.png" style="float:right;width:10em;margin-top:1em;margin-left:2em;"> -->

<!-- Data Science -->
In 2012, a year out of business college, I decided to drop everything and learn to code.
In a period of three months, I **learned to code** and **shipped my first data product**.
Since then, I've been working heavily with data.
I lead the user acquisition at a startup called PasswordBox.
The product was used by over 15 million persons and was eventually acquired by Intel in 2014.
Following the acquisition, I transitioned into data science.

With more than 5-year experience focusing on data science career path,
I have hands-on experience in solving empirical problems in the field of retail
banking industry including operation improvement and marketing,
with focus on predicting, text mining,
recommendation problems with machine learning techniques.

I am leading data teams working on data-driven projects with open-source
infrastructure and also advocating for changes.
I am specialized in translating the business problems into data-driven solutions, and weaving the gap between business and technology by on data visualization (DataViz) and persuasive presentations skills.

Right now, I am **Data Scientist / Data Manager** at Taishin International Bank in Taiwan.
Here, I document my journey learning about **data science** and **growth** all while teaching others.

<!-- Convertkit - Start -->
<!-- <script async id="_ck_148263" src="https://forms.convertkit.com/148263?v=6"></script> -->
<!-- Convertkit - End -->

<div class="posts">
  {% for post in paginator.posts %}
  <div class="post">
    <h2 class="post-title">
      <a href="{{ site.baseurl }}{{ post.url }}">
        {{ post.title }}
      </a>
    </h1>

    <span class="post-date">{{ post.date | date_to_string }}</span>

    {{ post.excerpt }}

    {% if post.excerpt != post.content %}
      <p><a href="{{ site.baseurl }}{{ post.url }}">Read more</a></p>
    {% endif %}
  </div>
  {% endfor %}
</div>

<div class="pagination">
  {% if paginator.next_page %}
    <a class="pagination-item older" href="{{ site.baseurl }}/page{{paginator.next_page}}">Older</a>
  {% else %}
    <span class="pagination-item older">Older</span>
  {% endif %}
  {% if paginator.previous_page %}
    {% if paginator.page == 2 %}
      <a class="pagination-item newer" href="{{ site.baseurl }}/">Newer</a>
    {% else %}
      <a class="pagination-item newer" href="{{ site.baseurl }}/page{{paginator.previous_page}}">Newer</a>
    {% endif %}
  {% else %}
    <span class="pagination-item newer">Newer</span>
  {% endif %}
</div>

