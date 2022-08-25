# Use a custom style from MapSaudi Lab

Estimated reading time : 1 minutes

Check out this code sample that allows you to add a custom style to your map, using the React Native library.

```
import React, {useState} from 'react';
import {StyleSheet, View, TextInput, Button} from 'react-native';
import MapLibreGL from '@react-native-mapbox-gl/maps';

import {accessToken, customStyle} from '../../config';

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
  topBar: {
    height: 60,
    display: 'flex',
    flexDirection: 'row',
    padding: 10,
  },
  tokenInput: {
    height: 40,
    flex: 2,
    borderWidth: 1,
    padding: 10,
    marginRight: 10,
    color: 'black',
  },
  updateButton: {
    height: 40,
    padding: 10,
  },
  map: {
    flex: 1,
  },
});

const CustomStyle = () => {
  const [style, setStyle] = useState(customStyle);

  const [input, updateInput] = useState('');

  return (
    <View style={styles.page}>
      <View style={styles.container}>
        <View style={styles.topBar}>
          <TextInput
            style={styles.tokenInput}
            onChangeText={newInput => updateInput(newInput.trim())}
            defaultValue={customStyle}
            placeholder={'enter your custom style name'}
          />
          <Button
            style={styles.updateButton}
            title={'Update'}
            onPress={() => setStyle(input)}
          />
        </View>
        <MapLibreGL.MapView
          style={styles.map}
          logoEnabled={false}
          attributionEnabled={true}
          attributionPosition={{bottom: 8, left: 8}}
          styleURL={`https://api.jawg.io/styles/${style}.json?access-token=${accessToken}`}>
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

export default CustomStyle;

```