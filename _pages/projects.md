---
layout: page
title: projects
permalink: /projects/
description: 
nav: true
nav_order: 2
---

<div class="projects projects-accordion">
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  {%- for project in sorted_projects -%}
    {% include project_accordion.html project=project %}
  {%- endfor %}
</div>

<script>
document.addEventListener('DOMContentLoaded', function () {
  var toggles = document.querySelectorAll('.project-card .project-toggle');

  toggles.forEach(function (btn) {
    btn.addEventListener('click', function () {
      var card = btn.closest('.project-card');
      if (!card) return;

      var isOpen = card.classList.contains('is-open');

      document.querySelectorAll('.project-card.is-open').forEach(function (openCard) {
        if (openCard !== card) openCard.classList.remove('is-open');
      });

      card.classList.toggle('is-open', !isOpen);
    });
  });
});
</script>

