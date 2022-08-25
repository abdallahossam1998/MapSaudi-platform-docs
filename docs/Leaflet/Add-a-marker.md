# Add a marker

Estimated reading time : 1 minutes

Check out this code sample that uses the Leaflet library to add a marker from GeoJSON onto your map.

```
<html>
<head>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.5.0/leaflet.css" />
  <script src="https://cdnjs.cloudflare.com/ajax/libs/leaflet/1.5.0/leaflet-src.js"></script>
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
  <!-- JavaScript -->
  <script>
    // Don't forget to replace <YOUR_ACCESS_TOKEN> by your real access token ! 
    const accessToken = '<YOUR_ACCESS_TOKEN>';
    const map = L.map('map').setView([48.852966, 2.349902], 12);
    L.tileLayer(
      `https://tile.jawg.io/jawg-terrain/{z}/{x}/{y}.png?access-token=${accessToken}`, {
        attribution: '<a href="http://jawg.io" title="Tiles Courtesy of Jawg Maps" target="_blank" class="jawg-attrib">&copy; <b>Jawg</b>Maps</a> | <a href="https://www.openstreetmap.org/copyright" title="OpenStreetMap is open data licensed under ODbL" target="_blank" class="osm-attrib">&copy; OSM contributors</a>',
        maxZoom: 22
      }
    ).addTo(map);

    // This add a marker with the default icon
    L.marker([48.852966, 2.349902]).addTo(map);
    // Marker with custom icon
    L.marker([48.858093, 2.294694], {
      icon: L.icon({
        iconUrl: 'https://www.jawg.io/docs/images/icons/eiffel-tower.png',
        iconSize: [50, 50]
      })
    }).addTo(map);
  </script>
</body>
</html>
```