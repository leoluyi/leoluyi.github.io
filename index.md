---
layout: default
title: Home
---

# <strong>Hi, I'm Leo Lu</strong>

{% include social.html %}

<div class="avatar">
  <img class="rounded-circle" src="{{ site.baseurl }}/public/img/{{ site.author.avatar }}" alt="Responsive image" width="180px" height="auto" align="right" style="float:right;margin-top:0.5em;margin-left:1em;">
</div>

<!-- Data Science -->
In 2012, a year out of business college, I decided to drop everything and learn to code.
In a period of three months, I **learned to code** and **shipped my first data product**.
Since then, I've been working heavily with data.
I lead the user acquisition at a startup called PasswordBox.
The product was used by over 15 million persons and was eventually acquired by Intel in 2014.
Following the acquisition, I transitioned into data science.

<!-- Convertkit - Start -->
<!-- <script async id="_ck_148263" src="https://forms.convertkit.com/148263?v=6"></script> -->
<!-- Convertkit - End -->

<section class="container">
  <h2 class="page-heading">Latest Posts</h2>
  <div class="panel panel-default">
    <div class="panel-body">
      {% for post in site.posts limit:5 %}
      <div class="row">
        <div class="col-sm-3 col-md-3 col-lg-3">
          <span style="float:right">
            {{ post.date | date: "%b %d, %Y" }}
          </span>
        </div>
        <div class="col-sm-9 col-md-9 col-lg-9">
          <span style="float:left">
            <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
          </span>
        </div>
      </div>
      {% endfor %}
    </div>
  </div>
</section>
