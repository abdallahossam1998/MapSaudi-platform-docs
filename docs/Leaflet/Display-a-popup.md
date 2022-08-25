# Display a popup

Estimated reading time : 1 minutes

Check out this code sample that uses the Leaflet library to add a marker from GeoJSON onto your map.

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
    const map = L.map('map').setView([16.233131, -61.572646], 10);
    L.tileLayer(
      `https://tile.jawg.io/jawg-sunny/{z}/{x}/{y}.png?access-token=${accessToken}`, {
        attribution: '<a href="http://jawg.io" title="Tiles Courtesy of Jawg Maps" target="_blank" class="jawg-attrib">&copy; <b>Jawg</b>Maps</a> | <a href="https://www.openstreetmap.org/copyright" title="OpenStreetMap is open data licensed under ODbL" target="_blank" class="osm-attrib">&copy; OSM contributors</a>',
        maxZoom: 22
      }
    ).addTo(map);

    const marker = L.marker([15.966636, -61.653889]).addTo(map);
    marker.bindPopup('<b>A popup that is shown when you click on a marker</b>');

    // Basic popup definition
    L.popup({
        closeOnClick: false
      })
      .setLatLng([16.263131, -61.602646])
      .setContent('<b>Hello world!</b><br/> I am a popup.')
      .addTo(map);
  </script>
</body>
</html>
```