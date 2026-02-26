Leaflet instances must be tracked, followed, focused, and cloned in browser, being mirrored into Maptalks in real time using a dynamic layer.

Ship tracking information is located in an Object[] at:

```js
capturedMaps[0]._zoomBoundLayers.?["<key>"].?_tiles["<key>"].el?.xhr?.responseJSON.data.rows
```

As unwieldy as this might be, individual rows listed in the array take the following JSON structure:

```js
{
	COURSE: "318"
	DESTINATION: "MEBAR"
	DWT: "3532"
	ELAPSED: "11"
	FLAG: "TR"
	GT_SHIPTYPE: "9"
	HEADING: "322"
	LAT: "37.523979"
	LENGTH: "87"
	LON: "20.844616"
	L_FORE: "75"
	SHIPNAME: "ALIYE HANIM"
	SHIPTYPE: "7"
	SHIP_ID: "335269"
	SPEED: "88"
	WIDTH: "12"
	W_LEFT: "4"
}
```

Here is what each of those characteristics refer to:
- `GT_SHIPTYPE` - Refers to ship subtypes, i.e. General Cargo/Bulk Carrier, etc. Their association can be fetched via the `input[name]` attribute under the Mui checkbox. Unknown ships do not carry a `GT_SHIPTYPE` attribute.
- `SHIPTYPE` - Refers to the macro-ship type, i.e. Cargo vessels/Tankers on Marinetraffic. Their association can be fetched via the `input[name]` attribute under the Mui checkbox.