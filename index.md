---
layout: default
title: Vincent Barbosa Vaz
---

# Welcome to my GitHub Pages

## Interests

* <a href="https://ai.google/" target="_blank">Google AI</a> - AI, Google, Research
* <a href="http://yann.lecun.com/" target="_blank">Yann Lecun</a> - AI, Machine learning, Computer vision
* <a href="https://www.meilleurdevdefrance.com/" target="_blank">MDF: Meilleur Développeur de France</a> - Hackathon, Conferences, Innovation
* <a href="https://vivatechnology.com/" target="_blank">VivaTech</a> - Startups, Conferences, Innovation
* <a href="https://codingcompetitions.withgoogle.com/hashcode/" target="_blank">Hash Code - Google's Coding Competitions</a> - Hackathon

## Latest Posts

<ul>
  {% for post in site.posts %}
    <li>
      <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
      <p>{{ post.date | date_to_string }}</p>
      <p>{{ post.excerpt }}</p>
    </li>
  {% endfor %}
</ul>
