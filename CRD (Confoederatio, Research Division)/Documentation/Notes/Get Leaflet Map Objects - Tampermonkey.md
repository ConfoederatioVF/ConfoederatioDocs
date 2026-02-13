#tampermonkey #leaflet #scraping

```js
// ==UserScript==
// @name         Leaflet Map Instance Tracker
// @namespace    http://tampermonkey.net/
// @version      1.0
// @description  Intercepts and stores all Leaflet map instances in a global array.
// @match        *://*/*
// @run-at       document-start
// @grant        none
// ==/UserScript==

(function () {
  "use strict";

  // This array will hold all map instances found on the page
  window.capturedMaps = [];

  let leafletBackend;

  // We define a getter/setter on window.L to catch the moment Leaflet loads
  Object.defineProperty(window, "L", {
    get: function () {
      return leafletBackend;
    },
    set: function (newLeaflet) {
      leafletBackend = newLeaflet;

      // Ensure we have the Map object and haven't hooked it yet
      if (leafletBackend && leafletBackend.Map && !leafletBackend._hooked) {
        leafletBackend._hooked = true;

        console.log("Leaflet detected! Injecting initialization hook...");

        leafletBackend.Map.addInitHook(function () {
          window.capturedMaps.push(this);
          console.log("New Leaflet map instance captured:", this);
        });
      }
    },
    configurable: true,
  });

  // Optional: Expose a helper function to the console to interact with maps
  window.getMaps = () => window.capturedMaps;
})();
```