---
layout: single
title: "Research"
permalink: /research/
author_profile: true
---

<header>
    <h1>Working papers</h1>
  </header>
<div class="tab-content" id="research-tabs-content" style="margin-top: 1rem;">
  <div class="tab-pane fade show active" id="working-papers" role="tabpanel" aria-labelledby="working-papers-tab">
    <ul>
      <li>Add your working papers here.</li>
    </ul>
  </div>
  <header>
    <h1>Work in progress</h1>
  </header>
  <div class="tab-pane fade" id="work-in-progress" role="tabpanel" aria-labelledby="work-in-progress-tab">
    <ul>
      <li>Dissent in central bank communication</li>
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
