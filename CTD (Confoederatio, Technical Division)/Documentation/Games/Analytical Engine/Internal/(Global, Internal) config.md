
config.console: (Object)
config.editor_map_context_menu: (Object)  
- <interface_key>: (Object) - Note that interface_obj comes with the following keys: .civilisation_name, .civilisation_obj, .civilisation_tag, .current_page, .mouse_coords, .province_id, .province_obj.  
	- id*: (String) - Optional. The given ID for the context menu. <interface_key> by default.  
	- name*: (LocalisationString) - Optional. The name of the context menu. Undefined by default.  
	- order: (Number) - Optional. The order for the given context menu. 0 by default.
	  
	- constructor_function*: (Function\<Object\>) - Optional. Dynamically populates the context menu upon instantiation. (arg0_interface_obj).  
		- <element_key>: (Object)  
			- <element_property_key>: (Variable) - Same as createContextMenu() specifications.

			- global_key: (String) - The key corresponding to this element in global.
			- local_key: (String) - The key corresponding to this element in the local interface_obj.  
			- placeholder: (Function/Variable) - The return value of the function is the placeholder.
			- value_equation: (Function) - The return value of the function is what the .global_key and .local_key values are set to, given (arg0_value).  
			- x: (Function/Number) - If a function, it needs to return a Number.  
			- y: (Function/Number) - If a function, it needs to return a Number.
			  
			- effect: (Object)
				- open_ui: (Array\<String>/String)
			- special_function: (Function)
		- update_function: (Function) - The update function that runs every 100ms for the entire interface_obj. (arg0_interface_obj).
		- update_function_interval*: (Number) - Optional. 100 by default.

config.mapmodes: (Object)  
- <mapmode_key>: (Object)  
	- name*: (String) - The name of the current mapmode.  
	- description*: (String) - The description for the current mapmode.

	- overlays: (Array\<String>) - The list of other mapmodes to trigger, e.g. if there are multiple overlays to be added to the current layer.
	- separate_mapmode*: (Boolean) - Whether this represents a separate mapmode or merely an overlay upon the extant custom mapmode layer.
	- special_function: (Function)(arg0_province_obj) - The function to call when iterating over each province. Returns [r, g, b, a]/undefined.