# Change the language of your map

Estimated reading time : 1 minutes

Check out this code sample that uses the MapLibre GL JS library to change the language on your map.

```
<!DOCTYPE html>
<html>
<head>
  <meta charset=UTF-8>
  <link href="https://unpkg.com/maplibre-gl@2.1.9/dist/maplibre-gl.css" rel="stylesheet" />
  <script src="https://unpkg.com/maplibre-gl@2.1.9/dist/maplibre-gl.js"></script>
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
      z-index: 1;
      position: absolute;
      top: 5px;
      left: 5px;
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
  <script>
    // Don't forget to replace <YOUR_ACCESS_TOKEN> by your real access token! 
    const accessToken = '<YOUR_ACCESS_TOKEN>';
    const map = new maplibregl.Map({
        container: 'map',
        style: `https://api.jawg.io/styles/jawg-dark.json?lang=en&access-token=${accessToken}`,
        zoom: 2,
        center: [2.3210938, 48.7965913],
        hash: true
      })
      .addControl(new maplibregl.NavigationControl(), 'top-right');
    // This plugin is used for right to left languages
    maplibregl.setRTLTextPlugin('https://unpkg.com/@mapbox/mapbox-gl-rtl-text@0.2.3/mapbox-gl-rtl-text.min.js');

    map.on('load', function() {
      document
        .getElementById('languages')
        .addEventListener('change', function(event) {
          var language = event.target.value;
          map.setStyle(`https://api.jawg.io/styles/jawg-dark.json?lang=${language}&access-token=${accessToken}`);
        });
    });
  </script>
</body>
</html>
```