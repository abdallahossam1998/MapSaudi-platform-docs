# Simple map integration

Estimated reading time : 1 minutes

Check out this code sample that uses the Leaflet library to integrate a simple map onto your site.

```
<html>
<head>
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.8.0/dist/leaflet.css" />
  <script src="https://unpkg.com/leaflet@1.8.0/dist/leaflet.js"></script>
  <style>
    body {
      margin: 0;
      padding: 0;
    }
    #map {
      min-height: 500px;
      height: 100%;
      width: 100%;
    }
  </style>
</head>
<body>
  <div id="map"></div>
  <script>
    // Don't forget to replace <YOUR_ACCESS_TOKEN> by your real access token ! 
    const accessToken = '<YOUR_ACCESS_TOKEN>';
    const map = L.map('map').setView([48.7965913, 2.3210938], 3);
    L.tileLayer(
      `https://tile.jawg.io/jawg-sunny/{z}/{x}/{y}.png?access-token=${accessToken}`, {
        attribution: '<a href="http://jawg.io" title="Tiles Courtesy of Jawg Maps" target="_blank" class="jawg-attrib">&copy; <b>Jawg</b>Maps</a> | <a href="https://www.openstreetmap.org/copyright" title="OpenStreetMap is open data licensed under ODbL" target="_blank" class="osm-attrib">&copy; OSM contributors</a>',
        maxZoom: 22
      }
    ).addTo(map);
  </script>
</body>
</html>
```