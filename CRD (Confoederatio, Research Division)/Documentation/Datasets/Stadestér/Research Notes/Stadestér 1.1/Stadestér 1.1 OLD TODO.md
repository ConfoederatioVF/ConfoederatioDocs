> [!WARNING]
> The content of **Research Notes** may or may not be duplicated elsewhere, depending on status.

- add outlier mask for jakarta, indonesia
- rework nelson adjustment by using percentage growth instead of OCR pixel radius
  - reprocess substrata
- fix barrow, alaska
- fix bristol duplicate by relocating coordinates across all constituent datasets
- modify metro adjustment
  - all marked agglomerations should be disaggregated, with their population figures assigned to the nearest non-agglomeration city in terms of coordinates. the object should then be deleted, and the resulting non-agglomeration city renamed
- remove non-metro adjusted distributions, as they are no longer necessary
- improve merging logic so that candidates to merge into are only valid over their domain
- remove stadestér-GHSL discontinuities
  - take the highest population from base GHS POP pixel if the city no longer exists in stadestér-GHSL and retain it until 2025
  - remaining (occupied pixel cities) should have their GHS POP pixel values assessed within their moore neighbourhood (so long as the pixel is not grabbed by a higher pop city) and then proportionally distribute the values based on the sum values within the metro system
  - the area assigned to each GHSL city should then also be proportional to its population (temporary until a better system is devised for processing satellite data), density can then be calculated normally

- regenerate population rasters
- round all final population figures in JSON

- http://www.worldcitypop.com/data.asp this table is averaged w/ proximity time windows, and is better than chandler/modelski
  - this is bcus it uses avg's of estimates w/ in a time win
- cleaned chandler/modelski declines/increases % wise from the base yr should b taken into acc for yrs between intervals
- new base dataset