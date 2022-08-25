# Simple map integration

Estimated reading time : 1 minutes

Check out this code sample that uses the React Native library to integrate a simple map.

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

const SimpleMap = () => {
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
              centerCoordinate: [2.3210938, 48.7965913],
              zoomLevel: 2,
            }}
          />
        </MapLibreGL.MapView>
      </View>
    </View>
  );
};

export default SimpleMap;

```