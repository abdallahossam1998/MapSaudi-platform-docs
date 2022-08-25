# Add a marker

Estimated reading time : 1 minutes

Check out this code sample that uses the React Native library to add a marker from GeoJSON or coordinates onto your map.

```
import React from 'react';
import {StyleSheet, View, Image} from 'react-native';
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

const AddMarker = () => {
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
              centerCoordinate: [2.3210938, 48.8565913],
              zoomLevel: 5,
            }}
          />
          <MapLibreGL.MarkerView
            coordinate={[-0.124589, 51.500741]}
            children={
              <Image
                source={{
                  uri: 'https://www.r7.jawg.io/docs/images/icons/big-ben.png',
                }}
                style={{width: 25, height: 25}}
              />
            }
            anchor={{x: 0, y: 0.5}}
          />
          <MapLibreGL.ShapeSource
            id="marker-source"
            shape={{
              type: 'Feature',
              geometry: {
                type: 'Point',
                coordinates: [2.294694, 48.858093],
              },
            }}>
            <MapLibreGL.SymbolLayer
              id="marker-layer"
              style={{
                iconImage:
                  'https://www.jawg.io/docs/images/icons/eiffel-tower.png',
                iconSize: 0.5,
              }}
            />
          </MapLibreGL.ShapeSource>
        </MapLibreGL.MapView>
      </View>
    </View>
  );
};

export default AddMarker;

```