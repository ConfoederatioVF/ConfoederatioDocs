**Algorithmic Approach:**

**What's actually needed to determine polygon shapes?**

1. Lab-space kNN binning (map to legend)
2. Legend detection (drag-select), automatically detect colour swatches
3. Unioning duplicates

[This](https://colab.research.google.com/drive/1--W2P96BMFV8-9ZZLDjvKxwrIvU_ugUK#scrollTo=B2-IPgn_dTkg) exercise solved #2 and #3, but not #1.

**ML Segmentation:**
- **Library:** segment-anything
- `samgeo` (Segment Geospatial). This is a specialised wrapper that allows you to use SAM specifically for geographic data. It can take a prompt (like 'find all red areas') and output a GeoJSON.
	- Website: https://samgeo.gishub.org/
	- Video with Leaflet: https://www.youtube.com/watch?v=n-FZzKirE9I&list=PLAxJ4-o7ZoPcrg5RnZjkB_KY6tv96WO2h&index=7
- Mapkurator (labels only): https://knowledge-computing.github.io/mapkurator-doc/#/docs/introduction

- Cliopatria also tackled this problem: https://www.nature.com/articles/s41597-025-04516-9
## Proposed Workflow (Collation):

1. Geowarp source:
	1. Image from Clipboard **OR**
	2. Source scrape (must return image at designated path). This is so that image sources can be georeferenced over a long duration without manual population/interference
2. Auto-polygonisation from geowarped source
	1. Lab-space kNN binning (map to legend)
	2. Legend detection (drag-select), automatically detect colour swatches
		1. If a legend is not detected, a manual legend can be quickly created
		2. By default, the auto-populated legend will use Lab-space kNN binning with colour distance; proximity thresholds
	3. Union duplicates
3. Convert to GeoJSON

## Consistent Solutions

Consistent solutions for contested regions of the world in which sovereignty changes rapidly are as follows:

- Deepstatemap (Ukraine only)
- ISW (kNN-binning extraction)
- Liveuamap (global)
- Suriyakmaps
- Wikipedia SVGs (global, best quality)

At start, it is recommended for data to come from Wikipedia SVGs. Control polygons should have probability ranges for contested areas.