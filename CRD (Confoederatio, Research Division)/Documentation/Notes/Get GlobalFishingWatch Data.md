**GFW** appears to use Deck.gl, which is defined as `deck`. Calls from API are known to be obfuscated, but the raw HTML side ledgers from: https://globalfishingwatch.org/map/vessel-search provide end of year locations based on MMSI, i.e. https://globalfishingwatch.org/map/vessel-search?qry=%20368972000&sO=basic&lTD=&fTD= for the USS Mahan.

Because there is not much can be done in the way that tiles are overlaid, base tiles will have to be JPEG blasted back to the main map in order to ensure that a valid overlay can be drawn. On the other hand, individual ship geometries can be extracted once targeted, i.e. at URLs such as: [this](https://globalfishingwatch.org/map/fishing-activity/default-public/vessel/668844fb5-531d-25c5-50bc-aee6b1fa6529?lTD=&fTD=&longitude=-66.67964935302734&latitude=17.818082794252348&zoom=10.031239359825273&dvIn[0][id]=vessel-group-1771842886386&dvIn[0][category]=vesselGroups&dvIn[0][cfg][clr]=%23FFAE9B&dvIn[0][cfg][vis]=true&dvIn[0][cfg][filters][vGs][0]=gerald_r_ford_338803000-user-public&dvIn[0][cfg][dss][0]=public-global-presence%3Av3.0&dvIn[0][cfg][dss][1]=public-chile-presence%3Av20211126&dvIn[0][cfg][dss][2]=public-panama-presence%3Av20211126&dvIn[0][cfg][dss][3]=public-norway-presence%3Av20220112&dvIn[0][cfg][dss][4]=public-png-presence%3Av20230210&dvIn[0][cfg][colorRamp]=salmon&dvIn[0][dvId]=presence-activity-v-3&dvIn[1][id]=vessel-090410a5e-e4eb-1ca9-104d-28c8380a01dc&dvIn[1][dvId]=fishing-map-vessel-track-v-3&dvIn[1][cfg][track]=~1&dvIn[1][cfg][info]=public-global-vessel-identity%3Av3.0&dvIn[1][cfg][events][0]=~3&dvIn[1][cfg][events][1]=~4&dvIn[1][cfg][events][2]=~5&dvIn[1][cfg][events][3]=~6&dvIn[1][cfg][events][4]=~7&dvIn[1][cfg][clr]=%23F95E5E&dvIn[1][dT]=true&dvIn[2][id]=vessel-9f64a3b2d-d8b5-1e79-fa71-05cbf86d8021&dvIn[2][dvId]=fishing-map-vessel-track-v-3&dvIn[2][cfg][track]=~1&dvIn[2][cfg][info]=public-global-vessel-identity%3Av3.0&dvIn[2][cfg][events][0]=~3&dvIn[2][cfg][events][1]=~4&dvIn[2][cfg][events][2]=~5&dvIn[2][cfg][events][3]=~6&dvIn[2][cfg][events][4]=~7&dvIn[2][cfg][clr]=%2333B679&dvIn[2][dT]=true&dvIn[3][id]=vessel-9d14d1a03-34df-3705-1d61-2476b9eae18a&dvIn[3][dvId]=fishing-map-vessel-track-v-3&dvIn[3][cfg][track]=~1&dvIn[3][cfg][info]=public-global-vessel-identity%3Av3.0&dvIn[3][cfg][events][0]=~3&dvIn[3][cfg][events][1]=~4&dvIn[3][cfg][events][2]=~5&dvIn[3][cfg][events][3]=~6&dvIn[3][cfg][events][4]=~7&dvIn[3][cfg][clr]=%23F09300&dvIn[3][dT]=true&dvIn[4][id]=vessel-f0d807cba-a6fe-4512-4283-f1abd68b71b9&dvIn[4][dvId]=fishing-map-vessel-track-v-3&dvIn[4][cfg][track]=~1&dvIn[4][cfg][info]=public-global-vessel-identity%3Av3.0&dvIn[4][cfg][events][0]=~3&dvIn[4][cfg][events][1]=~4&dvIn[4][cfg][events][2]=~5&dvIn[4][cfg][events][3]=~6&dvIn[4][cfg][events][4]=~7&dvIn[4][cfg][clr]=%23F4511F&dvIn[4][dT]=true&dvIn[5][id]=vessel-3613d484e-eacf-d604-8ae4-25d1cffb2054&dvIn[5][dvId]=fishing-map-vessel-track-v-3&dvIn[5][cfg][track]=~1&dvIn[5][cfg][info]=public-global-vessel-identity%3Av3.0&dvIn[5][cfg][events][0]=~3&dvIn[5][cfg][events][1]=~4&dvIn[5][cfg][events][2]=~5&dvIn[5][cfg][events][3]=~6&dvIn[5][cfg][events][4]=~7&dvIn[5][cfg][clr]=%230B8043&dvIn[5][dT]=true&dvIn[6][id]=vessel-38c1fc061-1fa3-5afc-409e-c880af955ecf&dvIn[6][dvId]=fishing-map-vessel-track-v-3&dvIn[6][cfg][track]=~1&dvIn[6][cfg][info]=public-global-vessel-identity%3Av3.0&dvIn[6][cfg][events][0]=~3&dvIn[6][cfg][events][1]=~4&dvIn[6][cfg][events][2]=~5&dvIn[6][cfg][events][3]=~6&dvIn[6][cfg][events][4]=~7&dvIn[6][cfg][clr]=%234184F4&dvIn[6][dT]=true&dvIn[7][id]=vessel-5a1df292c-c5e8-3739-ce0c-eb05d29a902c&dvIn[7][dvId]=fishing-map-vessel-track-v-3&dvIn[7][cfg][track]=~1&dvIn[7][cfg][info]=public-global-vessel-identity%3Av3.0&dvIn[7][cfg][events][0]=~3&dvIn[7][cfg][events][1]=~4&dvIn[7][cfg][events][2]=~5&dvIn[7][cfg][events][3]=~6&dvIn[7][cfg][events][4]=~7&dvIn[7][cfg][clr]=%23AD1457&dvIn[7][dT]=true&dvIn[8][id]=basemap-labels&dvIn[8][cfg][vis]=false&dvIn[9][id]=ais&dvIn[9][cfg][vis]=false&dvIn[10][id]=vms&dvIn[10][cfg][vis]=false&dvIn[11][id]=basemap&dvIn[11][cfg][basemap]=satellite&bDV&tV=vesselGroup&start=2026-01-22T00%3A00%3A00.000Z&end=2026-02-22T00%3A00%3A00.000Z&vDi=public-global-vessel-identity%3Av3.0&vIs=selfReportedInfo&vSRi=668844fb5-531d-25c5-50bc-aee6b1fa6529&vE[0]=loitering&vE[1]=encounter&vE[2]=port_visit&vE[3]=gap&tk[0]=fishing-map-vessel-track-v-3&tk[1]=public-global-all-tracks%3Av3.0&tk[2]=public-global-vessel-identity%3Av3.0&tk[3]=public-global-fishing-events%3Av3.0&tk[4]=public-global-port-visits-events%3Av3.1&tk[5]=public-global-encounters-events%3Av3.0&tk[6]=public-global-loitering-events%3Av3.0&tk[7]=public-global-gaps-events%3Av3.0)

```js
window.findDeckData = function () {
      // 1. Find the canvas element used by Deck.gl
      const canvas = document.querySelector(".mapboxgl-canvas") || document.querySelector("canvas");
      if (!canvas) return console.error("Could not find map canvas.");

      // 2. Find the React Internal Key
      const fiberKey = Object.keys(canvas).find((key) => key.startsWith("__reactFiber") || key.startsWith("__reactInternalInstance"));
      if (!fiberKey) return console.error("Could not find React Fiber on this element.");

      // 3. Walk up the React tree to find the DeckGL component
      let walker = canvas[fiberKey];
      let layers = null;

      while (walker) {
          if (walker.memoizedProps && walker.memoizedProps.layers) {
              layers = walker.memoizedProps.layers;
              break;
          }
          walker = walker.return;
      }

      if (layers) {
          window.GFW_LAYERS = layers;
          console.log("%c Found Deck.gl Layers! ", "background: #222; color: #00e676; font-size: 14px;");

          // Create a summary for the user
          const summary = layers.map(l => ({
              id: l.id,
              type: l.constructor.name,
              dataLength: l.props.data ? (Array.isArray(l.props.data) ? l.props.data.length : 'Complex/Tile') : 0
          }));

          console.table(summary);
          console.log("Access them via: window.GFW_LAYERS");
      } else {
          console.warn("Found React tree but no 'layers' prop. Try zooming/panning the map and running this again.");
      }
  }
  
window.digSubLayers = function () {
  // Find the vessel layer (it was index 1 in your previous output)
  const vesselLayer = window.GFW_LAYERS.find((l) => l.id.startsWith('vessel-'));

  if (!vesselLayer || !vesselLayer.internalState.subLayers) {
    return console.error('Vessel layer or sublayers not found.');
  }

  console.log(`Digging into ${vesselLayer.internalState.subLayers.length} sub-layers...`);

  vesselLayer.internalState.subLayers.forEach((sl, i) => {
    // 1. Check if the sublayer has data in props
    const data = sl.props.data;
    
    // 2. Check if the sublayer has attributes (Binary Data)
    const attributes = sl.state && sl.state.attributeManager 
	   ? sl.state.attributeManager.attributes 
	   : null;

    if (attributes && attributes.instancePositions) {
      console.log(`%c Found Points in Sub-Layer [${i}] (${sl.id})`, 'color: #00ff00');
      console.log('Coordinates (Binary):', attributes.instancePositions.value);
      window.vesselPoints = attributes.instancePositions.value;
    } 
    
    if (attributes && attributes.positions) {
      console.log(`%c Found Path/Line in Sub-Layer [${i}] (${sl.id})`, 'color: #00ff00');
      console.log('Coordinates (Binary):', attributes.positions.value);
      window.vesselPath = attributes.positions.value;
    }

    if (data && data.length > 0) {
        console.log(`Sub-Layer [${i}] (${sl.id}) has ${data.length} data items.`, data);
    }
  });
};
```