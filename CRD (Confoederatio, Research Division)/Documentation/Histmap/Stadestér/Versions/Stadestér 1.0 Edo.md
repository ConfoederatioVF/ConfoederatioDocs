
| Stadestér 1.0 (Edo) | <                                                                                                                                                                                                                                                                                        |
| ------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Release Date        | 21 September 2025. 23:38GMT.                                                                                                                                                                                                                                                             |
| Patch Notes         | - Added both metro and non-metro adjusted versions for Stadestér<br>- Added methodological paper<br>- Archived all figures in Stadestér 1.0<br>- Finished release methodological paper<br>- Fixed substrata raster<br>- Uploaded static mirror versions and rasters to Gdrive and Proton |
| Database            | [[Stadestér]]                                                                                                                                                                                                                                                                            |
| Previous Version    | [[Stadestér 0.4b Caracol]]                                                                                                                                                                                                                                                               |
| Next Version        | [[Stadestér 1.0.1 Rome]]                                                                                                                                                                                                                                                                 |

## Abstract

Stadestér is an internally consistent global urban population database of ~41214 cities and their populations from 3000BC to 2025AD as taken from Buringh, Chandler, de Vries, GHSL, GHS-POP, Modelski, Populstat, Reba et al., and Wikipedia. Resultant data was standardised, geolocated, cubic spline interpolated, and calculated at 1-year intervals via weighted geometric averages. Reliability was assessed via comparisons to other demographic sources and long-run urban estimates, out-of-model sampling, regional centre of population/gravity comparisons, and manual copychecking prior to calibration, deviating by a mean of 17,4% (SD = 13%) of HYDE/UN estimates over the long run.

To avoid duplicate entries, cities were merged based on their physical distance from one other as well as their semantic similarity between both contemporary and historical names. Metropolitan networks were corrected for by subtracting suburban populations from their metro area, and redistributing any negative numbers held by the metropolitan area back to their suburbs in a proportional manner. Geolocation was achieved via automated Selenium/Puppeteer scraping, the Google Places API, Google Maps, Nominatim/OSM, and manual transcription.

Area, density, rate of natural increase (RNI), and geospatial distributions of population within cities are also available at annual resolution starting from 1800AD. Note that rasters have only been outputted for the subset of HYDE years from 3000BC-2025AD, and that we provide an open-source CLI for generating data from specific years, in addition to a custom UI tool for geoprocessing and visualisation (Constele Red). Area/density calculations were derived from Angel, Bairoch, Clark, Pasciuti and Chase-Dunn, and Stanilov and Sykora. The work of Hanson, Ortman, and Storey on classical populations have not yet been implemented.

We also naturally provide rasters of global overall population and non-urban population as an alternative to HYDE3.2/3.3 based on HYDE corrected for outliers, McEvedy and Jones, and GHS-POP. To replace masked outliers, we created custom climate models based on the ALCC work of KK10/LUH2 as rural population fallbacks. Both the main substrata and fallback substrata were calibrated to reliable estimates of regional and global population.

## Notes on Usage

All rasters (stadester_population_rasters, stadester_rural_rasters, stadester_urban_rasters) utilise WGS84 Equirectangular (4320x2160), or roughly 5-arcmin resolution as encoded in 32-bit int RGBA (little-endian) in PNG format.

City entries are contained in their respective JSON files. Two versions of this dataset are available at release, one including metro population adjustment to remove double-counting (metro_adjusted_rasters_and_json), and another without adjustment for discrete analysis (non_metro_adjusted_rasters_and_json). Static mirrors of both Stadestér 1.0's CLI and UI components are additionally made available with dependencies already bundled (see Appendix).

## Versioning

1.0 represents the release version of Stadestér. The first number of each database version qualitative expansions in the types of data presented (i.e. new variables), whilst changes in the second number represent any quantiative changes or expansions of existing fields. A third digit is reserved for any changes made that is not directly related to the data presented where applicable.

Stadestér 1.0's methodological paper, including testing and validation of the dataset, is attached below.

- All Versions: [[Stadestér]]
- [[Stadestér 1.0 Edo]]
- [[Stadestér 1.0.1 Rome]]
- [[Stadestér 1.1 Cusco]]