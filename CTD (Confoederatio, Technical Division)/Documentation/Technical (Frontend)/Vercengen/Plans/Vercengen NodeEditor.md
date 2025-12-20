Remaining logic:
- 'script' type for ve.NodeEditorDatatype.openContextMenu() WIP
- Fix bug where deleting the node being connected to doesnt delete its relevant connections
- Fix bug where default values are not used instead of undefined if parameter is set to a constant_value then disabled
- Fix bug where previews are not live upon ve.NodeEditorDatatype.draw() call
	- Add .id to ve.NodeEditor
	- options.dag_sequence should be deprecated
	- All unique .node_editor instances should be run

- fromJSON/toJSON implementation for ve.NodeEditorDatatype
- fromJSON/toJSON implementation for ve.NodeEditor

- Only same types can connect to each other
  - `.output_type` implementation
- Alluvial width functions
- .preview_mode=true for special\_function
- Run/execution menu, alongside pausing execution
- Node editor settings implementation
- get v()/set v() serialisation