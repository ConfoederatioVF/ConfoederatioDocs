Remaining logic:
- 'script' type for ve.NodeEditorDatatype.openContextMenu() DONE
- Fix bug where deleting the node being connected to doesnt delete its relevant connections DONE
- Fix bug where default values are not used instead of undefined if parameter is set to a constant_value then disabled DONE
- Fix bug where previews are not live upon ve.NodeEditorDatatype.draw() call DONE
	- Add .id to ve.NodeEditor DONE
	- options.dag_sequence should be deprecated DONE
	- All unique .node_editor instances should be run DONE

- fromJSON/toJSON implementation for ve.NodeEditorDatatype
- fromJSON/toJSON implementation for ve.NodeEditor

- Only same types can connect to each other
  - `.output_type` implementation
- Alluvial width functions
- .preview_mode=true for special\_function
- Run/execution menu, alongside pausing execution
- Node editor settings implementation
- get v()/set v() serialisation