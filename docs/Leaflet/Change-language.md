# Change the language of your map

Estimated reading time : 1 minutes

Check out this code sample that uses the Leaflet library to change the language on your map.

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
    select {
      z-index: 1000;
      position: absolute;
      top: 5px;
      right: 5px;
      padding: 5px;
      background: white;
    }
  </style>
</head>
<body>
  <div id="map">
    <select id="languages">
      <option value="en">English</option>
      <option value="fr">French</option>
      <option value="it">Italian</option>
      <option value="es">Spanish</option>
      <option value="de">German</option>
      <option value="nl">Dutch</option>
      <option value="zh">Chinese</option>
    </select>
  </div>
  <!-- JavaScript -->
  <script>
    // Don't forget to replace <YOUR_ACCESS_TOKEN> by your real access token ! 
    const accessToken = '<YOUR_ACCESS_TOKEN>';
    const map = L.map('map').setView([48.7965913, 2.3210938], 3);
    const layer = L.tileLayer(
      `https://tile.jawg.io/jawg-dark/{z}/{x}/{y}.png?lang=en&access-token=${accessToken}`, {
        attribution: '<a href="http://jawg.io" title="Tiles Courtesy of Jawg Maps" target="_blank" class="jawg-attrib">&copy; <b>Jawg</b>Maps</a> | <a href="https://www.openstreetmap.org/copyright" title="OpenStreetMap is open data licensed under ODbL" target="_blank" class="osm-attrib">&copy; OSM contributors</a>',
        maxZoom: 22,
      }
    ).addTo(map);

    document
      .getElementById('languages')
      .addEventListener('change', event => {
        const language = event.target.value;
        layer.setUrl(`https://tile.jawg.io/jawg-dark/{z}/{x}/{y}.png?lang=${language}&access-token=${accessToken}`);
      });
  </script>
</body>
</html>
```