# Add geometry

Estimated reading time : 1 minutes

Check out this code sample that uses the React Native library to add a geometry from GeoJSON onto your map.

```
import React from 'react';
import {StyleSheet, View} from 'react-native';
import MapLibreGL from '@react-native-mapbox-gl/maps';

import {accessToken} from '../../config';

const styles = StyleSheet.create({
  page: {
    flex: 1,
    justifyContent: 'center',
    alignItems: 'center',
    backgroundColor: '#F5FCFF',
  },
  container: {
    width: '100%',
    height: '100%',
    backgroundColor: 'white',
  },
  map: {
    flex: 1,
  },
});

const AddGeometry = () => {
  return (
    <View style={styles.page}>
      <View style={styles.container}>
        <MapLibreGL.MapView
          style={styles.map}
          logoEnabled={false}
          attributionEnabled={true}
          attributionPosition={{bottom: 8, left: 8}}
          styleURL={`https://api.jawg.io/styles/jawg-sunny.json?access-token=${accessToken}`}>
          <MapLibreGL.Camera
            defaultSettings={{
              centerCoordinate: [2.3488, 48.8534],
              zoomLevel: 10,
            }}
          />
          <MapLibreGL.ShapeSource id="route-source" shape={geoJsonFeature}>
            <MapLibreGL.LineLayer
              id="route-layer"
              style={{
                lineColor: 'steelblue',
                lineWidth: 4,
                lineJoin: 'round',
                lineCap: 'round',
              }}
            />
          </MapLibreGL.ShapeSource>
        </MapLibreGL.MapView>
      </View>
    </View>
  );
};

const geoJsonFeature = {
  type: 'Feature',
  properties: {},
  geometry: {
    type: 'LineString',
    coordinates: [
      [2.319887, 48.90046],
      [2.329981, 48.901163],
      [2.38515, 48.902008],
      [2.394906, 48.898444],
      [2.397627, 48.894578],
      [2.398846, 48.887109],
      [2.408308, 48.880409],
      [2.41327, 48.872892],
      [2.413838, 48.864376],
      [2.416341, 48.849234],
      [2.412246, 48.834539],
      [2.422139, 48.835798],
      [2.41939, 48.842577],
      [2.42813, 48.841528],
      [2.447699, 48.844818],
      [2.463438, 48.842089],
      [2.467426, 48.838891],
      [2.467582, 48.833133],
      [2.462696, 48.81906],
      [2.458705, 48.81714],
      [2.438448, 48.818232],
      [2.421462, 48.824054],
      [2.406032, 48.827615],
      [2.390939, 48.826079],
      [2.379296, 48.821214],
      [2.363947, 48.816314],
      [2.345958, 48.816036],
      [2.331898, 48.817011],
      [2.332461, 48.818247],
      [2.292196, 48.827142],
      [2.279052, 48.83249],
      [2.272793, 48.82792],
      [2.263174, 48.83398],
      [2.255144, 48.83481],
      [2.251709, 48.838822],
      [2.250612, 48.845555],
      [2.239978, 48.849702],
      [2.224219, 48.853517],
      [2.228225, 48.865183],
      [2.231736, 48.869069],
      [2.245678, 48.876435],
      [2.25541, 48.874264],
      [2.258467, 48.880387],
      [2.277487, 48.877968],
      [2.282327, 48.883923],
      [2.291507, 48.889472],
      [2.319887, 48.90046],
    ],
  },
};

export default AddGeometry;

```