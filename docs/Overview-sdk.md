# SDKs & Softwares
Estimated reading time : 2 minutes

## Integrating Maps in your project
MapSaudi exposes multiple Tile APIs to work with maps. To display maps, you need to use a Maps SDK.

There are already great OpenSource Maps SDKs, and we'd rather spend our nights optimizing rendering efficiency to give you the **fastest** maps on the market than putting our name on a brand new Maps SDK which would pretty much do the same as the others.

## Raster Tiles
Raster tiles were the first approach to displaying maps. These are small squares (usually 256px) which all together form a map. These squares are png format images that already contain your map with your style applied. This makes client side display faster.

We would recommend [Leaflet](https://www.leafletjs.com) for raster tiles because it gives a better modular approach and has an excellent quality.

![alt text](./images/icons/leaflet.png "Leaflet")

Integrating MapSaudi maps with Leaflet is a question of seconds. Check out the available samples and integration-guide.

------
## Vector Tiles
Vector tiles were created after the raster tiles. These are also squares, which together form a map. This time, these squares only contain the data, so you have to associate a style to it to finally have a map. This allows for more personalization and better interactions with the map.

We would recommend using MapLibre GL for vector tiles.

![alt text](./images/icons/maplibre.png "MapLibre")

Integrating MapSaudi maps with MapLibre GL is quick & easy. Check out the available samples and integration-guide.

------
## Desktop / Software
To use tiles in software, you need to know which Standard to apply. MapSaudi can talk to different standards. We expose TMS (also named Slippy-Map-Tile, or OpenStreetMap), and **WMTS** APIs. Also, WMS APIs can be opened for dynamic queries in our custom plans.

If you are using Tableau or GIS software such as **ArcGIS**, **ArcMap** or **QGIS**, carry on reading as we have provided specific implementations for it.

![alt text](./images/icons/arcmap.png "ArcGIS")

Integrate MapSaudi maps in **QGIS** version **2.0 or later** with the **WMTS** endpoint provided by MapSaudi. Since **QGIS** 3.14, they are also supporting vector tiles !

Integrate MapSaudi maps in **ArcGIS Desktop 10 or later** with the **WMTS** endpoint provided by MapSaudi.

Learn how with this tutorial:

![alt text](./images/icons/tableau.png "Tableau")

Integrate MapSaudi maps in **Tableau Desktop 10 or later** with the TMS files we provide for you.