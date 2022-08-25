# MapLibre GL JS (vector map)

Estimated reading time : 2 minutes

## Prerequisite

For all of our examples, you will need:

- An API key and MapSaudi account ([from the platform](https://app.mapsaudi.com/)),
- Basic knowledge in JavaScript and HTML,
- One style (default or custom style)

## Get the library

There are several ways to get this library:

- from the github repository ([github.com/Leaflet/Leaflet](https://github.com/Leaflet/Leaflet))
- from npmjs.com (package name: [leaflet](https://www.npmjs.com/package/leaflet))
- from a CDN (e.g unpkg.com)

```
<link rel="stylesheet" href="https://unpkg.com/maplibre-gl@2.1.9/dist/maplibre-gl.css" />
<script src="https://unpkg.com/maplibre-gl@2.1.9/dist/maplibre-gl.js"></script>
```

## Attribution

Your map **must** display the following links: [MapSaudi]() and © [OpenStreetMap](https://www.openstreetmap.org/about/).

This is our attribution template:

```
<a href="https://basemaps.mapsaudi.com/" title="Tiles Courtesy of MapSaudi Maps" target="_blank" class="jawg-attrib" >&copy; <b>MapSaudi</b>Maps</a> | <a href="https://www.openstreetmap.org/copyright" title="OpenStreetMap is open data licensed under ODbL" target="_blank" class="osm-attrib" >&copy; OSM contributors</a>
```

## Our examples

- [simple-map](): Simple map integration
- [add-marker](): Add a marker on your map
- [add-geometry](): Add a geometry from GeoJSON on your map
- [add-your-data](): Add a GeoJSON to your map
- [add-popup](): Add a popup on your map
- [change-language](): Change your map's language
- [change-style](): Change your map style (with our default styles)
- [custom-style](): Use a custom style from [MapSaudi Lab](https://app.mapsaudi.com/)
- [display-route](): Display a route on your map
- [draw-radius](): Draw a location radius
