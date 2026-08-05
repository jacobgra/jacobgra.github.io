---
layout: single
title: "Research"
permalink: /research/
author_profile: true
---

<ul class="nav nav-tabs" id="research-tabs" role="tablist">
  <li class="nav-item" role="presentation">
    <button class="nav-link active" id="working-papers-tab" data-bs-toggle="tab" data-bs-target="#working-papers" type="button" role="tab" aria-controls="working-papers" aria-selected="true">Working papers</button>
  </li>
  <li class="nav-item" role="presentation">
    <button class="nav-link" id="work-in-progress-tab" data-bs-toggle="tab" data-bs-target="#work-in-progress" type="button" role="tab" aria-controls="work-in-progress" aria-selected="false">Work in progress</button>
  </li>
</ul>
<div class="tab-content" id="research-tabs-content" style="margin-top: 1rem;">
  <div class="tab-pane fade show active" id="working-papers" role="tabpanel" aria-labelledby="working-papers-tab">
    <ul>
      <li>Add your working papers here.</li>
    </ul>
  </div>
  <div class="tab-pane fade" id="work-in-progress" role="tabpanel" aria-labelledby="work-in-progress-tab">
    <ul>
      <li>Add your work in progress here.</li>
    </ul>
  </div>
</div>

<script>
  document.addEventListener('DOMContentLoaded', function () {
    var tabs = document.querySelectorAll('#research-tabs .nav-link');
    var panes = document.querySelectorAll('#research-tabs-content .tab-pane');

    tabs.forEach(function (tab) {
      tab.addEventListener('click', function () {
        tabs.forEach(function (t) {
          t.classList.remove('active');
          t.setAttribute('aria-selected', 'false');
        });
        panes.forEach(function (pane) {
          pane.classList.remove('show', 'active');
        });

        tab.classList.add('active');
        tab.setAttribute('aria-selected', 'true');

        var target = tab.getAttribute('data-bs-target');
        var pane = document.querySelector(target);
        if (pane) {
          pane.classList.add('show', 'active');
        }
      });
    });
  });
</script>
