---
layout: default
permalink: /meta/archive
---

<section class="meta" id="archive">
  <div class="header">
    <i class="fa fa-calendar fa-3x fa-pull-left" aria-hidden="true"></i>
    <h2>Archive</h2>
  </div>
  <div>
   {% assign thisYear = site.time | date: "%Y" %}
   {% for post in site.posts %}
       {% assign postYear = post.date | date: "%Y" %}
       {% if postYear != listYear %}
           {% unless forloop.first %}
             </ul>
           {% endunless %}
           {% if thisYear == postYear %}
             <h1>This year's posts:</h1>
           {% else %}
             <h1>{{ postYear }}:</h1>
           {% endif %}
           <ul>
           {% assign listYear = postYear %}
       {% endif %}
       <li><time>{{ post.date | date: "%d %b" }}</time><a href="{{ post.url }}">{{ post.title }}</a></li>
       {% if forloop.last %}</ul>{% endif %}
   {% endfor %}
  </div>

</section>
