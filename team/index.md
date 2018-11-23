---
layout: page
current: team
navigation: true
title: Team Members
logo: 'assets/images/small-logo.jpg'
class: page-template
subclass: 'post page'
---
<!-- <link rel="stylesheet" href="{{ '/assets/bootstrap_grid/bootstrap.css' | prepend: site.baseurl | replace: '//','/' }}"> -->
<!-- <script src="{{ '/assets/bootstrap_grid/bootstrap.min.js' | prepend: site.baseurl | replace: '//','/' }}"></script> -->
<div class="member-container">
  {% for member in site.data.members %}
  <!-- {{ member }} -->
    <div class="member-box" {% if member.display_order %}style="order: {{ member.display_order }}"{% endif %}>
      {% if member.image %}
        <img src='{{ site.baseurl | append: '/assets/images/members/' | append: member.image | replace: '//','/' }}' class='member-image'>
      {% else %}
        <img src='{{ site.baseurl | append: '/assets/images/members/' | append: 'anonymous.png' | replace: '//','/' }}' class='member-image'>
      {% endif %}

      {% if member.name %}
        <p class="member-name">{{ member.name }}</p>
      {% endif %}
      {% if member.alias %}
        <p class="member-alias">({{ member.alias }})</p>
      {% endif %}
      {% if member.interest %}
        <p class="member-interest">{{ member.interest }}</p>
      {% endif %}
      {% if member.social %}
        <ul class="member-social">
          {% if member.social.github %}
            <li><a rel="noopener" href="https://github.com/{{ member.social.github }}" target="blank"><i class="fa fa-github"></i></a></li>
          {% endif %}
          {% if member.social.linkedin %}
            <li><a rel="noopener" href="https://www.linkedin.com/in/{{ member.social.linkedin }}" target="blank"><i class="fa fa-linkedin"></i></a></li>
          {% endif %}
          {% if member.social.twitter %}
            <li><a rel="noopener" href="https://twitter.com/{{ member.social.twitter }}" target="blank"><i class="fa fa-twitter"></i></a></li>
          {% endif %}
        </ul>
      {% endif %}
    </div>
  {% endfor %}
</div>
<style>
  .row{
    display: table;
    /* margin-left: -15px;
    margin-right: -15px; */
  }

  .member-container{
    justify-content: space-evenly;
    width: 100%;
    display: inline-flex;
    flex-direction: row;
    flex-wrap: wrap;
    align-items: stretch;
  }

  .member-box{
    float: left;
    padding: 0.5%;
    width: 30%;
    min-width: 300px;
    height: 100%; /*for flex to work*/
    border-radius: 2%;
    margin: 1.5%;
    background-color: #a9bfbe17;
  }

  .member-image{
    padding-left: 5%;
    padding-right: 5%;
    width: 90%;
    height: 90%;
    margin-bottom: 2%;
    border-radius: 50%;
  }

  .member-name, .member-interest, .member-alias{
    text-align: center;
    font-size: 115%;
    margin-bottom: 2%;
  }
  .member-name{
    font-weight: bold;
  }

  .member-interest{
    font-size: 100%;
  }

  .member-alias{
    font-size: 90%;
    margin-top: -1%;
  }

  .member-social {
    list-style: none;
    padding: 3%;
    margin: 0;
    justify-content: space-evenly;
    display: inline-flex;
    flex-direction: row;
    flex-wrap: wrap;
  }
  .member-social > li{
    display: inline;
    margin: 0;
    padding: 0;
  }
</style>

<!-- Override the original -->
<style>
  @media (max-width: 1170px)
  .post-full-content {
      padding: 0;
  }

  .post-full-content {
      padding: 0;
  }
</style>
