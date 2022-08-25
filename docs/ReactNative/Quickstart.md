# React Native

Estimated reading time : 3 minutes

## Prerequisite

The support of react native is done by an **unofficial open source react native bindings** to maps SDKs based on OpenStreetMap.

Their binding uses Mapbox as examples, **you must change those URLs by MapSaudi Maps URLs.**

For all of our examples, you will need:

- An API key and MapSaudi account ([from the Platform](https://app.mapsaudi.com/)),
- Basic knowledge of React Native,
- One style (default or custom style)

## Get the library

There are several ways to get this library:

- from the github repository ([github.com/react-native-mapbox-gl/maps](https://github.com/rnmapbox/maps))
- from npmjs.com (package name: [@react-native-mapbox-gl/maps](https://www.npmjs.com/package/@react-native-mapbox-gl/maps))

You will need to add some changes in your Podfile and build.gradle to use MapLibre GL instead of Mapbox GL

Podfile:

```
$RNMBGL_Use_SPM = {
  url: "https://github.com/maplibre/maplibre-gl-native-distribution",
  requirement: {
    kind: "upToNextMajorVersion",
    minimumVersion: "5.11.0"
  },
  product_name: "Mapbox"
}

# ...

pre_install do |installer|
  $RNMBGL.pre_install(installer)
end

post_install do |installer|
   flipper_post_install(installer)
   $RNMBGL.post_install(installer)
end
```

```
buildscript {
  ext {
    // ...
    rnmbglMapboxLibs = {
      implementation ("org.maplibre.gl:android-sdk:9.2.1")
      implementation ("com.mapbox.mapboxsdk:mapbox-sdk-turf:5.3.0")
    }

    rnmbglMapboxPlugins = {
      implementation ("com.mapbox.mapboxsdk:mapbox-android-gestures:0.7.0")
      implementation ("com.mapbox.mapboxsdk:mapbox-android-plugin-localization-v9:0.12.0")    {
        exclude group: 'com.mapbox.mapboxsdk', module: 'mapbox-android-sdk'
      }
      implementation ("com.mapbox.mapboxsdk:mapbox-android-plugin-annotation-v9:0.8.0")        {
        exclude group: 'com.mapbox.mapboxsdk', module: 'mapbox-android-sdk'
      }
      implementation ("com.mapbox.mapboxsdk:mapbox-android-plugin-markerview-v9:0.4.0") {
        exclude group: 'com.mapbox.mapboxsdk', module: 'mapbox-android-sdk'
      }
    }
  }
}

repositories {
  // ...
  maven {
    url = "https://dl.bintray.com/maplibre/maplibre-gl-native"
  }
}
```

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
- [add-your-data]() : Add your own data on your map
- [add-popup](): Add a popup on your map
- [change-language](): Change your map's language
- [change-style](): Change your map style (with our default styles)
- [custom-style](): Use a custom style from [MapSaudi Lab](https://app.mapsaudi.com/)
