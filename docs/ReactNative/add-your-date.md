# Add your data

Estimated reading time : 1 minutes

Use the code sample below to add your data on your map. This example is perfect to build a simple store locator!

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

const AddData = () => {
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
          <MapLibreGL.ShapeSource
            id="market-source"
            url={'https://media.jawg.io/add-your-data/marketplaces.geojson'}>
            <MapLibreGL.SymbolLayer
              id="shop-icon"
              style={{
                iconImage: 'https://media.jawg.io/add-your-data/shop.png',
                iconAnchor: 'bottom',
              }}
            />
          </MapLibreGL.ShapeSource>
        </MapLibreGL.MapView>
      </View>
    </View>
  );
};

export default AddData;

```