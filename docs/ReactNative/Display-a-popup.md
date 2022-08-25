# Display a popup

Estimated reading time : 1 minutes

Check out this code sample that uses the React Native library to add a popup over your map data points.

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

const AddPopup = () => {
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
              centerCoordinate: [-61.572646, 16.233131],
              zoomLevel: 9,
            }}
          />
          <MapLibreGL.MarkerView
            id="annotaton-simple"
            coordinate={[-61.572646, 16.273131]}>
            <MapLibreGL.Callout title="Hello world!" style={{color: 'black'}} />
          </MapLibreGL.MarkerView>

          <MapLibreGL.PointAnnotation
            id="annotation-hidden"
            coordinate={[-61.653889, 15.966636]}
            style={{backgroundColor: 'white'}}>
            <MapLibreGL.Callout
              title="A popup that is shown when you click on a marker"
              style={{color: 'black'}}
            />
          </MapLibreGL.PointAnnotation>
        </MapLibreGL.MapView>
      </View>
    </View>
  );
};

export default AddPopup;

```