# Use a custom style from MapSaudi Platform

Estimated reading time : 1 minutes

Switch between the default Jawg styles for your map using this code sample that uses the Leaflet library.

```
<html>
<head>
  <link href="https://unpkg.com/leaflet@1.8.0/dist/leaflet.css" rel="stylesheet" />
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
    // Set your custom style ID. To get your custom style ID see https://www.jawg.io/docs/maps#get-custom-style-id
    const styleId = '<YOUR_CUSTOM_STYLE_ID>';
    const map = L.map('map').setView([30.445209, -91.177565], 14);
    L.tileLayer(
      `https://tile.jawg.io/${styleId}/{z}/{x}/{y}.png?access-token=${accessToken}`, {
        attribution: '<a href="http://jawg.io" title="Tiles Courtesy of Jawg Maps" target="_blank" class="jawg-attrib">&copy; <b>Jawg</b>Maps</a> | <a href="https://www.openstreetmap.org/copyright" title="OpenStreetMap is open data licensed under ODbL" target="_blank" class="osm-attrib">&copy; OSM contributors</a>',
        maxZoom: 22
      }
    ).addTo(map);
  </script>
</body>
</html>
```