---
cover: https://i.postimg.cc/qvvmDC6H/embed-template.png
description: Planning for Confoederatio 2.0 regarding updated infrastructure, including for both tooling and core databases throughout 2026.
---
This page details the current backlog relevant to [[Confoederatio]], as well as the dates at which any changes have been committed to **Confoederatio projects** by namespace.

Current priorities are highlighted in ==YELLOW==.

==**Maintenance Backlog** (February 2026):==
- Update Snow Zed npm version
- Update Triumph & Tragedy npm version

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
		- Fix so that Tippy tooltips are globally anch#plans #confoederatio #Y2026

See also: [[Confoederatio]]

Also referred to as [[19 December 2025 - Confoederatio 2.0|Confoederatio 2.0]], **Confoederatio26** is the main yearly plan for Confoederatio progress in the sense of achieving polished versions of existing infrastructure and solidifying both core tools and databases for future work and progress.
## Timetable

Dates are specified as being when projects end, i.e. deadlines, not when they start.

- 31 January 2026: [[Vercengen]] 1.0 Release - Software Engine
    - ve.Colour should take in RGBA inputs if specified DONE
    - ve.DatavisSuite WIP
    - ve.FlexInterface DONE
    - ve.Graph WIP
    - ve.GraphLegend WIP
    - ve.GraphText WIP
    - ve.NodeEditor DONE
	    - ve.NodeEditor polish: abort button, time elapsed per node, run/preview DAG from node
    - ve.NodeEditorDatatype DONE
    - ve.ObjectInspector DONE
    - ve.ScriptManager DONE
	    - .autosave_folder should be changed to .project_folder, with the ability to move the project folder DONE
	    - Ergonomics for Blockly/Codemirror should be automatically managed based on ES6-compatibility DONE
		    - Blockly should be hidden upon onload errors, and if no onload errors were detected, the display should be restored DONE
		    - Onload should be lossless rather than converting to Blockly DONE
	    - Manual synchronisation toggle that disables synchronisation between Codemirror <-> Blockly and makes it manual instead DONE
	    - Migrate themes and settings to be Monaco compatible DONE
	    - Multiple language recognition/project folder documentation DPME
    - ve.ScriptManagerBlockly should be moved to a dedicated iframe DONE
    - ve.ScriptManagerCodemirror should be swapped for ve.ScriptManagerMonaco DONE
    - ve.Range now takes in number inputs DONE
    - ve.Table
	    - Option to change the number of results per page (number[] option, predefined)
	    - Page number input
	    - ve.Table should have an optional searchbar
	- ve.UndoRedo should support manual commits
	- ve.Window should define scene height (this will help exclude navbar_el by default)
    - Renaming Vercengen components WIP
	    - ve.BIUF > ve.RichText DONE
	    - ve.Table > ve.Spreadsheet DONE
	    - ve.WYSIWYG > ve.WordProcessor DONE
		    - Polish work for ve.WordProcessor
- 31 March 2026:  [[Stadestér 1.1 Cusco]] Release - Historical Urban Database
- 31 April 2026: [[Velkscala 1.0]] Release - Historical Demographic Database
- 31 July 2026: [[Naissance HGIS]] 1.0 Release - 4D Integrated Research Environment (IRE)
- 31 August 2026: Web infrastructure work
    - https://confoederatio.org/ modernisation work
    - Confoederatio Docs completeness
    - Naissance HGIS data portal/livemap capability
	    - Porting Stadestér/Velkscala to Naissance HGIS
	- Finish updating READMEs for GitHub and synchonisation with Confoederatio Docs
- 31 December 2026: Finish database polish work
    - Stadestér 1.2 (currently 1.0)
    - Eoscala 1.5 (currently 1.2) - Historical Economic Database
    - Atlas 1.0, intermittent work on Atlas via Naissance HGIS. Currently substituted with Cliopatria. Historical Boundary Databaseored, and not anchored to the element at hand DONE
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
	- Finish porting other backend utils functions from old UF DONE
		- Reform multiline literal comments to use `<br>- ` formatting for bullet points/indentation DONE
		- ==Add logging system to Vercengen with multiple logging channels that can be selected and prefix formats==
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