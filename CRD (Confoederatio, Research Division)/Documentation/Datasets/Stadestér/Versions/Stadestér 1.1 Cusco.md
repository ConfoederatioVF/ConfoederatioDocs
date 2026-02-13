#wip

| Stadestér 1.1 (Cusco) | <                                   |
| --------------------- | ----------------------------------- |
| Release Date          | Proposed Version                    |
| Patch Notes           | None                                |
| Database              | [[Stadestér]]                       |
| Previous Version      | [[Stadestér 1.0.1 Rome]]            |
| Research Notes        | [[1. Stadestér 1.1 Research Notes]] |
## Abstract

**Stadestér 1.1** should be a complete overhaul of [[Stadestér 1.0 Edo]] as it currently stands since there turned out to be major errors with [Reba et al.](https://www.nature.com/articles/sdata201634), whose work should generally be treated with extreme caution due to issues with transcription. As a result, future plans should generally exclude Chandler/Modelski digitalisations that come from there.

Until [[Naissance HGIS]] fully matures, Stadestér 1.1 would be built as an independent [[Vercengen]] app to aid in data visualisation and graph production or viewing. [[Echarts]] would be used for visualisation. This would also help with creating a public data portal for Stadestér that would make sense as a stopgap until Naissance is capable of exporting data portals to a browser view.
## Methodology

The planned methodology behind Stadestér 1.1 is a complete reset of merging and processing logic to make it more clear and reproducible with public ground-truthing benchmarks and automated testing against known comparisons.

This methodology will primarily be split up into 5 main phases:
1. Data structure planning (this is necessary to track source provenance and for projecting different visualisations from the same database)
	1. Improve proximity merging logic so that candidates to merge into are only valid over their time domain
	2. Historical name handling should be included so that cities can be dynamically renamed based on their specified time period/entry. This should be capable of handling multiple names via a join (string[])
2. Prehistoric (3700BC-2000BC)
   
   The work of [Andrea Biguzzi](https://www.worldcitypop.com/data.asp) should form the basis of this dataset with percentage-based relative declines/increases to benchmark populations contained here. This would involve the following steps:
	1. Latlng geolocation scripting for all cities in the world city population database, as well as consistent source tracking in metadata/localisation terms.
	2. Relative anchoring with Biguzzi as GT and Chandler/Modelski changes representing RNI (rate of natural increase) between averaged anchor points.
1. Preindustrial (2000BC-1800AD)
	1. Merging of Populstat from [[Stadestér 1.0 Edo]] with Biguzzi/Chandler/Modelski via proximity/semantic merging
	2. Merging with Buringh (geomean)
	3. Add outlier mask for Jakarta, Indonesia
	4. (Velkscala): REVISIT
		1. Rework Nelson adjustment by using percentage growth instead of OCR pixel radius DONE
			1. Reprocess substrata DONE
	5. Remove DeVries from dataset, use Buringh only when merging (Biguzzi already included DeVries)
2. Industrial (1800AD-1975AD)
	1. Metro buffering (1800-1945), with interactive spatiotemporal visualisations (see Python code). This buffering code should be identical to that of Stadestér 1.0 since it performed quite well in Jaccard index terms.
3. Modern (1975-2025AD)
	1. GHSL data combined with GHS-POP
	2. Remove Stadestér-GHSL discontinuities
		1. Take the highest population from base GHS POP pixel if the city no longer exists in Stadestér-GHSL and retain it until 2025
		2. Remaining (occupied pixel cities) should have their GHS POP pixel values assessed within their moore neighbourhood (so long as the pixel is not grabbed by a higher pop city) and then proportionally distribute the values based on the sum values within the metro system
		3. The area assigned to each GHSL city should then also be proportional to its population (temporary until a better system is devised for processing satellite data), density can then be calculated normally
## Plans

| Name                   | Status      |
| ---------------------- | ----------- |
| [[Stadestér 1.1 TODO]] | NOT STARTED |
## Research Notes

**Stadestér 1.1:**
- [[Stadestér 1.1 Proposed Methodology]]