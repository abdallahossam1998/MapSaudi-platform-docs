# Change the style of your map

Estimated reading time : 1 minutes

Switch between the default MapSaudi styles for your map using this code sample that uses the React Native library.

```
import React, {useState} from 'react';
import {StyleSheet, View} from 'react-native';
import MapLibreGL from '@react-native-mapbox-gl/maps';
import SelectDropdown from 'react-native-select-dropdown';

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
  menu: {
    height: 40,
    width: '100%',
  },
});

const ChangeStyle = () => {
  const jawgStyles = [
    'jawg-streets',
    'jawg-sunny',
    'jawg-terrain',
    'jawg-dark',
    'jawg-light',
  ];

  const [style, setStyle] = useState(jawgStyles[0]);

  return (
    <View style={styles.page}>
      <View style={styles.container}>
        <SelectDropdown
          buttonStyle={styles.menu}
          data={jawgStyles}
          defaultValueByIndex={0}
          rowStyle={{
            height: 40,
          }}
          onSelect={(selectedItem, _) => setStyle(selectedItem)}
        />
        <MapLibreGL.MapView
          style={styles.map}
          logoEnabled={false}
          attributionEnabled={true}
          attributionPosition={{bottom: 8, left: 8}}
          styleURL={`https://api.jawg.io/styles/${style}.json?lang=en&access-token=${accessToken}`}>
          <MapLibreGL.Camera
            defaultSettings={{
              centerCoordinate: [35.51, 33.88],
              zoomLevel: 12,
            }}
          />
        </MapLibreGL.MapView>
      </View>
    </View>
  );
};

export default ChangeStyle;

```