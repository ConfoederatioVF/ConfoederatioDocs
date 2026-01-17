---
cover: https://i.postimg.cc/qvvmDC6H/embed-template.png
description: Planning for Confoederatio 2.0 regarding updated infrastructure, including for both tooling and core databases throughout 2026.
---
#plans #confoederatio #Y2026

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
    - Atlas 1.0, intermittent work on Atlas via Naissance HGIS. Currently substituted with Cliopatria. Historical Boundary Database