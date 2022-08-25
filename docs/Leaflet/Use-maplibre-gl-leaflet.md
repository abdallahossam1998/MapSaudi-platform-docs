# Use vector tiles with maplibre-gl-leaflet

Estimated reading time : 1 minutes

Check out this code sample that uses the Leaflet library to add a marker from GeoJSON onto your map.

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <link rel="stylesheet" href="https://unpkg.com/leaflet@1.8.0/dist/leaflet.css" />
  <script src="https://unpkg.com/leaflet@1.8.0/dist/leaflet.js"></script>
  <!-- Add maplibre-gl-js -->
  <link href='https://unpkg.com/maplibre-gl@2.1.9/dist/maplibre-gl.css' rel='stylesheet' />
  <script src='https://unpkg.com/maplibre-gl@2.1.9/dist/maplibre-gl.js'></script>
  <!-- Add maplibre-gl-leaflet -->
  <script src="https://unpkg.com/@maplibre/maplibre-gl-leaflet@0.0.17/leaflet-maplibre-gl.js"></script>
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
    const map = L.map('map', {
      maxZoom: 22
    }).setView([48.8590, 2.3435], 13);

    L.marker([48.8584, 2.2945], {
        icon: L.icon({
          iconUrl: 'https://www.jawg.io/docs/images/icons/eiffel-tower.png',
          iconSize: [50, 50],
          iconAnchor: [25, 50],
          popupAnchor: [0, -57]
        })
      })
      .bindPopup("Hello <b>Leaflet GL</b>!")
      .addTo(map)
      .openPopup();

    var gl = L.maplibreGL({
      style: `https://api.jawg.io/styles/jawg-streets.json?access-token=${accessToken}`,
      attribution: '<a href="http://jawg.io" title="Tiles Courtesy of Jawg Maps" target="_blank" class="jawg-attrib">&copy; <b>Jawg</b>Maps</a> | <a href="https://www.openstreetmap.org/copyright" title="OpenStreetMap is open data licensed under ODbL" target="_blank" class="osm-attrib">&copy; OSM contributors</a>',
      maxZoom: 22
    }).addTo(map);
  </script>
</body>
</html>
```