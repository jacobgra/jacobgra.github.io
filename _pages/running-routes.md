---
layout: archive
title: "Running routes"
permalink: /running-routes/
author_profile: true
---
Stockholm University is located in a perfect area for running. The highlighted path is a good 12 km track around Norra Djurgården. I would be happy to take you out for a run-and-talk!

<div id="running-routes-map" style="height: 420px; max-width: 760px; width: 100%; margin: 1rem 0;"></div>

<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css" integrity="sha256-p4NxAoJBhIIN+hmNHrzRCf9tD/miZyoHS5obTRR9BMY=" crossorigin="">
<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js" integrity="sha256-20nQCchB9co0qIjJZRGuk2/Z9VM+kNiyxNV1lvTlZBo=" crossorigin=""></script>
<script src="https://cdn.jsdelivr.net/npm/leaflet-gpx@2.2.0/gpx.min.js"></script>
<script>
  (function () {
    var mapElement = document.getElementById('running-routes-map');
    if (!mapElement || typeof L === 'undefined') {
      return;
    }

    var norraDjurgardenCenter = [59.36, 18.07];
    var norraDjurgardenBounds = L.latLngBounds([
      [59.34, 18.04],
      [59.38, 18.10]
    ]);
    var map = L.map('running-routes-map', {
      zoomControl: true,
      minZoom: 10,
      maxZoom: 20,
      maxBounds: norraDjurgardenBounds,
      maxBoundsViscosity: 1.0
    }).setView(norraDjurgardenCenter, 13);

    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      maxZoom: 16,
      attribution: '&copy; <a href="https://www.openstreetmap.org/copyright">OpenStreetMap</a> contributors'
    }).addTo(map);

    var routes = [
      { file: '/assets/gpx/djurgarden-loop.gpx', name: 'Djurgården loop', color: '#0072B2' }
    ];

    routes.forEach(function (route) {
      new L.GPX(route.file, {
        async: true,
        marker_options: {
          startIconUrl: null,
          endIconUrl: null,
          shadowUrl: null,
          wptIcons: {}
        },
        polyline_options: {
          color: route.color,
          weight: 4,
          opacity: 0.9
        }
      }).on('loaded', function (event) {
        event.target.bindPopup(route.name);
      }).addTo(map);
    });
  })();
</script>
