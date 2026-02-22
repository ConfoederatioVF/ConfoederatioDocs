```js
/**
 * Extractor for OpenLayers features stored in Pinia.
 * Navigates: map-store -> layers -> vessels_markers -> values_ -> source
 */
window.getVesselsFromOL = function () {
  // 1. Access Pinia State directly (Reliable)
  const root = document.querySelector("#app") || document.querySelector("[data-v-app]");
  if (!root || !root.__vue_app__) return "Vue 3 app not found.";
  
  const pinia = root.__vue_app__.config.globalProperties.$pinia;
  const state = pinia.state.value;
  const mapStore = state["map-store"];

  if (!mapStore || !mapStore.layers || !mapStore.layers.vessels_markers) {
    return "Could not navigate to map-store.layers.vessels_markers";
  }

  // 2. Navigate to the Source (using your hint)
  const layer = mapStore.layers.vessels_markers;
  const source = layer.values_?.source || layer.source;

  if (!source) return "OpenLayers Source not found.";

  // 3. Get Features (This pulls the live array of ship objects)
  const features = source.getFeatures ? source.getFeatures() : [];
  if (features.length === 0) return "No features found in the source.";

  /**
   * Manual Projection Converter (EPSG:3857 to EPSG:4326)
   * Required because OpenLayers coordinates are in meters.
   */
  const toLonLat = (coords) => {
    const x = coords[0];
    const y = coords[1];
    const lon = (x * 180) / 20037508.34;
    let lat = (y * 180) / 20037508.34;
    lat = (180 / Math.PI) * (2 * Math.atan(Math.exp((lat * Math.PI) / 180)) - Math.PI / 2);
    return [lon, lat];
  };

  // 4. Build GeoJSON
  const geojson = {
    type: "FeatureCollection",
    features: features.map((f) => {
      const geom = f.getGeometry();
      const rawCoords = geom.getCoordinates();
      const cleanCoords = toLonLat(rawCoords);

      // Get metadata (MMSI, Name, etc.)
      // OL stores these in the 'values_' property or via getProperties()
      const props = f.getProperties ? f.getProperties() : (f.values_ || {});

      // Clean up properties to avoid circular references
      const cleanProps = { ...props };
      delete cleanProps.geometry; 

      return {
        type: "Feature",
        geometry: {
          type: "Point",
          coordinates: cleanCoords,
        },
        properties: cleanProps,
      };
    }),
  };

  console.log(`Successfully extracted ${geojson.features.length} vessels.`);
  return geojson;
};

/**
 * Utility to download the resulting GeoJSON
 */
window.downloadVessels = function() {
    const data = window.getVesselsFromOL();
    if (typeof data === 'string') {
        console.error(data);
        return;
    }
    const blob = new Blob([JSON.stringify(data, null, 2)], {type: "application/json"});
    const url = URL.createObjectURL(blob);
    const a = document.createElement("a");
    a.href = url;
    a.download = `vessels_data_${Date.now()}.geojson`;
    a.click();
    URL.revokeObjectURL(url);
};

```

URL: https://www.aisfriends.com/embed?lat=49&lon=6.3&zoom=2&types=4&names=true&menu=false

```
https://www.aisfriends.com/vessels/bounding-box?lon_min=-180&lat_min=-90&lon_max=180&lat_max=90&zoom=12&types=4
```