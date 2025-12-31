> [!WARNING]
> The content of **Research Notes** may or may not be duplicated elsewhere, depending on status.

#stadestér #research_notes

When creating Stadestér 1.1 as a [[Vercengen]] app, the codebase should be rebuilt from scratch to allow for cleaner long-term data structuring since it should be structured as software, and not merely as a database.

Additionally, both [[Velkscala]] and [[Project Centaur]] will be transferred to Stadestér as a joint database.

A new methodology will primarily be split up into 5 main phases:
1. Data structure planning (this is necessary to track source provenance and for projecting different visualisations from the same database)
	1. Improve proximity merging logic so that candidates to merge into are only valid over their time domain
	2. Historical name handling should be included so that cities can be dynamically renamed based on their specified time period/entry. This should be capable of handling multiple names via a join (string[])
2. Prehistoric (3700BC-2000BC)
   
   The work of [Andrea Biguzzi](https://www.worldcitypop.com/data.asp) should form the basis of this dataset with percentage-based relative declines/increases to benchmark populations contained here. This would involve the following steps:
	1. Latlng geolocation scripting for all cities in the world city population database, as well as consistent source tracking in metadata/localisation terms.
3. Preindustrial (2000BC-1800AD)
	1. Merging of Populstat from [[Stadestér 1.0 Edo]] with Biguzzi/Chandler/Modelski.
	2. Add outlier mask for Jakarta, Indonesia
	3. (Velkscala):
		1. Rework Nelson adjustment by using percentage growth instead of OCR pixel radius
			1. Reprocess substrata
	4. Remove DeVries from dataset, use Buringh only when merging (Biguzzi already included DeVries)
4. Industrial (1800AD-1975AD)
	1. Metro buffering (1800-1945), with interactive spatiotemporal visualisations (see Python code). This buffering code should be identical to that of Stadestér 1.0 since it performed quite well in Jaccard index terms.
5. Modern (1975-2025AD)
	1. GHSL data combined with GHS-POP
	2. Remove Stadestér-GHSL discontinuities
		1. Take the highest population from base GHS POP pixel if the city no longer exists in Stadestér-GHSL and retain it until 2025
		2. Remaining (occupied pixel cities) should have their GHS POP pixel values assessed within their moore neighbourhood (so long as the pixel is not grabbed by a higher pop city) and then proportionally distribute the values based on the sum values within the metro system
		3. The area assigned to each GHSL city should then also be proportional to its population (temporary until a better system is devised for processing satellite data), density can then be calculated normally