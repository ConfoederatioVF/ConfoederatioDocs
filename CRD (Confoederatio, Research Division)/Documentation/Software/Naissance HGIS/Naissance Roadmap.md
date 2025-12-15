---
cover: https://i.postimg.cc/Rhp5GKJS/embed-template-naissance.png
description: The current TODO list and roadmap for Naissance HGIS and any supporting Vercengen Components and features.
---
S+00 is needed to prepare both [[Vercengen]] and [[Naissance HGIS]] for future work on Mapmode Scripting and other basic features.

S+00: Preparation Work
- Masks:
	- Masks for Groups:
		- Difference from Brush
		- Intersection for Brush
	- Group Operations:
		- Mask Operations for Groups:
			- Clip Group to Brush Intersection
			- Difference Brush from Group
		- Merge Operations:
			- Merge Groups
				- Polygons are mutually exclusive
- Settings:
	- Confirmation prompt for deleting Groups/Layers (veToggle)
- Update Vercengen for Naissance HGIS's needed capabilities: (this should be worked on first)
	- ve.DAG (Directed Acyclic Graph)
	- ve.Graph
		- Echarts GUI bindings with UI Editor that can take in CSVs via ve.Table and a documentation guide on how to format data for different chart types
	- ve.ObjectInspector
	- ve.NodeEditor
	- ve.NodeEditorExpression - Iterates over an Array\<Object\> and executes a function per object, unless `arg1_options.singleton=true`
	- ve.NodeEditorFilter - Returns an Array\<Object\>
	- ve.ScriptManager should be able to configure a build list of multiple files using file patterns and ve.List
	- ve.SearchSelect (see Discord for more information) DONE
	- ve.WYSIWYG should be updated to use all Vercengen components
	  
	- Vercengen should have template strings for positioning Windows that dynamically adjust the X/Y coords based on the height/width of other Windows

- Shift Keyframes button for Features/Geometries
	- Options:
		- Delete disconnected keyframes
		- Shift Keyframes Down \<Date Length\>
		- Shift Keyframes Up \<Date Length\>

S+01: Basic Feature Work
- Vercengen should have .sfx bindings that can play a sound effect upon activation
- `.keybind` genericisation using Mousetrap

**Note.** Mapmode scripting should ideally work via `Entity Filtering > Property Querying Per Entity > Property Filtering > Set Symbol` in a node-based setup.

- Generic Expressions registry
	- Get Property Expression
	- Get Variable Expression
	- Overlay Geometry expression (temporary object bound to mapmode)
	- Overlay Label expression (temporary object bound to mapmode)
	- Run Script Expression (use ve.ScriptManager)
	- Set Symbol
		- Symbol registry (in config)
- Generic Filter registry
- Mapmode node-based scripting
- Mapmode UI should be available at the bottom right on top of the brush, and should work similarly to EU4
- ve.Graph integration for Variables Editor/Node Editor

S+02: Import/Export Work, Time Control
- Integrate file formats supported by https://github.com/maptalks/maptalks.formats for importing to GeoJSON
	- Import As Group Button (placed after divider in Leftbar Hierarchy)
- Export GeoJSON back out to CSV/GPX/KML/WKT/TopoJSON/OSM/SHP. [Mapshaper](https://github.com/mbloch/mapshaper) supports such exports.
	- Export Group Button (in context menu)
	- Export Options:
		- Export at Date (main.date by default)
		- Export Hidden (false by default)
		- Flatten Features (false by default)
- Import Expression for Node Editor
- Export Expression for Node Editor

- Model Builder for Node Editor
	- Assign Entity to Group Expression
	- Assign Entity to Layer Expression
	- Create Feature Expression
	- Create Geometry Expression
	  
	- Add Keyframe Expression (sequential arguments)
	- Move Keyframe Expression (sequential arguments)
	- Remove Keyframe Expression (sequential arguments)
	- Shift Keyframe Expression (sequential arguments)
- Timelapse controls for Date (top right corner)