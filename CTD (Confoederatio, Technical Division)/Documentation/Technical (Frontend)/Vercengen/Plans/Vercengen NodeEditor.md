Remaining logic:
- 'script' type for ve.NodeEditorDatatype.openContextMenu() DONE
- Fix bug where deleting the node being connected to doesnt delete its relevant connections DONE
- Fix bug where default values are not used instead of undefined if parameter is set to a constant_value then disabled DONE
- Fix bug where previews are not live upon ve.NodeEditorDatatype.draw() call DONE
	- Add .id to ve.NodeEditor DONE
	- options.dag_sequence should be deprecated DONE
	- All unique .node_editor instances should be run DONE

- fromJSON/toJSON implementation for ve.NodeEditorDatatype DONE
- fromJSON/toJSON implementation for ve.NodeEditor DONE

- Only same types can connect to each other DONE
  - `.output_type` implementation DONE
- Alluvial width functions DONE
- .preview_mode=true for special\_function DONE
- Run/execution menu, alongside pausing execution
- Node editor settings implementation
- get v()/set v() serialisation DONE