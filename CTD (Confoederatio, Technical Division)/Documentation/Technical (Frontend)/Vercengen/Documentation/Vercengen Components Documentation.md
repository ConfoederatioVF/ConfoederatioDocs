This page was last updated on **20 January 2026**. In the meantime, it may have become outdated. Please check in with Vercengen's documentation website for up-to-date information. Single-file documentation pages are mainly meant for AI models to ingest.

**ve.Component:**

```js
/**
 * <span color = "yellow">{@link ve.Component}</span>: Components represent inputs and displays that yield a value via `.v`. They are typically encapsulated by a <span color="yellow">{@link ve.Feature}</span>, but can be manually mounted via <span color=00ffff>{@link ve.Component.bind|bind}</span>(arg0_container_el:{@link HTMLElement}).
 * 
 * ##### Constructor:
 * - `arg0_options`: {@link Object}
 *   - All bindings accept 'this'/'global'/'window' variables. Bindings propagate recursively upwards (i.e. a userchange at a lower level will register as a userchange in an upper level).
 *   - `.binding`: {@link string} - Related event: `.onchange`. Bidirectional data binding for both `.from_binding`/`.to_binding`.
 *   - `.from_binding`: {@link string} - Related event: `.onprogramchange`. Unidirectional data binding.
 *   - `.to_binding`: {@link string} - Related event: `.onuserchange`. Unidirectional data binding.
 *   - 
 *   - `.onchange`: {@link function}(this.v, this:{@link ve.Component})
 *   - `.onprogramchange`: {@link function}(this.v, this:{@link ve.Component})
 *   - `.onuserchange`: {@link function}(this.v, this:{@link ve.Component})
 *   -
 *   - `.attributes`: {@link Object} - Any attributes to place on the mounted `this.element`.
 *     - `<attribute_key>`: {@link string}
 *   - `.limit=true`: {@link function}(this.v)|{@link undefined} | {@link boolean} - Whether to display the current Component. Immediate mode.
 *   - `.onload`: {@link function}(this:{@link ve.Component})
 *   - `.tooltip`: {@link Object}<{@link ve.Component}>|{@link string}
 *   - `.style`: {@link Object} - The CSS/Telestyle object to use for the current element. Immediate mode CSS if function is declared.
 *     - `<selector_key>`: {@link string} - CSS query selector. :nth-parent() is acceptable.
 *       - `<css_property>`: {@link function}|{@link string}
 *     - `<css_property>`: {@link function}|{@link string}
 *
 * ##### DOM:
 * - Attributes:
 *   - `data-debug-add-component`: {@link boolean}
 *   - `data-debug-limit`: {@link boolean}
 * - Fields:
 *   - `.instance`: this:{@link ve.Component}
 *
 * ##### Instance:
 * - `.child_class=this.constructor`: {@link ve.Component} - The constructor object of the child class.
 * - `.is_vercengen_component=true`: {@link boolean} - Whether to mark this ve.Component as a Vercengen component.
 * - `.parent_el`: {@link HTMLElement} - The parent element of the current component, should it exist.
 * -
 * - `.height=1`: {@link number}
 * - `.width=1`: {@link number}
 * - `.x=0`: {@link number} - Switches to an n+1 default if only `.y` is defined.
 * - `.y=n + 1`: {@link number} - Switches to 0 if only `.x` is defined.
 * -
 * - The linter/engine guarantees the following fields:
 * - `.element`: {@link HTMLElement} - The HTMLElement that the ve.Component is mounted to.
 * - `.name`: {@link string} - The name to display for the current ve.Component.
 * - `.owner`: {@link any} - The root owner of the current ve.Component. This is typically a {@link ve.Class}, but can also be a {@link ve.Feature} or {@link global}/{@link window}.
 * - `.owners`: {@link Array}<{@link any}> - A list of relevant owners in descending orders.
 * - `.v`: {@link any} - The value stored by the component. Getter/setter.
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.Component.addComponent|addComponent}</span>() - Attempts to mount the current component on its parent_el.
 * - <span color=00ffff>{@link ve.Component.bind|bind}</span>(arg0_container_el:{@link HTMLElement}) - Manually mounts the current component to arg0_container_el.
 * - <span color=00ffff>{@link ve.Component.fireFromBinding|fireFromBinding}</span>() - Pseudo-setter from binding. Fires only upon program-driven changes to `.v` directly.
 * - <span color=00ffff>{@link ve.Component.fireToBinding|fireToBinding}</span>() - Pseudo-setter to binding. Fires only upon user-driven changes to `.v`.
 * - <span color=00ffff>{@link ve.Component.remove|remove}</span>() - Removes the component/element from the DOM.
 * - <span color=00ffff>{@link ve.Component.removeComponent|removeComponent}</span>() - Unmounts the current component from its parent_el.
 * - <span color=00ffff>{@link ve.Component.setValueFromObject|setValueFromObject}</span>(arg0_object:{@link Object}, arg1_object:{@link Object}) - 
 * - <span color=00ffff>{@link ve.Component.setOwner|setOwner}</span>(arg0_value:{@link Object}, arg1_owner_array=[]:{@link Array}<{@link Object}>) - Used by the reflection engine in {@link ve.Class} to set the owner hierarchy automatically.
 * 
 * ##### Static Methods:
 * - <span color=00ffff>{@link ve.Component.linter|linter}</span>() - Run at startup if {@link ve.registry.debug_mode} is true. Lints all Vercengen components.
 * 
 * ##### Types:
 * Types are annotated by both their constructor function and what they return after the pipe separator (`.v`). 
 * 
 * \* indicates a recursive Object of that type.
 * - {@link ve.Component.ve.DatavisSuite|veDatavisSuite}(arg0_value:{@link Object}, arg1_options:{@link Object}) | {@link Object}
 * - {@link ve.Component.ve.FileExplorer|veFileExplorer}(arg0_value:{@link string}, arg1_options:{@link Object}) | {@link string} - The file path the File Explorer is currently navigating.
 * - {@link ve.Component.ve.Hierarchy|veHierarchy}(arg0_value:{@link Object}<{@link ve.Component}>, arg1_options:{@link Object}) | {@link Object}<{@link ve.Component}> - Note. It is recommended to use {@link ve.HierarchyDatatype} as the specific {@link ve.Component} for `arg0_value`. Tree/scene inspector.
 *   - {@link ve.Component.ve.HierarchyDatatype|veHierarchyDatatype}({@link Object}<{@link ve.Component}>, arg1_options:{@link Object}) | {@link Object}<{@link ve.Component}> - Represents individual items in a hierarchy.
 * - {@link ve.Component.ve.NodeEditor|veNodeEditor}(arg0_value:{@link Object}, arg1_options:{@link Object}) | {@link Object} - Visual node-based DAG editor with async processing.
 *   - {@link ve.Component.ve.NodeEditorDatatype|veNodeEditorDatatype}(arg0_value:{@link Object}, arg1_options:{@link Object}) | {@link Object}
 * - {@link ve.Component.ve.ScriptManager|veScriptManager}(arg0_value:{@link string}, arg1_options:{@link Object}) | {@link string}
 *   - {@link ve.Component.ve.ScriptManagerBlockly|veScriptManagerBlockly}(arg0_value:{@link string}, arg1_options:{@link Object}) | {@link string}
 *   - {@link ve.Component.ve.ScriptManagerCodemirror|veScriptManagerCodemirror}(arg0_value:{@link string}, arg1_options:{@link Object}) | {@link string}
 * - {@link ve.Component.ve.Spreadsheet|veSpreadsheet}(arg0_value:{@link Array}<{@link Array}<{@link Array}<{@link any}>>>|{@link Object}, arg1_options:{@link Object}) | {@link Array}<{@link Array}<{@link Array}<{@link any}>>>|{@link Object} - Spreadsheet editor with formulas. Can be converted to {@link ve.Table} on demand.
 * - {@link ve.Component.ve.WordProcessor|WordProcessor}(arg0_value:{@link string}, arg1_options:{@link Object}) | {@link string} - Word processor.
 * 
 * - {@link ve.Component.ve.Button|veButton}(arg0_value:{@link function}, arg1_options:{@link Object}) | {@link function}
 * - {@link ve.Component.ve.Checkbox|veCheckbox}(arg0_value:{@link boolean}|{@link Object}<{@link boolean}>\*, arg1_options: {@link Object}) | {@link boolean}|{@link Object}<{@link boolean}>\* - A recursive list of checkboxes, or a single toggleable input.
 * - {@link ve.Component.ve.Colour|veColour}(arg0_value:{@link Array}<{@link number}, {@link number}, {@link number}|{@link string}, arg1_options: {@link Object}>) | {@link Array}<{@link number}, {@link number}, {@link number}> - RGB colour selector.
 * - {@link ve.Component.ve.Datalist|veDatalist}(arg0_value:{@link Object}<{@link string}>, arg1_options: {@link Object})
 * - {@link ve.Component.ve.Date|veDate}(arg0_value:{@link UF.Date}, arg1_options: {@link Object}) | {@link UF.Date}
 * - {@link ve.Component.ve.DateLength|veDateLength}(arg0_value:{@link UF.Date}, arg1_options: {@link Object}) | {@link UF.Date}
 * - {@link ve.Component.ve.File|veFile}(arg0_value:{@link string}, arg1_options:{@link Object}) | {@link string} - The file/folder path selected by the user.
 * - {@link ve.Component.ve.FlexInterface|veFlexInterface}(arg0_value:{@link Object}<{@link Object}|{@link ve.Component}>, arg1_options:{@link Object}) | {@link Object}<{@link Object}|{@link ve.Component}>
 * - {@link ve.Component.ve.Graph|veGraph}(arg0_value:{@link Object}, arg1_options:{@link Object}) | {@link Object}
 * - {@link ve.Component.ve.HTML|veHTML}(arg0_value:{@link function}|{@link HTMLElement}|{@link string}, arg1_options: {@link Object}) | {@link string}
 * - {@link ve.Component.ve.Interface|veInterface}(arg0_value:{@link Object}<{@link ve.Component}>, arg1_options:{@link Object}) | {@link Object}<{@link ve.Component}>
 * - {@link ve.Component.ve.List|veList}(arg0_value:{@link Array}<{@link ve.Component}>, arg1_options:{@link Object}) | {@link Array}<{@link ve.Component}>
 * - {@link ve.Component.ve.Map|veMap}(arg0_value:{@link maptalks.Map}, arg1_options:{@link Object}) | {@link maptalks.Map}
 * - {@link ve.Component.ve.MultiTag|veMultiTag}(arg0_value:{@link Array}<{@link string}>, arg1_options:{@link Object}) | {@link Array}<{@link string}>
 * - {@link ve.Component.ve.Number|veNumber}(arg0_value:{@link number}, arg1_options:{@link Object}) | {@link number}
 * - {@link ve.Component.ve.ObjectInspector|veObjectInspector}(arg0_value:{@link any}, arg1_options:{@link Object}) | {@link any}
 * - {@link ve.Component.ve.PageMenu|vePageMenu}(arg0_value:{@link Object}, arg1_options:{@link Object}) | {@link string} - The `.page` key currently displayed.
 * - {@link ve.Component.ve.Password|vePassword}(arg0_value:{@link string}, arg1_options:{@link Object}) | {@link string}
 * - {@link ve.Component.ve.Radio|veRadio}(arg0_value:{@link Object}<{@link boolean}>\* | {@link Object}<{@link boolean}>\*
 * - {@link ve.Component.ve.Range|veRange}(arg0_value:{@link number}, arg1_options: {@link Object}) | {@link number}
 * - {@link ve.Component.ve.RawInterface|veRawInterface}(arg0_components_obj:{@link Object}<{@link ve.Component}>, arg1_options:{@link Object}) | {@link Object}<{@link ve.Component}>
 * - {@link ve.Component.ve.RichText|veRichText}(arg0_value:{@link string}, arg1_options:{@link Object}) | {@link string} - Single-line rich text input. `.v` is an HTML string.
 * - {@link ve.Component.ve.SearchSelect|veSearchSelect}(arg0_components_obj:{@link Object}<{@link ve.Component}>, arg1_options:{@link Object}) | {@link Object}<{@link ve.Component}>
 * - {@link ve.Component.ve.Select|veSelect}(arg0_value:{@link ve.Object}<{@link string}>, arg1_options:{@link Object}) | {@link string} - The key of the selected option.
 * - {@link ve.Component.ve.Table|veTable}(arg0_value:{@link Array}<{@link Array}<{@link any}>>, arg1_options:{@link Object}) | {@link Array}<{@link Array}<{@link any}>> - Paginated lazy-loaded table. Can be converted to {@link ve.Spreadsheet} on demand.
 * - {@link ve.Component.ve.Telephone|veTelephone}(arg0_value:{@link string}, arg1_options:{@link Object}) | {@link string}
 * - {@link ve.Component.ve.Text|veText}(arg0_value:{@link string}, arg1_options: {@link Object}) | {@link string}
 * - {@link ve.Component.ve.Time|veTime}(arg0_value:{hour:{@link number}, minute:{@link number}}, arg1_options:{@link Object}) | {hour:{@link number}, minute:{@link number}}
 * - {@link ve.Component.ve.Toggle|veToggle}(arg0_value:{@link boolean}, arg1_options:{@link Object}) | {@link boolean}
 * - {@link ve.Component.ve.UndoRedo|veUndoRedo}(arg0_value:{@link string}, arg1_options:{@link Object}) | {@link string} - The {@link DALS.Timeline} ID that the UndoRedo component is currently navigating.
 * - {@link ve.Component.ve.URL|veURL}(arg0_value:{@link string}, arg1_options:{@link Object}) | {@link string}
 * 
 * @class
 * @memberof ve
 * @namespace ve.Component
 * @type {ve.Component}
 */
```

The following types represent complex components, which are given their own folders.

**ve.DatavisSuite:**
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link Object}
 *   - `.data_scripts`: {@link Object}
 *     - `<script_key>`: {@link string}
 *       - `.name`: {@link string}
 *       - 
 *       - `.description`: {@link string}
 *       - `.tags`: {@link Array}<{@link string}>
 *       - `.value`; {@link Object} - The JSON object that stores the current script from which to serialise/deserialise.
 *   - `.graphs`: {@link Object}
 *     - `<graph_key>`: {@link ve.Graph}
 *   - `.series`: {@link Object}
 *     - `<series_key>`: {@link Object}
 *       - `.coords`: {@link Array}<{@link Array}<{@link string}, {@link number}, {@link number}>, {@link Array}<{@link string}, {@link number}, {@link number}>> - The coords/range of the series using the Spreadsheet Name for the [0] element.
 *       - `.name`: {@link string} - The name of the series, data column header value by default.
 *       - `.pivot="column"`: {@link string} - Either 'column'/'row'.
 *       - `.symbol`: {@link Object} - Echarts bindings per series.
 *   - `.table_value`: {@link Object} - The ve.Spreadsheet value that can be used to restore both formulas and values.
 * - `arg1_options`: {@link Object}
 *   - `.dark_mode=true`: {@link boolean}
 *
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.DatavisSuite}
 */
```

**ve.FileExplorer:**
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * File explorer used either for navigation (i.e. saving/loading) or as a generic file explorer primitive.
 * - Functional binding: <span color=00ffff>veFileExplorer</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link string} - The file path in which the FileExplorer should be initialised.
 * - `arg1_options`: {@link Object}
 *   - `.actions_components_obj`: {@link Object}<{@link ve.Component}> - Appended components in the topbar action meny, usually at the end.
 *   - `.file_components_obj={select: ...}`: {@link Object}<{@link ve.Component}>
 *   - `.file_icon="<icon>description</icon>"`: {@link string}
 *   - `.file_options`: {@link Object}
 *   - `.folder_components_obj={select: ...}`: {@link Object}<{@link ve.Component}>
 *   - `.folder_icon="<icon>folder</icon>"`: {@link string}
 *   - `.folder_options`: {@link Object}
 *   - `.name`: {@link string}
 *   - `.navigation_only=false`: {@link boolean}
 *   - `.onrefresh`: {@link function}(v:{@link ve.FileExplorer.v}, arg1_e:{@link ve.FileExplorer})
 *   - 
 *   - `.load_function`: {@link function}(arg0_data:{@link string}, arg1_file_path:{@link string}) - Automatically loads the text content of a valid extension into this function.
 *   - `.save_extension`: {@link Array}<{@link string}>|{@link string} - The save dot extension that files can be loaded from. `.*` refers to all file extensions.
 *   - `.save_function`: {@link function}(arg0_save_file_name:{@link string}) - Returns the value of the current savedata state.
 *   
 * ##### Instance:
 * - `.clipboard`: {@link Array}<{@link string}> - The list of full file paths currently stored in the clipboard.
 * - `.selected`: {@link Array}<{@link string}> - The list of selected file paths.
 * - `.v`: {@link string} - Accessor. The current file path.
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.FileExplorer.clearClipboard|clearClipboard}</span>()
 * - <span color=00ffff>{@link ve.FileExplorer.deselect|deselect}</span>(arg0_file_path:{@link string}, arg1_options:{do_not_modify_classes: {@link boolean}}) | {@link Array}<{@link string}>
 * - <span color=00ffff>{@link ve.FileExplorer.deselectAll|deselectAll}</span>()
 * - <span color=00ffff>{@link ve.FileExplorer.fireSelectToggle|fireSelectToggle}(v:{@link boolean}, e:{@link ve.Toggle}) - Internal handler for toggling file/folder selection.
 * - <span color=00ffff>{@link ve.FileExplorer.select|select}</span>(arg0_file_path:{@link string}) | {@link Array}<{@link string}>
 * - <span color=00ffff>{@link ve.FileExplorer.selectAll|selectAll}</span>()
 * - <span color=00ffff>{@link ve.FileExplorer.setClipboard|setClipboard}</span>() - Sets the clipboard to currently selected file paths.
 * - <span color=00ffff>{@link ve.FileExplorer.refresh|refresh}</span>() - Refreshes the current ve.FileExplorer display. Handled automatically.
 * - 
 * - <span color=00ffff>{@link ve.FileExplorer.getFiles|getFiles}</span>(arg0_file_paths:{@link Array}<{@link string}>) | {@link Array}<{@link string}> - Returns all the subpaths in the set of file/folder paths given.
 * - <span color=00ffff>{@link ve.FileExplorer.copy|copy}</span>(arg0_file_paths:{@link Array}<{@link string}>, arg1_file_path:{@link string}, arg2_function:{@link function}) - Opens a copy files modal with a callback function.
 * - <span color=00ffff>{@link ve.FileExplorer.delete|delete}</span>(arg0_file_paths:{@link Array}<{@link string}>, arg1_file_path:{@link string}, arg2_function:{@link function}) - Opens a delete files modal with a callback function.
 * - <span color=00ffff>{@link ve.FileExplorer.move|move}</span>(arg0_file_paths:{@link Array}<{@link string}>, arg1_file_path:{@link string}, arg2_function:{@link function}) - Opens a move files modal with a callback function.
 * - <span color=00ffff>{@link ve.FileExplorer.rename|rename}</span>(arg0_file_path:{@link string}, arg1_function:{@link function}) - Opens a rename file modal with a callback function.
 *
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.FileExplorer}
 */
```

**ve.Graph**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link Object}
 *   - `.series`: {@link Object}
 *     - `.name`: {@link string}
 *     - `.origin`: {@link Array}<{@link number}, {@link number}, {@link number}> - The sheet index, X, Y origin of the top-left corner of `.value`, the first top-left populated cell.
 *     - `.pivot="column"`: {@link string} - Either 'column'/'row'.
 *     - `.symbol`: {@link Object} - The symbol the data line takes on.
 *     - `.labels`: {@link Array}<{@link string}> - The labels for each datapoint.
 *     - `.value`: {@link Array}<{@link Array}<{@link number}>> - 2D dataframe storing values within this series.
 * - `arg1_options`: {@link Object}
 *   - `.symbol`: {@link Object}
 *     - `.title`: {@link Object}
 *       - `.text`: {@link string}
 *   - `.type="line_chart"`: {@link string} - The type of chart to show in the graph.
 *   - 
 *   - `.height`: {@link number}
 *   - `.width`: {@link number}
 *   - `.x`: {@link number}
 *   - `.y`: {@link number}
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Graph}
 */
```

**ve.Hierarchy:**
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Hierarchy used for organising both nested and un-nested lists via item/group distinctions.
 * - Functional binding: <span color=00ffff>veHierarchy</span>().
 * 
 * ##### Constructor:
 * - `arg0_components_obj`: {@link Object}<{@link ve.Component}|{@link ve.HierarchyDatatype}> - The individual items to append to the current hierarchy.
 * - `arg1_options`: {@link Object}
 *   - `.allow_disabled_reordering=false`: {@link boolean}
 *   - `.disable_searchbar=false`: {@link boolean}
 *   - `.namespace=Class.generateRandomID(ve.Hierarchy)`: {@link string}
 *   - `.searchbar_style`: {@link Object} - The Telestyle object to apply to the searchbar.
 * 
 * ##### Instance:
 * - `.components_obj`: {@link Object}<{@link ve.Component}|{@link ve.HierarchyDatatype}>
 * - `.nestable`: {@link Nestable}
 * - `.v`: {@link this.components_obj} - Accessor. The current components_obj mounted to the ve.Hierarchy.
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.Hierarchy.addItem|addItem}</span>(arg0_parent_el:{@link HTMLElement}, arg1_hierarchy_datatype:{@link ve.HierarchyDatatype})
 * - <span color=00ffff>{@link ve.Hierarchy.getHierarchyArray|getHierarchyArray}</span>(arg0_options:{flatten_object: {@link boolean} }) | {@link Object[]}
 * - <span color=00ffff>{@link ve.Hierarchy.getHierarchyObject|getHierarchyObject}</span>(arg0_options:{flatten_object: {@link boolean} }) | {@link Object}
 * - <span color=00ffff>{@link ve.Hierarchy.removeItem|removeItem}</span>(arg0_hierarchy_datatype:{@link ve.HierarchyDatatype})
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Hierarchy}
 */
```

**ve.HierarchyDatatype:**
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Hierarchy datatype used as a nested draggable item/group for {@link ve.Hierarchy}. Item by default.
 * - Functional binding: <span color=00ffff>veHierarchyDatatype</span>().
 * 
 * [WIP] - This section, especially with `.oncollapse` and `.instance.is_collapsed`:{@link boolean} reflection is scheduled to be reworked in future updates.
 *  
 * ##### Constructor:
 * - `arg0_value`: {@link Object}<{@link ve.Component}>
 * - `arg1_options`: {@link Object}
 *   - `.disabled=false`: {@link boolean} - Whether the item is draggable within the hierarchy.
 *   - `.id`: {@link string}
 *   - `.name_options`: {@link Object} - Any options that should be carried over to `.components_obj.name`. Same options as {@link ve.Text}.
 *   - `.no_folders=false`: {@link boolean} - Whether minimising/maximising individual folders should be allowed.
 *   - `.type="item"`: {@link string} - Either 'group'/'item'.
 * 
 * ##### Instance:
 * - `.components_obj`: {@link Object}<{@link ve.Component}>
 * - `.instance`: {@link any} - The bound object which this HierarchyDatatype is visualising.
 * - `.is_vercengen_hierarchy_datatype=true`: {@link boolean}
 * - `.name`; {@link string} - Accessor. Differs from {@link ve.Component.name} in that it is a {@link ve.Text}.v value instead of a span element.
 * - `.oncollapse`: {@link function}(v:{@link boolean}, e:{@link ve.HierarchyDatatype}) - Fires upon a user toggling the collapse button.
 * - `.type="item"`: {@link string} - Determined by `.options.type`.
 * - `.v`: {@link Object}<{@link ve.Component}> - Accessor. Same as `.components_obj`.
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.HierarchyDatatype.refresh|refresh}</span>() - Refreshes the display of the current datatype.
 * 
 * ##### Static Fields:
 * - `.instances`: {@link Array}<this:{@link ve.HierarchyDatatype}>
 *
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.HierarchyDatatype}
 */
```

**ve.NodeEditor:**
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Creates a drag-and-drop Node Editor using Maptalks as a backend. Nodes are executed from a root node using a parallelised version of Kahn's algorithm, and nodes must form a directed acyclic graph (DAG). Circular references will not be executed if forced.
 * 
 * If you need a loop, call `async run()` multiple times instead.
 * - Functional binding: <span color=00ffff>veNodeEditor</span>().
 * 
 * [WIP] - Settings remain to be concretely implemented.
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link Object} - The JSON object for the Maptalks instance attached to the current NodeEditor, including properties data.
 * - `arg1_options`: {@link Object}
 *   - `.bg_ctx`: {@link function} | {@link Object} - Returns the context of a Canvas.
 *   - `.category_types`: {@link Object}
 *     - `<category_key>`: {@link Object}
 *       - `.colour`: {@link Array}<{@link number}, {@link number}, {@link number}>|{@link string} - Either a hex/RGB value.
 *   - `.exclude_all=false`: {@link boolean} - Whether to exclude the default 'All' category at the start.
 *   - `.node_types`: {@link Object}
 *     - `<node_key>`: {@link Object} - Current valid types for `.input_parameters` and `.output_type` include 'any'/'number[]'/'string[]'/'boolean'/'number'/'script'/'string'.
 *       - `.category="Expression"` - The category that any {@link ve.NodeEditorDatatype} instances should belong to. Typically should either be 'Filter'/'Expression'.
 *       - `.input_parameters=[]`: {@link Array}<{@link Object}> - The types of input parameters that will be accepted for evaluation.
 *         - `[n]`: {@link Object}
 *           - `.name`: {@link string}
 *           - `.type`: {@link string}
 *       - `.output_type="any"`: {@link string}
 *     - `.name`: {@link string}
 *     - `.output_type="any"`: {@link string} - What the output (return) type is regarded as being. There can only be a single return type per Node, similar to functions in most programming languages.
 *     - `.special_function`: {@link function}(argn_arguments:{@link any}) ¦ {@link Object}
 *       - Returns:
 *       - `.alluvial_width=1`: {@link number}
 *       - `.display_value`: {@link string} - The actual display_value to show.
 *       - `.run`: {@link function} - The actual expression to execute upon running it in non-preview mode.
 *       - `.value`: {@link any} - If a filter, it should return an {@link Array}<{@link any}>.
 *     - 
 *     - `.options`: {@link Object}
 *       - `.alluvial_scaling=1`: {@link number} - How much to scale alluvial widths by when displayed compared to their actual number.
 *   	   - `.id=Class.generateRandomID(ve.NodeEditorDatatype)`: {@link string} - The ID to assign to the present datatype at a class level.
 *       - `.show_alluvial=false`: {@link boolean}
 *   - `.project_folder`: {@link string}
 * 
 * ##### Instance:
 * - `.id`: {@link string}
 * - `.main`: {@link Object}
 *   - `.variables`: {@link Object} - Where values during the run-cycle are stored.
 * - `.map`: {@link maptalks.Map} - Not an actual map instance. Used for rendering the node environment in 3D space.
 * - `.node_layer`: {@link maptalks.VectorLayer}
 * - `.v`: {@link Object}
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.NodeEditor._connect|_connect}</span>(arg0_node:{@link ve.NodeEditorDatatype}, arg1_node:{@link ve.NodeEditorDatatype}, arg2_index:{@link number}, arg3_options:{@link Object})
 * - <span color=00ffff>{@link ve.NodeEditor._disconnect|_disconnect}</span>(arg0_node:{@link ve.NodeEditorDatatype}, arg1_node:{@link ve.NodeEditorDatatype}, arg2_index:{@link number})
 * - <span color=00ffff>{@link ve.NodeEditor._select|_select}</span>(arg0_node:{@link ve.NodeEditorDatatype}, arg1_index:{@link number})
 * 
 * - <span color=00ffff>{@link ve.NodeEditor.clear|clear}</span>()
 * - <span color=00ffff>{@link ve.NodeEditor.drawToolbox|drawToolbox}</span>()
 * - <span color=00ffff>{@link ve.NodeEditor.getCanvas|getCanvas}</span>() | {@link HTMLCanvasElement}
 * - <span color=00ffff>{@link ve.NodeEditor.getDAGSequence|getDAGSequence}</span>() | {@link Array}<{@link Array}<{@link ve.NodeEditorDatatype}>>
 * - <span color=00ffff>{@link ve.NodeEditor.getDefaultBaseLayer|getDefaultBaseLayer}</span>() | {@link Object}
 * - <span color=00ffff>{@link ve.NodeEditor.loadSettings|loadSettings}</span>(arg0_settings:{@link Object})
 * - async <span color=00ffff>{@link ve.NodeEditor.run|run}</span>(arg0_preview_mode:{@link boolean}) | {@link Object}
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.NodeEditor}
 */
```

**ve.NodeEditorDatatype:**
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Represents a single node instance within a {@link ve.NodeEditor} that can have acyclic connections to other nodes within the same editor for DAG execution.
 * - Functional binding: <span color=00ffff>veNodeEditorDatatype</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link Object}
 *   - `.category="Expression"` - The category that any {@link ve.NodeEditorDatatype} instances should belong to. Typically should either be 'Filter'/'Expression'.
 *   - `.coords`: {@link maptalks.Coordinate}|{x: {@link number}, y: {@link number}}
 *   - `.input_parameters=[]`: {@link Array}<{@link Object}> - The types of input parameters that will be accepted for evaluation.
 *     - `[n]`: {@link Object}
 *       - `.name`: {@link string}
 *       - `.type`: {@link string}
 *   - `.key`: {@link string}
 *   - `.name`: {@link string}
 *   - `.output_type="any"`: {@link string} - What the output (return) type is regarded as being. There can only be a single return type per Node, similar to functions in most programming languages.
 *   - `.special_function`: {@link function}(argn_arguments:{@link any}) ¦ {@link any} - If a filter, it should return an {@link Array}<{@link any}>.
 * - `arg1_options`: {@link Object}
 *   - `.alluvial_scaling=1`: {@link number} - How much to scale alluvial widths by when displayed compared to their actual number.
 *   - `.id=Class.generateRandomID(ve.NodeEditorDatatype)`: {@link string} - The ID to assign to the present datatype at a class level.
 *   - `.node_editor`: {@link ve.NodeEditor} - The node editor that this ve.NodeEditorDatatype is attached to.
 *   - `.show_alluvial=false`: {@link boolean}
 *   
 * ##### Instance:
 * - `.connections`: {@link Array}<{@link Array}<{@link ve.NodeEditorDatatype}, {@link number}>>
 * - `.constant_values`: {@link Array}
 * - `.dynamic_values`: {@link Array}
 * - `.geometries`: {@link Array}
 * - `.id`: {@link string}
 * - `.ui`: {@link Object}
 *   - `.information`: {@link Object}
 * - `.v`: {@link Object}
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.Component.NodeEditorDatatype.draw|draw}</span>()
 * - <span color=00ffff>{@link ve.Component.NodeEditorDatatype.getConnection|getConnection}</span>(arg0_node:{@link ve.NodeEditorDatatype}, arg1_index:{@link number}) | {@link number}
 * - <span color=00ffff>{@link ve.Component.NodeEditorDatatype.handleEvents|handleEvents}</span>()
 * - <span color=00ffff>{@link ve.Component.NodeEditorDatatype.hasConnection|hasConnection}</span>(arg0_index:{@link number}) | {@link boolean}
 * - <span color=00ffff>{@link ve.Component.NodeEditorDatatype.isSelected|isSelected}</span>(arg0_index:{@link number})
 * - <span color=00ffff>{@link ve.Component.NodeEditorDatatype.openContextMenu|openContextMenu}</span>()
 * - <span color=00ffff>{@link ve.Component.NodeEditorDatatype.remove|remove}</span>()
 * 
 * ##### Static Methods:
 * - <span color=00ffff>{@link ve.NodeEditorDatatype.draw|draw}</span>(arg0_options:{@link Object})
 * - <span color=00ffff>{@link ve.NodeEditorDatatype.getNode|getNode}</span>(arg0_node_id:{@link string}) | {@link ve.NodeEditorDatatype}
 *
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.NodeEditorDatatype}
 */
```

**ve.ScriptManager**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 *
 * Visual block-based and code-based IDE used to assemble `.js` script files. ES6 compatible; non-compatible files will degrade to code editor only.
 *
 * **Note:** Declaring duplicate ve.ScriptManager components will reset the main Blockly workspace for each new instance.
 * - Functional binding: <span color=00ffff>veScriptManager</span>().
 * - This component has special default settings located in {@link ve.registry.settings.ScriptManager}.
 *
 * ##### Constructor:
 * - `arg0_value`: {@link string} - The code to load into the present ve.ScriptManager.
 * - `arg1_options`: {@link Object}
 *   - `.do_not_auto_detect_project=false`: {@link boolean} - Whether to attempt to read from the base `.ve-sm` file upon initialisation.
 *   - `.do_not_cache_file_explorer=false`: {@link boolean} - Whether the file directory should remain the same as when last opened.
 *   - `.do_not_display_file_name=false`: {@link boolean}
 *   - `.do_not_display_project_name=false`: {@link boolean}
 *   - `.folder_path=process.cwd()`: {@link string}
 *   - `.save_extension=[".*"]`: {@link Array}<{@link string}>
 * 	 - `.settings`: {@link Object}
 * 	   - `.autosave_projects=true`: {@link boolean}
 * 	   - `.display_load_errors=false`: {@link boolean}
 * 	   - `.monaco_theme="nord"`: {@link string}
 * 	   - `.index_documentation=true`: {@link boolean}
 * 	   - `.log_large_objects_in_console=false`: {@link boolean}
 * 	   - `.manual_synchronisation`: {@link true}
 * 	   - `.scene_height=0`: {@link number} - The scene height of the main workspace in px.
 * 	   - `.theme="theme-default"`: {@link string} - Either 'theme-default'/'theme-light'
 * 	   - `.view_file_explorer=true`: {@link boolean}
 *
 * ##### Instance:
 * - `.console_el`: {@link HTMLElement}
 *   - `.print`: {@link function}(arg0_message:{@link string}, arg1_type:{@link string}) - arg1_type is either 'message'/'error'.
 * - `._file_path`: {@link string} - The file path currently opened.
 * - `.leftbar_file_explorer`: {@link ve.FileExplorer}
 * - `.scene_blockly`: {@link ve.ScriptManagerBlockly}
 * - `.scene_monaco`: {@link ve.ScriptManagerMonaco}
 * - `.scene_interface`: {@link ve.FlexInterface}
 * - `.v`: {@link string}
 *
 * Private Fields:
 * - `._monaco_themes`: {@link Object}<{@link string}>
 * - `._settings`: {@link Object}
 *
 * ##### Methods:
 * - <span color=00ffff>{@link ve.ScriptManager.loadSettings|loadSettings}</span>(arg0_settings:{@link Object})
 * - <span color=00ffff>{@link ve.ScriptManager.saveSettings|saveSettings}</span>() | {@link string}
 * - <span color=00ffff>{@link ve.ScriptManager.setCodeEditorTheme|setCodeEditorTheme}</span>(arg0_theme_class:{@link string})
 * - <span color=00ffff>{@link ve.ScriptManager.setTheme|setTheme}</span>(arg0_theme_class:{@link string})
 * - <span color=00ffff>{@link ve.ScriptManager.throwLoadError|throwLoadError}</span>(arg0_error:{@link Error}|{@link string})
 *
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.ScriptManager}
 */
```

**ve.ScriptManagerBlockly:**
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 *
 * Represents a {@link Blockly} sub-component used as a visual editor for {@link ve.ComponentScriptManager}.
 *
 * **Note.** Declaring duplicate {@link ve.ScriptManager} components will reset the main Blockly workspace for each new instance.
 * - Functional binding: <span color=00ffff>veScriptManagerBlockly</span>().
 *
 * ##### Constructor:
 * - `arg0_value`: {@link string} - The code to input into the present Blockly viewer.
 * - `arg1_options`: {@link Object}
 *   - `.script_manager`: {@link ve.ScriptManager}
 *
 * ##### Instance:
 * - `.workspace`: {@link Blockly.Workspace}
 * - `.v`: {@link string}
 *
 * ##### Methods:
 * - <span color=00ffff>{@link ve.ScriptManagerBlockly.disable|disable}</span>()
 * - <span color=00ffff>{@link ve.ScriptManagerBlockly.enable|enable}</span>()
 * - <span color=00ffff>{@link ve.ScriptManagerBlockly.fixBlocklyScaling|fixBlocklyScaling}</span>()
 * - <span color=00ffff>{@link ve.ScriptManagerBlockly.handleCSS|handleCSS}</span>()
 * - <span color=00ffff>{@link ve.ScriptManagerBlockly.hide|hide}</span>()
 * - <span color=00ffff>{@link ve.ScriptManagerBlockly.interceptBlocklyTransforms|interceptBlocklyTransforms}</span>()
 * - <span color=00ffff>{@link ve.ScriptManagerBlockly.setTheme|setTheme}</span>(arg0_theme:{@link string}) - Either 'theme_default'/'theme_light'.
 * - <span color=00ffff>{@link ve.ScriptManagerBlockly.show|show}</span>()
 *
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.ScriptManagerBlockly}
 */
```

**ve.ScriptManagerMonaco**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 *
 * Manages the Monaco Editor instance for {@link ve.ScriptManager}, the main IDE component for Vercengen.
 * - Functional binding: <span color=00ffff>veScriptManagerMonaco</span>().
 *
 * ##### Constructor:
 * - `arg0_value`: {@link string} - The code to load into the present component.
 * - `arg1_options`: {@link Object}
 *   - `.monaco_options`: {@link Object} - Any monaco options to use upon instantiation.
 *   - `.script_manager`: {@link ve.ScriptManager}
 *   - `.theme`: {@link string} - The initial theme to load.
 *
 * ##### Instance:
 * - `.editor`: {@link Object} - The raw Monaco editor instance.
 * - `.v`: {@link string}
 *
 * ##### Methods:
 * - <span color=00ffff>{@link ve.ScriptManagerMonaco.setOptions|setOptions}</span>(arg0_options:{@link Object})
 * - <span color=00ffff>{@link ve.ScriptManagerMonaco.setTheme|setTheme}</span>(arg0_theme_name:{@link string})
 *
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.ScriptManagerMonaco}
 */
```

**ve.Spreadsheet**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Spreadsheet editor that returns a 2D array list/object using iframes for encapsulation. Excel/Google Sheets/HTML compatible with formulas and limited styling options. Note that there might be a slight initialisation delay due to lazy-loading.
 * 
 * The reason this does not always serialise to an {@link Array} is so that formulas and format data can be preserved.
 * - Functional binding: <span color=00ffff>veSpreadsheet</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link Array}<{@link Array}<{@link Array}<{@link any}>>>|{@link Object}
 *   - Nested arrays: [n1] - Container, [n2] - Sheet, [n3] - Row
 * - `arg1_options`: {@link Object}
 *   - `.dark_mode=false`: {@link boolean} - Whether the spreadsheet editor should launch in dark mode.
 * 
 * ##### Instance:
 * - `.v`: {@link Object}
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.Spreadsheet.convertToArray|convertToArray}</span>() | {@link Array}<{@link Array}<{@link Array}<{@link any}>>>
 * - <span color=00ffff>{@link ve.Spreadsheet.convertToSpreadsheet|convertToSpreadsheet}</span>() | {@link ve.Spreadsheet}
 * - <span color=00ffff>{@link ve.Spreadsheet.convertToTable|convertToTable}</span>() | {@link ve.Table}
 * - <span color=00ffff>{@link ve.Spreadsheet.fromArray|fromArray}</span>(arg0_array:{@link Array}<{@link Array}<{@link Array}<{@link any}>>>, arg1_do_not_display=false:{@link boolean}) | {@link Object}
 * - <span color=00ffff>{@link ve.Spreadsheet.getCellData|getCellData}</span>(arg0_sheet_index:{@link number}|{@link string}, arg1_x:{@link number}, arg2_y:{@link number}) | {f:{@link string}, v:{@link number}}
 * - <span color=00ffff>{@link ve.Spreadsheet.getSelectedRange|getSelectedRange}</span>() | [[{@link number}, {@link number}, {@link number}], [{@link number}, {@link number}, {@link number}]]
 * - <span color=00ffff>{@link ve.Spreadsheet.getSheetNames|getSheetNames}</span>() | {@link Array}<{@link string}>
 * - <span color=00ffff>{@link ve.Spreadsheet.setCellData|setCellData}</span>(arg0_sheet_index:{@link number}|{@link string}, arg1_x:{@link number}, arg2_y:{@link number}, arg3_value:{f:{@link string}, v:{@link number}})
 * - <span color=00ffff>{@link ve.Spreadsheet.setDarkMode|setDarkMode}</span>(arg0_value=false:{@link boolean})
 * - <span color=00ffff>{@link ve.Spreadsheet.setSelectedRange|setSelectedRange}</span>(arg0_sheet_index:{@link number}|{@link string}, arg1_start_coords:[{@link number}, {@link number}, {@link number}], arg2_end_coords:[{@link number}, {@link number}, {@link number}])
 * 
 * ##### Static Fields:
 * - `.instances`: {@link Array}<this:{@link ve.Spreadsheet}>
 *
 * ##### Static Methods:
 * - <span color=00ffff>{@link ve.Spreadsheet.fireToBinding|fireToBinding}</span>(arg0_table_id:{@link string})
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Spreadsheet}
 */
```

**ve.WordProcessor:**
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Multiline rich text editor used as a word processor.
 * - Functional binding: <span color=00ffff>veWordProcessor</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link string} - The HTML contents of the current text editor.
 * - `arg1_options`: {@link Object}
 * 
 * ##### Instance:
 * - `.v`: {@link string} - The current HTML contents, same as `arg0_value`.
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.WordProcessor.handleEvents|handleEvents}</span>() - Initialises event handlers for the present component.
 * - <span color=00ffff>{@link ve.WordProcessor.getWYSIWYGFromFields|getWYSIWYGFromFields}</span>(arg0_wysiwyg_el:{@link HTMLElement}) | {@link string} - Fetches the internal .innerHTML value, resolving conflicts between visual/code views.
 * - <span color=00ffff>{@link ve.WordProcessor.initWYSIWYG|initWYSIWYG}</span>() - Internal helper function. Initialises the component.
 * - 
 * - <span color=00ffff>{@link ve.WordProcessor.addParagraphTag|addParagraphTag}</span>(arg0_e:{@link KeyboardEvent})
 * - <span color=00ffff>{@link ve.WordProcessor.parentTagActive|parentTagActive}</span>(arg0_el:{@link HTMLElement}) | {@link boolean}
 * - <span color=00ffff>{@link ve.WordProcessor.selectionChange|selectionChange}</span>(arg0_e:{@link Event}, arg1_buttons:{@link Array}<{@link HTMLElement}>, arg2_editor:{@link HTMLElement}) | {@link boolean} - Fires an internal selection change event.
 * - <span color=00ffff>{@link ve.WordProcessor.pasteEvent|pasteEvent}</span>(arg0_e:{@link ClipboardEvent})
 * 
 * ##### Static Methods:
 * - <span color=00ffff>{@link ve.WordProcessor.execCodeAction|execCodeAction}</span>(arg0_button_el:{@link HTMLElement}, arg1_editor_el:{@link HTMLElement}, arg2_visual_view_el:{@link HTMLElement}, arg3_html_view_el:{@link HTMLElement})
 * - <span color=00ffff>{@link ve.WordProcessor.execDefaultAction|execDefaultAction}</span>(arg0_action:{@link string})
 * - <span color=00ffff>{@link ve.WordProcessor.execLinkAction|execLinkAction}</span>(arg0_modal_el:{@link HTMLElement})
 * - <span color=00ffff>{@link ve.WordProcessor.restoreSelection|restoreSelection}</span>(arg0_saved_selection:{@link Selection})
 * - <span color=00ffff>{@link ve.WordProcessor.saveSelection|saveSelection}</span>() | {@link Range}
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.WordProcessor}
 */
```

The following represent regular components, which are generally contained within their own files.

**ve.Button**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Generic button used to call a function upon user click. If multiple buttons are to be inline, they may be appended using {@link ve.RawInterface} as a container.
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link function}({@link MouseEvent}) - The function to call upon user click.
 * - `arg1_options`: {@link Object}
 * 
 * ##### Instance:
 * - `.v`: {@link function} - Accessor. The current function stored by the {@link ve.Button} component.
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Button}
 */
```

**ve.Checkbox**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Either used as a toggle (boolean) or more extensively as a nested checkbox list (Object), depending on the type.
 * - Functional binding: <span color=00ffff>veCheckbox</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link boolean|Object}
 *   - `<checkbox_group_key>`: {@link Object}
 *     - `.name`: {@link string}
 *     - `<checkbox_key>`: {@link boolean}
 *   - `<checkbox_key>`: {@link boolean}
 * - `arg1_options`: {@link Object}
 * 
 * ##### Instance:
 * - `.v`: {@link boolean}|{@link Object} - Equivalent to the `arg0_value` initialiser in structure.
 * 
 * ##### Static Methods:
 * - <span color=00ffff>{@link ve.Checkbox.generateHTMLRecursively}</span>(arg0_value:{@link boolean}|{@link Object}) | {@link Array}<{@link string}>
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Checkbox}
 */
```

**ve.Colour**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 *
 * Basic colour input used to fetch [R, G, B] parameters. May also fetch hex value via <span color = 00ffff>getHex</span>().
 * - Functional binding: <span color=00ffff>veColour</span>().
 *
 * ##### Constructor:
 * - `arg0_value`: {@link Array}<{@link number}, {@link number}, {@link number}>
 * - `arg1_options`: {@link Object}
 *   - `.is_rgba=false`: {@link boolean} - If true, adds an opacity slider and handles [R, G, B, A] values.
 *
 * ##### Instance:
 * - `.v`: {@link Array}<{@link number}, {@link number}, {@link number}> - The R, G, B (and optional A) value of the present Component.
 *
 * ##### Methods:
 * - <span color=00ffff>{@link ve.Colour.getHex|getHex}</span>() | {@link string} - Returns the hex value of the present R, G, B value.
 * - <span color=00ffff>{@link ve.Colour.toString|toString}</span>() | {@link string} - Returns the R,G,B value as a string.
 *
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Colour}
 */
```

**ve.Datalist**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Datalist component, typically a text component with autocomplete suggestions. May sometimes also be used as a primitive for search select.
 * - Functional binding: <span color=00ffff>veDatalist</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link Object}<{@link string}> - Read-only names are values, internal IDs are keys.
 * - `arg1_options`: {@link Object}
 *   - `.disabled=false`: {@link boolean}
 *   - `.selected`: {@link string} - The name of the selected value.
 * 
 * ##### Instance:
 * - `.v`: {@link string} - The current ID selected by the datalist. If no valid ID is found, the raw `.value` of the datalist element is returned.
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Datalist}
 */
```

**ve.Date**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Date component used for selecting historical dates over the long run. The value stored is an object with the structure { year: {@link number}, month: {@link number}, day: {@link number}, hour: {@link number}, minute: {@link number} }, with negative years representing BC. This data structure is otherwise known as a {@link UF.Date}.
 * - Functional binding: <span color=00ffff>veDate</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link UF.Date}
 * - `arg1_options`: {@link Object}
 *   - `.disabled=false`: {@link boolean}
 * 
 * ##### Instance:
 * - `.v`: {@link UF.Date}
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.Date.handleEvents|handleEvents}</span>() - Used internally to handle events for all date inputs.
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Date}
 */
```

**ve.DateLength**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Date length component used for managing historical time durations. The value stored is an object with the structure { year: {@link number}, month: {@link number}, day: {@link number}, hour: {@link number}, minute: {@link number} }, with negative years representing BC. This data structure is otherwise known as a {@link UF.Date}.
 * - Functional binding: <span color=00ffff>veDateLength</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link UF.Date}
 * - `arg1_options`: {@link Object}
 *   - `.disabled=false`: {@link boolean}
 * 
 * ##### Instance:
 * - `.v`: {@link UF.Date}
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.veDateLength}
 */
```

**ve.File**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Basic file input that can also accept folders. Note that if you need a file explorer, you should refer to {@link ve.FileExplorer}, though this component uses its subtype.
 * - Functional binding: <span color=00ffff>veFile</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link string} - The current file path, if any.
 * - `arg1_options`: {@link Object}
 *   - `.do_not_display=false`: {@link boolean} - Whether to display the file name to the left of the select file prompt
 *   - `.is_folder=false`: {@link boolean} - Whether the input is asking for a folder.
 *   - `.multifile=false`: {@link boolean} - Whether the input can accept multiple files/folders.
 *   - `.save_function`: {@link function} - If set, the current component will be a save prompt.
 * 
 * ##### Instance:
 * - `.v`: {@link string}
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.FileExplorer.openModal|openModal}</span>()
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.File}
 */
```

**ve.FlexInterface**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Flex interface used for partitions within the same window that can be automatically resized by the user, similar to sub-windows.
 * - Functional binding: <span color=00ffff>veFlexInterface</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link Object}
 *   - `<category_key>`: {@link Object}
 *     - `<category_key>`: {@link Object}
 *     - `<component_key>`: {@link ve.Component}
 *       - `.options`: {@link Object}
 *         - `.flex_disabled=false`: {@link boolean}
 *     - `.type="horizontal"` - Either 'horizontal'/'vertical'.
 *   - `.type="horizontal"` - Either 'horizontal'/'vertical'.
 * - `arg1_options`: {@link Object}
 * 
 * ##### Instance:
 * - `<category_key>`: {@link Object}<{@link ve.Component}|{@link Object}>
 * - `<component_key>`: {@link ve.Component}
 * - `.reserved_keys`: {@link Array}<{@link string}> - Controls what keys are reserved and cannot be destructured.
 * - `.v`: {@link Object}
 * - `.value`: {@link Object} - Uses this.value instead of this.components_obj.
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.FlexInterface.handleEvents|handleEvents}</span>()
 * - <span color=00ffff>{@link ve.FlexInterface.handleResize|handleResize}</span>(arg0_e:{@link Event}, arg1_size_property:{@link string}, arg2_position_property:{@link string})
 * 
 * ##### Static Methods:
 * - <span color=00ffff>{@link ve.FlexInterface.generateHTMLRecursively|generateHTMLRecursively}</span>(arg0_root_el:{@link HTMLElement}, arg1_value:{@link Object}, arg2_options:{ flex_disabled:{@link boolean} })
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.FlexInterface}
 */
```

**ve.HTML**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Custom component used to encapsulate any HTML that may need to be mounted to Vercengen. Also used for immediate-mode displays.
 * - Functional binding: <span color=00ffff>veHTML</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link function}|{@link HTMLElement}|{@link string} - If a function, the function must return a string, preferably in closure.
 * - `arg1_options`: {@link Object}
 * 
 * ##### Instance:
 * - `.v`: {@link HTMLElement}
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.HTML.toString|toString}</span>() | {@link string}
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.HTML}
 */
```

**ve.Interface**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Interface used for encapsulating other {@link ve.Component}s in a grid-like formatting pattern. Recursive.
 * - Functional binding: <span color=00ffff>veInterface</span>().
 * 
 * ##### Constructor:
 * - `arg0_components_obj`: {@link Object}<{@link ve.Component}>
 * - `arg1_options`: {@link Object}
 *   - `.is_folder=false`: {@link boolean}
 *   - `.open=false`: {@link boolean}
 *   - `.type="default"`: {@link string} - Either 'default'/'flex'/'raw'. Returns a {@link ve.FlexInterface} and {@link ve.RawInterface} in other cases.
 * 
 * ##### Instance:
 * - `<component_key>`: {@link ve.Component} - Automatic destructuring for component_key.
 * - `.components_obj`: {@link Object}<{@link ve.Component}> - Internal private field for `.v`.
 * - `.dimensions=[0,0]`: {@link Array}<{@link number}, {@link number}>
 *   `.reserved_keys`: {@link Array}<{@link string}> - Controls what keys are reserved and cannot be destructured.
 * - `.v`: {@link Object}<{@link ve.Component}>
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.Interface.addComponent|addComponent}</span>(arg0_component_key:{@link string}, arg1_component_obj:{@link ve.Component})
 * - <span color=00ffff>{@link ve.Interface.redraw|redraw}</span>() - Recalculates coordinates before calling {@link ve.Interface.refresh|this.refresh}().
 * - <span color=00ffff>{@link ve.Interface.refresh|refresh}</span>() - Redraws the present interface without recalculating coordinates.
 * - <span color=00ffff>{@link ve.Interface.removeComponent|removeComponent}</span>(arg0_component_obj:{@link ve.Component})
 * - <span color=00ffff>{@link ve.Interface.resize|resize}</span>(arg0_width:{@link number}, arg1_height:{@link number})
 * 
 * ##### Static Methods:
 * - <span color=00ffff>{@link ve.Interface.assignComponentCoordinates|assignComponentCoordinates}</span>(arg0_components_obj:{@link Object}<{@link ve.Component}>)
 * - <span color=00ffff>{@link ve.Interface.getDefinedComponentDimensions|getDefinedComponentDimensions}</span>(arg0_components_obj:{@link Object}<{@link ve.Component}>)
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Interface}
 */
```

**ve.List**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Generic horizontal list input for non-nested lists with reorderable elements, i.e. arrays.
 * - Functional binding: <span color=00ffff>veList</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link Array}<{@link ve.Component}>
 * - `arg1_options`: {@link Object}
 *   - `.do_not_allow_insertion=false`: {@link boolean}
 *   - `.do_not_display_info_button=false`: {@link boolean}
 *   - `.max`: {@link number} - The maximum number of elements in the array.
 *   - `.min=0`: {@link number} - The minimum number of elements in the array.
 *   - `.ondelete`: {@link function}(arg0_component_obj:{@link ve.Component})
 *   - `.options`: {@link Object} - The `.options` field to pass onto elements in the array.
 *   - `.split_rows=true`: {@link boolean} - Whether to split item rows onto separate lines.
 *   
 * ##### Instance:
 * - `.v`: {@link Array}<{@link ve.Component}>
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.List}
 */
```

**ve.Map**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Creates a Maptalks {@link maptalks.Map} that can be used for mounting and displaying geometries and tilelayers to.
 * - Functional binding: <span color=00ffff>veMap</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link Object} - The {@link maptalks.Map} `.options` that determines the projection and base layer.
 * - `arg1_options`: {@link Object}
 * 
 * ##### Instance:
 * - `.map`: {@link maptalks.Map}
 * - `.v`: {@link maptalks.Map}
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.Component.Map.clear|clear}</span>()
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Map}
 */
```

**ve.MultiTag**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Represents a multi tag input with unique metadata attributes for keywording.
 * - Functional binding: <span color=00ffff>veMultiTag</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link Array}<{@link string}>
 * - `arg1_options`: {@link Object}
 *   - `.tags_key="global"`: {@link string} - The namespace to assign to the current MultiTag component to be shared between instances.
 * 
 * ##### Instance:
 * - `.registry_array`: {@link Array}<{@link string}> - Read-only. Global registry array shared between instances.
 * - `.v`: {@link Array}<{@link string}>
 *   
 * ##### Methods:
 * - <span color=00ffff>{@link ve.MultiTag.notifyAllInstances|notifyAllInstances}</span>()
 * - <span color=00ffff>{@link ve.MultiTag.refresh|refresh}</span>()
 * - <span color=00ffff>{@link ve.MultiTag.updateLocalTags|updateLocalTags}</span>()
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.MultiTag}
 */
```

**ve.Number**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Represents a number input that can be set by the user.
 * - Functional binding: <span color=00ffff>veNumber</span>().
 * 
 * ##### Constructor:
 * - `arg0_value=0`: {@link Array}<{@link number}>|{@link number}
 * - `arg1_options`: {@link Object}
 *   - `.disabled=false`: {@link boolean}
 *   - `.max`: {@link number}
 *   - `.min`: {@link number}
 *   - `.step`: {@link number}
 * 
 * ##### Instance:
 * - `.v`: {@link number} 
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.Number.toString|toString}</span>() | {@link string}
 * - <span color=00ffff>{@link ve.Number.valueOf|valueOf}</span>() | {@link number}
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Number}
 */
```

**ve.ObjectInspector**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Object inspector similar to DevTools that has nested dropdowns and parses Javascript Object Literals (as opposed to JSON.stringify).
 * - Functional binding: <span color=00ffff>veObjectInspector</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link any}|{@link Object}
 * - `arg1_options`: {@link Object}
 *   - `.key_name="Object"`: {@link string} - The key name of the root object if relevant. Affects IDs in generated HTML.
 *   - `.max_depth=15`: {@link number} - The maximum recursion depth to display.
 * 
 * ##### Instance:
 * - `.v`: {@link any}|{@link Object} - The object to display in the inspector window.
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.ObjectInspector}
 */
```

**ve.PageMenu**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Multipage menu with a relative topbar for the user to switch between tabs. Contains an interface otherwise.
 * - Functional binding: <span color=00ffff>vePageMenu</span>().
 * 
 * ##### Constructor:
 * - `arg0_page_obj`: {@link Object}
 *   - `<page_key>`: {@link Object}
 *     - `.name`: {@link string}
 *     - `.options`: {@link Object} - Same as the `.options` in {@link ve.Interface}.
 *     - `.components_obj`: {@link Object}<{@link ve.Component}>
 * - `arg1_options`: {@link Object}
 *   - `.starting_page=Object.keys(page_obj)[0]`
 * 
 * ##### Instance:
 * - `.interface_el`: {@link HTMLElement}
 * - `.interfaces_obj`: {@link Object}<{@link ve.Interface}> - Contains all interfaces in all pages.
 * - `.navbar_el`: {@link HTMLElement}
 * - `.underline_el`: {@link HTMLElement}
 * - `.v`: {@link string} - The current `<page_key>` selected by the ve.PageMenu.
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.PageMenu.updateUnderline|updateUnderline}</span>()
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.PageMenu}
 */
```

**ve.Password**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Password input for the end user.
 * - Functional binding: <span color=00ffff>vePassword</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link string} - The password placeholder for the given input.
 * - `arg1_options`: {@link Object}
 *   - `.disabled=false`: {@link boolean}
 * 
 * ##### Instance:
 * - `.v`: {@link string}
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Password}
 */
```

**ve.Radio**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Mutually exclusive radio input with a specific reserved namespace. Consider using {@link ve.Checkbox} if you do not intend inputs to be mutually exclusive.
 * - Functional binding: <span color=00ffff>{@link ve.Radio}</span>
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link Object}
 *   - `<radio_group_key>`: {@link Object}
 *     - `.is_category`: true - You must set `.is_category` to true for it to take effect.
 *     - `<radio_key>`: {@link Object}
 *   - `<radio_key>`: {@link Object}
 *     - `.name`: {@link string}
 *     - `.selected`: {@link boolean}
 * - `arg1_options`: {@link Object}
 *   - `.selected`: {@link string} - Overrides the `<option_key>.selected` option in `arg0_value`.
 * 
 * ##### Instance:
 * - `.v`: {@link Object}<{@link boolean}> - Recursive value, the same as `arg0_value`.
 * 
 * ##### Static Fields:
 * - `.instances`: {@link Array}<{@link ve.Radio}>
 *   
 * ##### Static Methods:
 * - <span color=00ffff>{@link ve.Radio.generateHTMLRecursively|generateHTMLRecursively}</span>(arg0_value:{@link Object}<{@link boolean}>, arg1_this:{@link ve.Radio}) | {@link string}
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Radio}
 */
```

**ve.Range**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Creates a range selector, typically between 0-1 with a 0,01 step. These may be customised in set options.
 * - Functional binding: <span color=00ffff>veRange</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link number}
 * - `arg1_options`: {@link Object}
 *   - `.disable_number_input=false`: {@link boolean}
 *   - `.disabled=false`: {@link boolean}
 *   - `.max=1`: {@link number}
 *   - `.min=0`: {@link number}
 *   - `.step=0.01`: {@link number}
 * 
 * ##### Instance:
 * - `.v`: {@link number} 
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.Range.toString|toString}</span>() | {@link string}
 * - <span color=00ffff>{@link ve.Range.valueOf|valueOf}</span>() | {@link number}
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Range}
 */
```

**ve.RawInterface**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Raw interface used for creating a container {@link HTMLElement} that encapsulates components underneath it. Additionally destructures any components contained within.
 * - Functional binding: <span color=00ffff>veRawInterface</span>().
 * 
 * ##### Constructor:
 * - `arg0_components_obj`: {@link Object}<{@link ve.Component}>
 * - `arg1_options`: {@link Object}
 *   - `.no_name_element=false`: {@link boolean}
 * 
 * ##### Instance:
 * - `<component_key>`: {@link ve.Component} - Contains any destructured components.
 * - `.components_obj`: {@link Object}<{@link ve.Component}>
 * - `.reserved_keys`: {@link Array}<{@link string}> - Controls what keys are reserved and cannot be destructured.
 * - `.v`: {@link Object}<{@link ve.Component}>
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.RawInterface}
 */
```

**ve.RichText**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 *
 * Single-line rich text editor with bold, italic, underline, and clear text formatting options.
 *
 * BIUF stands for Bold, Italic, Underline, Formatting.
 * - Functional binding: <span color=00ffff>veRichText</span>().
 *
 * ##### Constructor:
 * - `arg0_value`: {@link string} - The HTML content to initialise the component with.
 * - `arg1_options`: {@link Object}
 *   - `.disabled=false`: {@link boolean} - Controls the .readonly attribute.
 *
 * ##### Instance:
 * - `.v`: {@link string} - Returns an HTML string.
 *
 * ##### Methods:
 * - <span color=00ffff>{@link ve.RichText.handleBIUF|handleBIUF}</span>(arg0_biuf_el:{@link HTMLElement})
 * - <span color=00ffff>{@link ve.RichText.initBIUFToolbar|initBIUFToolbar}</span>()
 * - <span color=00ffff>{@link ve.RichText.sendOnchangeEvent|sendOnchangeEvent}</span>()
 *
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.RichText}
 */
```

**ve.SearchSelect**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Search select/filter component used as a raw interface pool with a searchbar in which users can look up matching items with selected 'data-' attributes. Elements with the attribute `ve-display=true` will always be shown.
 * - Functional binding: <span color=00ffff>veSearchSelect</span>().
 * 
 * ##### Constructor:
 * - `arg0_components_obj`: {@link Object}<{@link ve.Component}> - The individual items to append to the current search select field.
 * - `arg1_options`: {@link Object}
 *   - `.display="inline"`: {@link string}
 *   - `.header_components_obj`: {@link Object}<{@link ve.Component}>
 *   - `.hide_filter=false`: {@link boolean} - Whether to hide the filter tool.
 *   - `.filter_names`: {@link function}(arg0_attribute_key:{@link string})|{@link Object}
 *     - `<attribute_key>`: {@link string}
 *   - `.search_select_els`: {@link function} | {@link Array}<{@link HTMLElement}> - The function that returns the search select elements in question, usually `document.querySelectorAll`.  
 *   - `.search_keys=["name"]`: {@link Array}<{@link string}>
 *     
 * ##### Instance:
 * - `.components_obj`: {@link Object}<{@link ve.Component}>
 * - `.filters`: {@link Object} - Any filters currently applied to the component.
 *   - `<filter_key>`: true
 * - `.search_value`: {@link string} - The current user search query.
 * - `.v`: {@link this.components_obj} - Accessor. The current components_obj mounted to ve.SearchSelect.
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.SearchSelect.getComponentElements|getComponentElements}</span>() | {@link Array}<{@link HTMLElement}>
 * - <span color=00ffff>{@link ve.SearchSelect.updateSearchFilter|updateSearchFilter}</span>()
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.SearchSelect}
 */
```

**ve.Select**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Conventional select dropdown that returns the key of the option selected by the end user.
 * - Functional binding: <span color=00ffff>veSelect</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link Array}<{@link string}>|{@link Object}
 *   - `<option_key>`: {@link Object|string}
 *     - `.name`: {@link string}
 *     - `.selected`: {@link boolean} - Whether the current option is selected.
 * - `arg1_options`: {@link Object}
 *   - `.disabled=false`: {@link boolean}
 *   - `.selected`: {@link string} - Overrides the `<option_key>.selected` option in `arg0_value`. 
 * 
 * ##### Instance:
 * - `.v`: {@link string} - The selected option key. 
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.Select.generateHTML|generateHTML}</span>() | {@link Array}<{@link string}> - Returns the HTML for the present select input.
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Select}
 */
```

**ve.Table**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Table that be converted to and from {@link ve.Spreadsheet} and back. Only takes in a 2D array list. Any edits in spreadsheet mode will be converted back to the view-only mode if possible.
 * - Functional binding: <span color=00ffff>veTable</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link Array}<{@link Array}<{@link any}>> 
 *   - Nested arrays: [n1] - Sheet, [n2] - Row
 * - `arg1_options`: {@link Object}
 *   - `.page_size=50`: {@link number}
 *   - `.sortable=true`: {@link boolean}
 *   - `.sort_ascending=true`: {@link boolean}
 *   - `.sort_column`: {@link number} - Which column should have its sort indicator active. 0-indexed.
 *   - `.dark_mode=false`: {@link boolean} - Whether the spreadsheet editor should launch in dark mode.
 *   
 * ##### Instance:
 * - `.v`: {@link Array}<{@link Array}<{@link any}>>
 *   
 * ##### Methods:
 * - <span color=00ffff>{@link ve.Table.convertToSpreadsheet|convertToSpreadsheet}</span>() | {@link ve.Spreadsheet}
 * - <span color=00ffff>{@link ve.Table.convertToTable|convertToTable}</span>() | {@link ve.Table}
 * - <span color=00ffff>{@link ve.Table.draw|draw}</span>()
 * - <span color=00ffff>{@link ve.Table.drawPages|drawPages}</span>()
 * - <span color=00ffff>{@link ve.Table.sort|sort}<span>(arg0_index:{@link number})
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Table}
 */
```

**ve.Telephone**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Handles telephone inputs with a basic text field with forced constraints.
 * - Functional binding: <span color=00ffff>veTelephone</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link string} - The current telephone number stored by the component.
 * - `arg1_options`: {@link Object}
 *   - `.disabled=false`: {@link boolean}
 *   - `.placeholder="+(XX)-000-000-0000"`: {@link string}
 * 
 * ##### Instance:
 * - `.v`: {@link string}
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Telephone}
 */
```

**ve.Text**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Generic single-line text input without rich text formatting options.
 * - Functional binding: <span color=00ffff>veText</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link Array}<{@link string}>|{@link string}
 * - `arg1_options`: {@link Object}
 *   - `.disabled=false`: {@link boolean}
 *   - `.length`: {@link number}
 *   - `.max`: {@link number}
 *   - `.min`: {@link number}
 * 
 * ##### Instance:
 * - `.v`: {@link string}
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Text}
 */
```

**ve.Time**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Time input for selecting a given hour/minute. For longer date components with years, see {@link ve.Date} or {@link ve.DateLength} for time durations.
 * - Functional binding: <span color=00ffff>veTime</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {hour: {@link number}, minute: {@link number}}
 * - `arg1_options`: {@link Object}
 *   - `.disabled=false`: {@link boolean}
 *   - `.max`: {@link number}
 *   - `.min`: {@link number}
 * 
 * ##### Instance:
 * - `.v`: {hour: {@link number}, minute: {@link number}}
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Time}
 */
```

**ve.Toggle**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Toggle component with HTML labels for on/off switches. Mainly returns a boolean value.
 * - Functional binding: <span color=00ffff>veToggle</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link boolean}
 * - `arg1_options`: {@link Object}
 *   - `.off_label`: {@link string} - The off label to be displayed after the HTML icon.
 *   - `.off_name`: {@link string} - The off name, including the HTML icon, to be displayed in its off state.
 *   - `.on_label`: {@link string} - The on label to be displayed after the HTML icon.
 *   - `.on_name`: {@link string} - The on name, including the HTML icon, to be displayed in its on state.
 *   - `.name`: {@link string} - If set, this reflects a common label shared between both the off/on states.
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.Toggle.updateName|updateName}</span>()
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.Toggle}
 */
```

**ve.UndoRedo**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Undo/Redo interface with the ability for users to navigate between different {@link DALS.Timeline} instances. Undo/Redo tree by default with both a canvas interface and HTML list.
 * 
 * ##### Constructor:
 * - `arg0_value=DALS.Timeline.current_timeline`: {@link string} - The timeline ID the initial value should be set to.
 * - `arg1_options`: {@link Object}
 * 
 * ##### Instance:
 * - `.v`: {@link string}
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.UndoRedo.draw|draw}</span>() - Redraws both HTML/canvas-side elements.
 * - <span color=00ffff>{@link ve.UndoRedo.handleEvents|handleEvents}</span>() - Handles events for zooming/panning around canvas.
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.UndoRedo}
 */
```

**ve.URL**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Component}</span> for methods or fields inherited from this Component's parent such as `.options.attributes` or `.element`.
 * 
 * Used to insert a link/URL, typically with an associated WYSIWYG hyperlink for the user to preview.
 * - Functional binding: <span color=00ffff>veURL</span>().
 * 
 * ##### Constructor:
 * - `arg0_value`: {@link string}
 * - `arg1_options`: {@link Object}
 *   - `.disabled=false`: {@link boolean}
 *   
 * ##### Instance:
 * - `.v`: {@link string}
 * 
 * @augments ve.Component
 * @memberof ve.Component
 * @type {ve.URL}
 */
```