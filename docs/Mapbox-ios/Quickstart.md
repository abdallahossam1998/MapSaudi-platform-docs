# Mapbox GL iOS

Estimated reading time : 1 minutes

## Prerequisite

For all of our examples, you will need:

- An API key and MapSaudi account ([from the platform](https://app.mapsaudi.com/)),
- knowledge in Swift/iOS development,
- One style (default or custom style)

## Get the library

There are several ways to get this library:

- from the github repository ([github.com/mapbox/mapbox-gl-native-ios](https://github.com/mapbox/mapbox-gl-native-ios/releases/tag/ios-v5.9.0))
- from cocoapods.org (pod name: [Mapbox-iOS-SDK](https://cocoapods.org/pods/Mapbox-iOS-SDK))

## Attribution

Your map **must** display the following links: [MapSaudi]() and © [OpenStreetMap](https://www.openstreetmap.org/about/).

This is our attribution template:

```
<a href="https://basemaps.mapsaudi.com/" title="Tiles Courtesy of MapSaudi Maps" target="_blank" class="jawg-attrib" >&copy; <b>MapSaudi</b>Maps</a> | <a href="https://www.openstreetmap.org/copyright" title="OpenStreetMap is open data licensed under ODbL" target="_blank" class="osm-attrib" >&copy; OSM contributors</a>
```

Since we are not using mapbox, you should also hide the mapbox logo (mapbox:mapbox_uiLogo set to false).

## Our examples

- [simple-map](): Simple map integration
- [add-marker](): Add a marker on your map
- [add-geometry](): Add a geometry from GeoJSON on your map
- [add-popup](): Add a popup on your map
- [change-language](): Change your map's language
- [change-style](): Change your map style (with our default styles)
- [custom-style](): Use a custom style from [MapSaudi Lab](https://app.mapsaudi.com/)
