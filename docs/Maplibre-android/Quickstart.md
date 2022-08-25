# MapLibre GL Android

Estimated reading time : 2 minutes

## Prerequisite

For all of our examples, you will need:

- An API key and MapSaudi account ([from the platform](https://app.mapsaudi.com/)),
- Basic knowledge in JavaScript and HTML,
- One style (default or custom style)
- check the full list of MapView attributes [here](https://github.com/maplibre/maplibre-gl-native/blob/android-v9.5.1/platform/android/MapboxGLAndroidSDK/src/main/res/values/attrs.xml)

## Get the library

There are several ways to get this library:

- from the github repository ([github.com/maplibre/maplibre-gl-native](https://github.com/maplibre/maplibre-gl-native/releases/tag/android-v9.5.1))
- from maven/gradle (group: org.maplibre.gl, name: android-sdk, version: 9.5.1)

## Attribution

Your map **must** display the following links: [MapSaudi]() and © [OpenStreetMap](https://www.openstreetmap.org/about/).

This is our attribution template:

```
<a href="https://basemaps.mapsaudi.com/" title="Tiles Courtesy of MapSaudi Maps" target="_blank" class="jawg-attrib" >&copy; <b>MapSaudi</b>Maps</a> | <a href="https://www.openstreetmap.org/copyright" title="OpenStreetMap is open data licensed under ODbL" target="_blank" class="osm-attrib" >&copy; OSM contributors</a>
```

Since we are not using mapbox, you should also hide the mapbox logo (mapbox:mapbox_uiLogo set to false).

```
<com.mapbox.mapboxsdk.maps.MapView
        android:id="@+id/mapView"
        android:layout_width="match_parent"
        android:layout_height="match_parent"
        mapbox:mapbox_uiLogo="false"
        mapbox:mapbox_uiAttribution="false"/>
```

## Our examples

- [simple-map](): Simple map integration
- [add-marker](): Add a marker on your map
- [add-geometry](): Add a geometry from GeoJSON on your map
- [add-your-data](): Add your own data on your map
- [add-popup](): Add a popup on your map
- [change-language](): Change your map's language
- [change-style](): Change your map style (with our default styles)
- [custom-style](): Use a custom style from [MapSaudi Lab](https://app.mapsaudi.com/)
