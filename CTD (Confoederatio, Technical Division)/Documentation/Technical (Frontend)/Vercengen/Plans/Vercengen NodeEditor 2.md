
**TODO:**
- Bind to file
- Ensure correct get v ()/set v() serialisation can losslessly roundtrip coordinates and nodes, as well as those of custom nodes
- Ensure that serialisation is JSON-compatible
- Finish NodeEditor polish options:
	- .settings: Object
		- .display_nodes_as_alluvial: boolean
		- .display_nodes_with_values: boolean  
		*  `.distributed_compute=false`: {@link boolean} - [WIP] - Whether to multithread/multicore tasks. This decision is currently under review.
		- .synchronous_script_manager: boolean - Enables a synchronous ScriptManager that remains open during editing, with an 'Assign File to Node' button when a 'script' parameter is selected. Otherwise, it appears as an 'Assign File as Node', since it creates a new script mode instead
	- In Settings menu:
		- Display Nodes as Alluvial
		- Display Nodes with Values
		- Show Inspector for Local Variables
		- Show ScriptManager (if .synchronous_script_manager is enabled)
- View file explorer

- **Logic:**
	- ==abort: true in return statement of the `.special_function` should lead to that branch halting execution, but other branches continuing onwards (used for conditional branching)==
	- Comment Nodes can be placed as text on the grid
	- Nodes should be able to be grouped effectively by creating custom nodes, which are added onto custom categories
		- Custom Nodes should have their own icon
		- Nodes in the Custom Node Editor should take on the shape of the custom ndoe parameter structure:
			- Parameter Nodes for handling input parameters
			- Return Node for handling the return value of a custom node