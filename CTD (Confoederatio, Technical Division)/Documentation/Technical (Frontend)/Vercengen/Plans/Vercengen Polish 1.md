#Y2026 #vercengen
See also: [[Vercengen Plans]]

ve.NodeEditor
- arg1_options:
	- .settings: Object
		- .display_nodes_as_alluvial: boolean
		- .display_nodes_with_values: boolean
		- .synchronous_script_manager: boolean - Enables a synchronous ScriptManager that remains open during editing, with an 'Assign File to Node' button when a 'script' parameter is selected. Otherwise, it appears as an 'Assign File as Node', since it creates a new script mode instead
	- In Settings menu:
		- Display Nodes as Alluvial
		- Display Nodes with Values
		- Show Inspector for Local Variables
		- Show ScriptManager (if .synchronous_script_manager is enabled)
ve.ScriptManager
- this.\_file\_path should be set by default when creating a new file, and the new file should be 'opened'
- Settings to hide Codemirror
- Settings to change autosave folder (assuming that changing it is enabled for the user)
- Warnings if outside of the `.autosave_folder`, assuming that it is set

Vercengen localisation for:
- ve.NodeEditor
- ve.NodeEditorDatatype
- ve.ObjectInspector