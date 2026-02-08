This page details the current backlog relevant to [[Confoederatio]], as well as the dates at which any changes have been committed to **Confoederatio projects** by namespace.

Current priorities are highlighted in ==YELLOW==.

**Vercengen** (February 2026):
- Release 1.0.1 with given patch notes. DONE
- Release 1.0.2:
	- Telestyle:
		- Fix Telestyle themes
		- Fix Telestyle to be able to handle dynamic immediate modes
	- ve.Feature:
		- Integrate ve.Feature to have Telestyle
		- Integrate methods from ve.Component into ve.Feature
	- ve.Tooltip: DONE
		- Fix so that Tippy tooltips are globally anchored, and not anchored to the element at hand DONE
		- Needs fixing so that its text height is bound to the body text height DONE
	- ve.UndoRedo
		- Manual commits to DALS using diff states/temp saves
			- Mode selector for toggling between manual commit modes
		- The 1st action in DALS doesn't jump to that action, but the 2nd and 3rd ones do
	- ve.ScriptManager
		- ScriptManager should be able to handle multiple instances for Monaco
		- ScriptManager should restore views and code folding when switching between files
	- ve.Window
		- Fix UIs using windows for Naissance HGIS
	- Release 1.0.2 with patch notes
- Release 1.0.3:
	- Finish porting Geospatiale II to Geospatiale III with namespaces DONE
	- Finish porting other backend utils functions from old UF WIP
		- Reform multiline literal comments to use `<br>- ` formatting for bullet points/indentation
		- Add logging system to Vercengen with multiple logging channels that can be selected and prefix formats
	- Release 1.0.3 with patch notes
**SVEA** (February 2026):
- ==(Histmap) **KK10/LUH2:**==
	1. Convert HYDE to GeoPNGs
	2. Scale HYDE to McEvedy
	3. Scale HYDE to global population estimates
	4. Scale KK10/LUH2 to Nelson based on delta change rates (backcalculation based on graph extraction % Pop Change/decade). Contemporary populations backcalculated from GHS-POP
	5. Scale KK10/LUH2 to OWID
	6. Scale KK10/LUH2 to global population estimates
	7. Outlier masking: make sure to add missing outlier for Jakarta, Indonesia
	8. Create global population substrata map with previous methodology
	9. Add node-based view for processing KK10/LUH2 Substrata
	10. Project Centaur handling for Northern America (from Stadestér)
- **Naissance HGIS:**
	- Save name/highlighting by 'Naissance HGIS' in Navbar, it should have the name of the save/project instead
	- The last project opened should be automatically reopened when launching Naissance HGIS
	  
	- <u>DALS</u>:
		- Integration for variable Editors
		- Variable editors should save formatting. Make sure they do!
	- <u>Naissance Entities</u>:
		- Entity time domains with `.is_starting_frame`: boolean with starting frame recognition
	- <u>Mapmodes</u>:
		- naissance.Mapmode:
			- is_default: boolean - sets this mapmode as a default mapmode from the beginning
			- mode: string - 'default'/'overlay'/'override'
				- default: colours default geometries in entity layer
				- overlay: layers on geometries either below or under the entity layer
			- override: boolean - resets all mapmodes and ensures that is the only mapmode available
		- Mapmode indicators with index in top right corner
		- Set mapmodes to last saved mapmodes when loading saves
		- Store non-default mapmodes save-side
			- Add New Mapmode
			- Delete Mapmode (only available for non-default mapmodes)
			- Mapmode Node Editors should be run in JS form `special_function`
			- Remove Mapmode
			- Reorder Mapmodes
	- **Geospatiale IV:**
		- Make sure that all methods from Geospatiale III dealing with file conversions have default async modes, and that non-async modes should be marked with a `Sync` suffix