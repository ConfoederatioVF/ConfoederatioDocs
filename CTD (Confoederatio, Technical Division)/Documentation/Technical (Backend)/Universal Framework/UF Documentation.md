◥ UNIVERSAL FRAMEWORK (UF).

Project 0001.

Abstract.

A single project to create a JS framework of which every Confoederatio technical project can be easily and modularly created with minimal effort. As such, it should be as wide-ranging and powerful as possible, with a standardised nomenclature geared towards fundamental, repetitive, and tedious operations.

ABRS. [TODO]

Currently, Universal Framework lacks synchronisation capability across multiple projects. To maintain this synchronisation, a path pointer file is necessary within the base project folder. Its update .bat file can then be called upon runtime instantiation to ensure that it is up to date with present version control. This is to be done as soon as Naissance reaches a stable Alpha state such that UF can be edited across multiple pieces of software. IDs are to be assigned as follows:

- Project 0001: UF (Electron) [Initial version is to be rolled out from Project 1706 - Naissance].
- Project 0002: UF (Discord/Node.js)
- Project 0003: UF (Browser)

Paradigm.

The new framework ought to be functional and accessible at the global level with standard namespaces for each feature to prevent naming conflicts (unless an alternative usage of the name is unlikely for certain niche modules). These are listed below.

Parts and Specifications.

Various UF parts are marked either as IMP-PRIMARY, IMP-SECONDARY, or IMP-AUXILIARY. This indicates the ordinal importance of their implementation, and primary importance is assumed unless mentioned otherwise. It is likely not all features can be immediately implemented or high priority, and partial implementation of the standard is expected. Percentage values will be given where appropriate.

UF can be broken down into two basic variants: a browser variant which can handle UI, and a NodeJS variant which can handle File I/O operations in addition to Discord.JS. Such a taxonomy appears thus:

- Browser Versions (including Electron)
    - Base CSS Themes and Animations
    - Browser UI Framework
        - Context Menus
        - Large Fixed Menus
        - Leaflet/Entity-Dependent Menus
        - Tabs and Pagination
    - Geodata
    - In-built Console
    - Interactive Statistical Rendering
    - SVG Path/Data Manipulation
    - WYSIWYG Editing
- Node Versions (including Discord)
    - Discord Button Handler
    - Discord Channels/Inactivity Clearers
    - Discord Reaction Framework
    - Discord Select Handler
    - Discord UI Framework
    - Discord Users/Userdata
    - Discord Visual Prompts
- Generic Features:
    - ABRS
    - Actions
    - Arrays
    - Colours
    - Date Framework
    - Debugging
    - File I/O
    - Formatting
    - Graphing
    - Lexing/Parsing
    - Localisation
    - Log
    - Numbers
    - Objects
    - Pathfinding
    - Statistics
    - Strings
    - Web Scraping
- ABRS (Automated Backup and Restoration System)

Automatically backs up and restores systems when working. Includes features to detect corrupted and empty files in backups, as well as maximum file size and numeric limits in addition to database compression. Should have features for rudimentary auto-debugging (by commenting out files and saving backups of those) and error steamrolling if enabled.

Includes serialisation options for OOP-style programming.

Functions.

Basic.

- changeSaveDirectory() - Changes the default save directory to a defined path.
    - arg0_path: (String) - The path string to change the save directory to.
- cleanCorruptFiles() - Cleans empty files and files that can’t be parsed to JSON
    - arg0_options: (Object)
        - log: (Boolean) - Optional. Whether to log the backup array. True by default.
- cleanEmptyFiles() - Removes empty files in a directory.
    - arg0_options: (Object)
        - log: (Boolean) - Optional. Whether to log the cleanup. True by default.
- cleanInvalidJSONFiles() - Removes corrupted JSON files from a directory.
    - arg0_options: (Object)
        - log: (Boolean) - Optional. Whether to log the backup array. True by default.
- cleanEscapeStrings() - Cleans escape strings from a given string.
    - arg0_string: (String) - The input string to pass to the function.
    - Returns: (String)
- loadBackupArray() - Loads a backup array in chronological order.
    - arg0_options: (Object)
        - log: (Boolean) - Optional. Whether to log the backup array. True by default.
- loadMostRecentSave() - Loads the most recent save in the current global.backup_array.
    - arg0_options: (Object) - Same as loadSave()
- loadRequirements() - Loads library requirements for ABRS
- loadSave() - Loads a save from a file into global.main, or initialises a custom function for it.
    - arg0_file: (String) - The file name to attempt loading.
    - arg1_options: (Object)
        - compressed_json: (Boolean) - Optional. Whether compressed JSON is enabled. True by default
        - db_file: (String) - Optional. The database path. 'database.js' by default
        - load_object_function: (String) - Optional. The string variable address for the current load object function. Undefined by default, meaning objects will be loaded into global.main
- returnABRSDateString() - Returns the current date as an ABRS debug string.
    - Returns: (String)
- writeDB() - Writes the DB to a current file.
    - arg0_options: (Object)
        - log: (Boolean) - Optional. Whether to log the backup array. True by default.
- writeSave() - Writes a save to backups folder.
    - arg0_options: (Object)
        - do_not_clean_escapes: (Boolean) - Optional. Whether to clear escapes. False by default.
        - file_limit: (Number) - Optional. The amount of backups to keep
        - save_object_function: (String) - The string variable address for the current save object function.

Actions.

DATATYPES.

- Action.

An action is used to represent a data change within an undo/redo tree, so that it can be reversed/forwarded in the future.

global.actions: (Object) - Stores all actions at the global level.

current_timeline: (String) - The current selected timeline ID.

initial_timeline: (String) - The ID of the root timeline. This may be changed if deleted.

<action_key>: (Object) - Indexes a possible delta action.

id: <action_key>: (String) - The ID of the current action key.

name: (String) - The human-readable name of the action.

delta_toggle: (String) - ‘undo’/’redo’. Whether or not a traversal over this should undo or redo. Functions as a toggle. ‘undo’ by default.

redo_function: (String) - The corresponding redo function.

redo_function_parameters: (Array<Variable, …>) - The parameters to feed into the redo function.

undo_function: (String) - The corresponding undo function.

undo_function_parameters: (Array<Variable, …>) - The parameters to feed into the undo function.

- Timeline.

A timeline stores all delta actions for future reference. Unneeded timelines can be pruned, and timeline lookback length can be specified.

global.timelines: (Object) - Stores all timelines at the global level.

<timeline_id>: (Array<Object>) - Stores a list of delta actions.

- Timeline Graph.

Stores the tree of all current timelines, starting from global.actions.initial_timeline.

Caching Actions.

- createAction() - Sets the action performed in the current timeline.
    - arg0_action_key: (String) - The key to assign to the action in question.
    - arg1_options: (Object)
        - name: (String) - The human-readable name of the action.
- function: (String) - The function key which performs the action
- reverse_function: (String) - The function key which reverses the action

- <variable_name>: (Variable) - Other flags to transfer over to the action object.
- Returns: (Object, Action)
- deleteAction()
    - arg0_action_key: (String) - The key of the action to delete.
    - Returns: (Object, Action)
- initialiseUndoRedo() - Initialises action config/caching if necessary.

Action Timelines.

- createTimeline() - Creates a new timeline from a parent (or an unassociated one if no parent is defined). The parent may be cloned into the new timeline if necessary.
    - arg0_parent_timeline: (String) - Optional. The ID of the parent timeline to split off from. global.actions.initial_timeline by default.
    - arg1_options: (Object)
        - timeline_index: (Number) - Optional. The index off which the timeline should be split. The last index of the timeline by default.
        - return_key: (Boolean) - Optional. Whether to return the timeline key. False by default.
    - Returns: (Object, Timeline)/(String)
- constructTimelineGraph() - Returns an A* compatible graph of global.timelines.
    - Returns: (Object)
        - <Timeline ID-index>: (Object)
            - <Timeline ID-index>: (Number) - Represents the connection cost between the current Timeline Position and another Timeline Position.
- deleteTimeline() - Deletes a timeline and the timelines that branch off it.
    - arg0_timeline_id: (String) - The timeline ID to delete.
- generateTimelineGraph() - Returns a graph of all timelines starting from initial_timeline[0].
    - arg0_timeline_id: (String) - The ID of the timeline to start generating a graph from.
    - arg1_options: (Object)
        - x_offset: (Number) - Optional. The current x offset. 0 by default.
        - y_offset: (Number) - Optional. The current y offset. 0 by default.
    - Returns: (Object)
- getTImelineWidth() - Fetches the total X/Y width of a timeline from all future descendant timelines.
    - arg0_timeline_id: (String) - The ID of the timeline to measure the descendant width of.
    - Returns: (Number)
- loadTimeline() - Loads in the current timeline, undoing/redoing all actions needed to get there.
    - arg0_timeline_Id: (String) - The ID of the timeline to load into the current state.
    - arg1_options: (Object0
        - timeline_index: (Number) - Optional. The index off which the timeline should split. The last index of the timeline by default.
- jumpToTimeline() - Jumps to a specific timeline.
    - arg0_timeline_id: (String) - The ID of the timeline to jump to
- redoAction() - Redoes an action in the current timeline.
    - Returns: (Boolean) - Whether the action was successfully redone.
- performAction() - Logs a delta action in the current timeline.
    - arg0_actions: (Object)
        - action_id: (String) - The ID of the action currently being performed.
        - redo_function: (String) - The corresponding redo function.
        - redo_function_parameters: (Array<Variable, ...>) - The current arguments passed to perform the delta action.
        - undo_function: (String) - The corresponding undo function.
        - undo_function_parameters: (Array<Variable, ...>) - The arguments needed to undo the delta action.
- undoAction() - Undoes the last action in the current timeline.
    - Returns: (Boolean) - Whether the action was successfully undone.

Arrays.

DATATYPES.

- Dataframe.

Array<Array, …> - 2D array representing a dataframe.

- [0]: Represents the header row, storing all variables.
- [...]: Data rows underneath the header
- Basic.
    - createArray() - Creates an array from the following options.
    - arg0_options: (Object)
        - domain: (Array<Number, Number>) - Creates an integer array between min, max.
        - linear_sequence: (Array<Number, Number, Number>) - Generates a linear sequence from linear_sequence[0] to linear_sequence[1] in steps of linear_sequence[2].
        - sequence: (Array<String>, Number) - Generates a sequenced array according to a mathematical equation.
            - sequence[0] - Mathematical equation as a string literal. The current iteration when generating the sequence is referred to as 'n'.
            - sequence[1] - The total number of iterations to repeat the sequence for.
        - repeat: (Array<Array<...>, Number>) - Repeats an array x times.
        - repeat_each: (Array<Array<...>, Number>) - Repeats each element of an array x times.
        - Returns: (Array)
    - dimensionality() - Formats an array with n dimensions with zero-indexed dimensionality.
    - arg0_input_array: (Array) - The array to input.
    - arg1_dimension_array: (Array<Number, …>) - An array providing the dimensions of the current array (what to break it down into), starting wit the Y dimension.
    - Returns: (Array<Array, …>)
- flattenArray() - Flattens a nested array to be 1-deep.
    - arg0_input_array: (Array) - The array to input.
    - Returns: (Array)
- getCardinality() - Fetches the cardinality of an array/object/variable.
    - arg0_variable: (Variable) - The variable to input.
    - Returns: (Number)
- getRecursiveCardinality() - Fetches the total number of elements in an array, including subarrays.
    - arg0_variable: (Variable) - The variable to input.
    - Returns: (Number)
- isArrayEmpty() - Checks whether an array is empty, including undefined/null values.
    - arg0_input_array: (Array) - The array to input.
    - Returns: (Boolean)
- truncateArray() - Truncates an array to a given length.
    - arg0_input_array: (Array) - The array to input.
    - arg1_length: (Number) - The length to truncate the array to.
    - Returns: (Array)
- reverseArray() - Reverses an input array.
    - arg0_input_array: (Array) - The array to reverse.
    - Returns: (Array)
- uniqueArray() - Removes any duplicate elements from an input array.
    - arg0_input_array: (Array) - The array to input.
    - Returns: (Array)
- Conversion.
- arrayToObject() - Casts an array to object.
    - arg0_array: (Array) - The array to input.
    - Returns: (Object)
- objectToArray() - Casts an object to array.
    - arg0_input_object: (Object) - The object to input.
    - Returns: (Array)
- Dataframes.
- appendDataframes() - Appends two dataframes to one another.
    - arg0_dataframe: (Array<Array, ...>) - The dataframe to input into the function.
    - arg1_dataframe: (Array<Array, ...>) - The dataframe to append.
    - arg2_options: (Object)
        - default_value: (Variable) - Optional. What the default value should be. Undefined by default.
    - Returns: (Array<Array, ...>)
- convertDataframeToObject() - Converts a dataframe to an object.
    - arg0_dataframe: (Array<Array, ...>) - The dataframe to convert to an object.
    - Returns: (Object)
- convertObjectTODataframe() - Converts a given object to a dataframe.
    - arg0_dataframe_obj: (Object) - The object to convert into a dataframe.
    - Returns: (Array<Array, ...>)
- getColumns() - Fetches the number of columns in a dataframe.
    - arg0_dataframe: (Array<Array, …>) - The dataframe to pass to the function.
    - Returns: (Number)
- getDimensions() - Returns the number of columns and rows.
    - arg0_dataframe: (Array<Array, …>) - The dataframe to pass to the function.
    - Returns: (Array<Number, Number>)
- getRows() - Fetches the number of rows in a dataframe.
    - arg0_dataframe: (Array<Array, …>) - The dataframe to pass to the function.
    - Returns: (Number)
- hasHeader() - Checks whether a dataframe has a ‘true’ header.
    - arg0_dataframe: (Array<Array, …>) - The dataframe to pass to the function.
    - Returns: (Boolean)
- mergeDataframes() - Merges two dataframes; with the second dataframe's columns being appended to the first dataframe post-operation. Mathematical operations can be applied here as a system of equations. Dataframes may have different dimensions, non-corresponding values are assumed to be zero or undefined.

Dataframes are a 2D array, typically with a header row.

- arg0_dataframe: (Array<Array, ...>) - The 1st dataframe to pass to the function.
- arg1_dataframe: (Array<Array, ...>) - The 2nd dataframe to pass to the function.
- arg2_options: (Object)
    - equation: (String) - The string literal to use as an equation (e.g. 'i + x*5'). If no equal sign is provided, this applies to every cell, regardless of column. Equations are split by semicolons.

As an example, x$D = i$B, replaces the D column of the 2nd dataframe with the B column of the 1st.

- 'i' represents the corresponding element of the first dataframe,
    - 'i$Column' represents the selection of a 1st dataframe column named 'Column'.
- 'x' represents the corresponding element of the second dataframe.
    - 'x$Column' represents the selection of a 2nd dataframe column named 'Column'.

- Returns: (Array<Array, …>)
- operateDataframes() - Operates on two dataframes by applying an equation string.
    - arg0_dataframe: (Array<Array, ...>) - The 1st dataframe to operate on as i
    - arg1_dataframe: (Array<Array, ...>) - The 2nd dataframe to operate on as x
    - arg2_options: (Object)
    - equation: (String) - The string literal to use as an equation (e.g. 'i + x*5'). If no equal sign is provided, this applies to every cell, regardless of column. Equations are split by semicolons.

As an example, x$D = i$B, replaces the D column of the 2nd dataframe with the B column of the 1st.

- 'i' represents the corresponding element of the first dataframe,
    - 'i$Column' represents the selection of a 1st dataframe column named 'Column'.
- 'x' represents the corresponding element of the second dataframe.
    - 'x$Column' represents the selection of a 2nd dataframe column named 'Column'.
- return_safe_number: (Boolean) - Optional. Whether to use returnSafeNumber(). True by default.

- Returns: (Object)
    - dataframe: (Array<Array, ...>) - The result of the 1st dataframe.
    - ot_dataframe: (Array<Array, ...>) - The result of the 2nd dataframe.

- setHeader() - Sets the upper header variables.
    - arg0_dataframe: (Array<Array, ...>) - The dataframe to pass to the function.
    - arg1_header_array: (Array<String, …>) - The names of variables to set on the 0th row.
    - Returns: (Array<Array, …>)
- selectColumn() - Selects a 2D array column (by header name).
    - arg0_dataframe: (Array<Array, ...>) - The dataframe to pass to the function.
    - arg1_column_name: (String) - The name of the variable/column to select.
    - arg2_options: (Object)
        - return_index: (Boolean) - Optional. Whether to return an index. False by default.
    - Returns: (Array)
- selectRow() - Selects a 2D array row (by index).
    - arg0_dataframe: (Array<Array, ...>) - The dataframe to pass to the function.
    - arg1_row_index: (Number) - The row index to pass to the function.
    - arg2_options: (Object)
        - exclude_header: (Boolean) - Optional. Whether to exclude the header. False by default.
    - Returns: (Array)
- setColumn() - Sets a 2D array column.
    - arg0_dataframe: (Array<Array, ...>) - The dataframe to pass to the function.
    - arg1_column_name: (String) - The name of the variable/column to set.
    - arg2_values: (Array) - The list of values to set for this column.
    - Returns: (Array)
- setRow() - Sets a 2D array row.
    - arg0_dataframe: (Array<Array, ...>) - The dataframe to pass to the function.
    - arg1_row_index: (Number) - The row index to pass to the function.
    - arg2_valkues: (Array) - The list of values to set for this row.
    - Returns: (Array)
- Maths.
- absoluteValueArray() - Performs an absolute value operation on every valid element in an array, recursively.
    - arg0_array: (Array) - The array to pass to the function.
    - Returns: (Array)
- absoluteValueArrays() - Absolute value the distance between two arrays, recursively.
    - arg0_array: (Array) - The array to perform absolute distances on.
    - arg1_array: (Array) - The second array with which to compare distances.
    - arg2_options: (Object)
        - recursive: (Boolean) - Optional. Whether the operation is recursive. True by default.
    - Returns: (Array)
- addArray() - Performs an addition operation on every valid element in an array, recursively.
    - arg0_array: (Array) - The array to pass to the function.
    - Returns: (Array)
- addArrays() - Adds two arrays together recursively.
    - arg0_array: (Array) - The first array to add to.
    - arg1_array: (Array) - The second array to add with.
    - arg2_options: (Object)
        - recursive: (Boolean) - Optional. Whether the operation is recursive. True by default.
    - Returns: (Array)
- addMatrices() - Adds 2 matrices represented as 2D arrays together.
    - arg0_matrix: (Array<Array, …>) - The 1st matrix to add.
    - arg1_matrix: (Array<Array, …>) - The 2nd matrix to add.
    - Returns: (Array<Array, …>)
- appendArrays() - Concatenates two arrays and returns it.
    - arg0_array: (Array) - The base array.
    - arg1_array: (Array) - The second array to append to the first.
    - Returns: (Array)
- arrayIsOfType() - Whether an array is purely of a given type.
    - arg0_array: (Array) - The array to pass to the function.
    - arg1_type: (String) - The typeof to compare to.
    - Returns: (Array)
- augmentMatrices() - Combine the columns of two matrices to form a new matrix.
    - arg0_matrix: (Array<Array, …>) - The 1st matrix to augment on.
    - arg1_matrix: (Array<Array, …>) - The 2nd matrix to augment with.
    - Returns: (Array<Array, …>)
- choleskyDecompositionMatrix() - Performs a Cholesky decomposition on a matrix.
    - arg0_matrix: (Array<Array, …>) - The matrix to pass to the function.
    - Returns: (Array<Array, …>)
- divideArray() - Performs a division operation on every valid element in an array, recursively.
    - arg0_array: (Array) - The array to pass to the function.
    - Returns: (Array)
- divideArrays() - Divides two arrays together recursively.
    - arg0_array: (Array) - The base array.
    - arg1_array: (Array) - The divisor array.
    - arg2_options: (Object)
        - recursive: (Boolean) - Optional. Whether the operation is recursive. True by default.
    - Returns: (Array)
- exponentiateArray() - Performs an exponent operation on every valid element in an array, recursively.
    - arg0_array: (Array) - The array to pass to the function.
    - Returns: (Array)
- exponentiateArrays() - Exponentiates two arrays, recursively.
    - arg0_array: (Array) - The base array.
    - arg1_array: (Array) - The power array.
    - arg2_options: (Object)
        - recursive: (Boolean) - Optional. Whether the operation is recursive. True by default.
    - Returns: (Array)
- gaussEliminationMatrix() - Performs Gauss elimination on a matrix.
    - arg0_matrix: (Array<Array, …>) - The matrix to pass to the function.
    - Returns: (Array<Array, …>)
- gaussJacobiMatrix() - Performs Gauss-Jacobi on a matrix.
    - arg0_matrix: (Array<Array, …>) - The matrix to pass to the function.
    - arg1_tolerance: (Number) - Optional. The level of accuracy to tolerate. 1e-6 by default.
    - arg2_max_iterations: (Number) - Optional. The number of max iterations. 1000 by default.
    - Returns: (Array<Array, …>)
- gaussJordanMatrix() - Performs Gauss-Jordan on a matrix.
    - arg0_matrix: (Array<Array, …>) - The matrix to pass to the function.
    - Returns: (Array<Array, …>)
- gaussSeidelMatrix() - Performs Gauss-Seidel on a matrix.
    - arg0_matrix: (Array<Array, …>) - The matrix to pass to the function.
    - arg1_tolerance: (Number) - Optional. The level of accuracy to tolerate. 1e-6 by default.
    - arg2_max_iterations: (Number) - Optional. The number of max iterations. 1000 by default.
    - Returns: (Array<Array, …>)
- getCofactor() - Fetches the cofactor in a matrix.
    - arg0_matrix: (Array<Array, …>) - The matrix to pass to the function.
    - arg1_row: (Number) - The row to calculate cofactor for.
    - arg2_column: (Number) - The column to calculate cofactor for.
    - Returns: (Array<Array, …>)
- getMatrixDeterminant() - Calculates the matrix determinant.
    - arg0_matrix: (Array<Array, …>) - The matrix to pass to the function.
    - Returns: (Number)
- householderTransformationMatrix() - Performs Householder transformation on a matrix.
    - arg0_matrix: (Array<Array, …>) - The matrix to pass to the function.
    - Returns: (Array<Array, …>)
- inverseMatrix() - Inverts a matrix.
    - arg0_matrix: (Array<Array, …>) - The matrix to pass to the function.
    - Returns: (Array<Array, …>)
- LUDecompositionMatrix() - Performs LUD decomposition on a matrix.
    - arg0_matrix: (Array<Array, …>) - The matrix to pass to the function.
    - Returns: (Object)
        - L: (Array<Array, …>)
        - U: (Array<Array, …>)
- multiplyArray() - Performs a multiplication operation on every valid element in an array, recursively.
    - arg0_array: (Array) - The array to pass to the function.
    - Returns: (Array)
- multiplyArrays() - Multiplies two arrays recursively.
    - arg0_matrix: (Array<Number, …>) - The base array.
    - arg1_matrix: (Array<Number, …>) - The array to multiply by.
    - arg2_options: (Object)
        - recursive: (Boolean) - Optional. Whether the operation is recursive. True by default.
    - Returns: (Array)
- multiplyMatrices() - Multiplies two matrices.
    - arg0_matrix: (Array<Array, …>) - The 1st matrix to input.
    - arg1_matrix: (Array<Array, …>) - The 2nd matrix to input.
    - Returns: (Array<Array, …>)
- operateArray() - Applies a mathematical equation to every element of an array, recursively.
    - arg0_array: (Array) - The array to pass to operateArray()
    - arg1_equation: (String) - The string literal to use as an equation.
        - ‘n’ represents the current array element.
    - Returns: (Array)
- operateArrays() - Performs an operation when merging two arrays together, recursively.
    - arg0_array: (Array) - The 1st array to pass to operateArrays()
    - arg1_array: (Array) - The 2nd array to pass to operateArrays()
    - arg2_equation: (String) - The string literal to use as an equation.
        - ‘i’ represents the corresponding element of the 1st array,
        - ‘x’ represents the corresponding element of the 2nd array
    - arg3_options: (Object)
        - recursive: (Boolean) - Optional. Whether the operation is recursive. True by default.
    - Returns: (Array)
- QRDecompositionMatrix() - Performs QR decomposition on a matrix.
    - arg0_matrix: (Array<Array, …>) - The matrix to pass to the function.
    - Returns: (Object)
        - Q: (Array<Array, …>)
        - R: (Array<Array, …>)
- QRLeastSquaredMatrix() - Performs QR least squared on two matrices.
    - arg0_matrix: (Array<Array, …>) - The 1st matrix to pass to the function.
    - arg1_matrix: (Array<Array, …>) - The 2nd matrix to pass to the function.
    - Returns: (Array)
- rootArray() - Roots an array recursively.
    - arg0_array: (Array) - The array to pass to the function.
    - Returns: (Array)
- rootArrays() - Roots two arrays recursively.
    - arg0_array: (Array) - The 1st array to pass to the function.
    - arg1_array: (Array) - The 2nd array to pass to the function.
    - arg2_options: (Object)
        - recursive: (Boolean) - Optional. Whether the operation is recursive. True by default.
    - Returns: (Array)
- SORMatrix() - Performs SOR inversion and multiplication matrices.
    - arg0_matrix: (Array<Array, …>) - The 1st matrix to pass to the function.
    - arg1_matrix: (Array<Array, …>) - The 2nd matrix to pass to the function.
    - Returns: (Array)
- subtractArray() - Subtracts from an array recursively.
    - arg0_array: (Array) - The array to pass to the function.
    - Returns: (Array)
- subtractArrays() - Subtract two arrays recursively.
    - arg0_array: (Array) - The 1st base array.
    - arg1_array: (Array) - The 2nd array, containing what to subtract from the 1st.
    - options: (Object)
        - recursive: (Boolean) - Optional. Whether the operation is recursive. True by default.
    - Returns: (Array)
- subtractMatrices() - Subtracts one matrix from another.
    - arg0_matrix: (Array<Array, …>) - The 1st base matrix to subtract from.
    - arg1_matrix: (Array<Array, …>) - The 2nd matrix to subtract with.
    - Returns: (Array<Array, …>)
- transposeMatrix() - Transposes a matrix.
    - arg0_matrix: (Array<Array, …>) - The matrix to transpose.
    - Returns: (Array<Array, …>)
- Search/Sort.
- getArrayElements() - Fetches array elements that fulfil the following criteria and returns it as an array. If an element being compared to is not of a valid type to the comparison (e.g. .greater option on an object), the element will be returned as-is in the new array.
    - arg0_array: (Array) - The array to pass to the function.
    - arg1_options: (Object)
        - cardinality: (Number) - Optional. Elements in returned array must have a length of this.
        - cardinality_greater: (Number) - Optional. Elements in returned array must have a length greater than this number.
        - cardinality_geq: (Number) - Optional. Elements in returned array must have a length greater to or equal to this number.
        - cardinality_leq: (Number) - Optional. Elements in returned array must have a length less than this number.
        - eq: (Number) - Optional. Elements in returned array are equal to this number.
        - greater: (Number) - Optional. Elements in returned array must be greater than this number.
        - geq: (Number) - Optional. Elements in returned array must be greater to or equal than this number.
        - indexes: (Array<Number>) - Optional. Fetches the following indexes.
        - in_array/in_set: (Array) - Optional. Fetches elements that are also included in this set.
        - less: (Number) - Optional. Elements in returned array must be less than this number.
        - leq: (Number) - Optional. Elements in returned array must be less than or equal to this number.
        - not_indexes: (Array<Number>) - Optional. Compares only indexes not mentioned in this array.
        - range: (Array<Number, Number>) - Optional. Returns array values within this range.
        - not_range: (Array<Number, Number>) - Optional. Returns array values outside this range.
        - recursive: (Boolean) - Optional. Whether the array is recursive. False by default.
    - Returns: (Array)
- getArraySubstring() - Recursively fetches the element of an array containing a substring.
    - arg0_array: (Array) - The array to pass to the function.
    - arg1_string: (String) - The substring to search array elements for.
    - arg2_options: (Object)
        - recursive: (Boolean) - Optional. Where to traverse recursively. True by default.
    - Returns: (Array<String, …>)
- indexesOf() - Returns the indexes of an array of strings.
    - arg0_array: (Array) - The array to pass to the function.
    - arg1_index_array: (Array<Number, …>) - The array of indices to fetch from the array.
    - arg2_options: (Object)
        - return_values: (Boolean) - Optional. Whether to return array values instead of indices. False by default.
    - Returns: (Array)
- sortArray() - Sorts an array. Can be based on subkey values (recursive, e.g. 'population.size').
    - arg0_array: (Array) - The array to pass to the function.
    - arg1_options: (Object)
        - sort_key: (String) - Optional. The sort subkey to specify. Empty (indicating the base index) by default.
        - mode: (String) - Optional. "alphabetical"/"ascending"/"descending". 'descending' by default.
        - recursive: (Boolean) - Optional. Whether the sort is recursive. False by default.
    - Returns: (Array)

BrowserUI.

- Basic HTML.
    - isDescendant() - Checks whether an element belongs to a specific parent.
        - arg0_parent_el: (HTMLElement) - The HTML element of the parent to check.
        - arg1_child_el: (HTMLElement) - The HTML element of the child to check.
        - Returns: (Boolean)
    - objectToAttributes() - Converts a given object to a bunch of attributes in terms of key/value pairs.
        - arg0_input_object: (Object) - The object to pass to the function.
        - Returns: (String)
    - onRangeChange() - Detects when a range is changed.
        - arg0_range_el: (HTMLElement) - The HTML element of the range.
        - arg1_listener: (Function) - The function to execute on change.
    - pointIsInCircle() - Checks if a point is in a circle.
        - arg0_circle_x: (Number) - The x position of the circle.
        - arg1_circle_y: (Number) - The y position of the circle.
        - arg2_point_x: (Number) - The x position to check.
        - arg3_point_y: (Number) - The y position to check.
        - arg4_radius: (Number) - The radius of the circle.
- Returns: (Boolean)
- Context Menus.
    - createContextMenu() - Creates a context menu within the DOM.
        - arg0_options: (Object)
            - anchor: (String) - The query selector to pin a context menu to.
            - class: (String) - The class prefix to prepend.
            - id: (String) - The ID of the context menu.
            - name: (String) - Optional. Title of the context menu. Undefined; will not display by default.
            - maximum_height: (String) - Optional. The height after which a scrollbar should appear in CSS units.
            - maximum_width: (String) - Optional. Maximum width in CSS units.
            - <input_key>: (Object)  
                type: (String) - The type of HTML input to grab.
                - biuf
                - rich_text/wysiwyg
                - button
                - checkbox
                - color/colour
                - datalist
                - date
                - date_length
                - email
                - file
                - hidden
                - html
                - image
                - number
                - password
                - radio
                - range
                - reset
                - search_select
                - select
                - submit
                - tel/telephone
                - text
                - time
                - url/URL
            - height: (Number) - Optional. The height of this element.
            - icon: (String) - Optional. The path to the display icon image.
            - name: (String) - Optional. The HTML text of the button to display.
            - onclick: (String) - Optional. The JS code to execute on button click.
            - tooltip: (String) - Optional. THe HTML tooltip a user can see by hovering over this input.
            - width: (Number) - Optional. The width of this element.
            - x: (Number) - Optional. The X position of the element in a grid. 0 by default.
            - y: (Number) - Optional. The Y position of the element in a grid. n + 1 by default, where n = last row.
    - createInput() - Returns a string representing the HTML input element.
        - arg0_options: (Object)
            - id: (String) - The ID to associate this input with.
            - type: (String) - The input type to return the HTML of. ‘biuf’/’rich_text’/’wysiwyg’/’button’/’checkbox’/’color’/’colour’/’datalist’/’date’/’date_length’/’email’/’file'/’html’/'hidden'/'image'/'number'/'password'/'radio'/'range'/'reset'/'search_select'/'select'/'submit'/'tel'/'text'/'time'/'url'
            - icon: (String) - Optional. The path to the display icon image.
            - name: (String) - Optional. The HTML string of the button to display.
            - onclick: (String) - Optional. The onclick/confirm attribute of the button.
            - tooltip: (String) - Optional. The HTML tooltip a user can see by hovering over this input.
            - attributes: (Object) - Optional.
                - <attribute_name>: <value> - The attribute to pass to the focus element.
            - options: (Object) - Optional.
                - <option_id>: <value> - The datalist option ID to pass to the focus element.

//Individual input type options.

//’biuf’

- default: (String) - Optional. The default string to input as a placeholder value. ‘Name’ by default.

//’date’

- default_date: (Object) - The date to set defaults to if applicable.

//’html’

- innerHTML: (String) - The HTML to append to this cell.

Internal UI Helper Functions.

- addParagraphTag()
    - arg0_e (Event, KeyPress)
- childOf()
    - arg0_child_el (HTMLElement)
    - arg1_parent_el (HTMLElement)
- execCodeAction()
    - arg0_button_el (HTMLElement)
    - arg1_editor_el (HTMLElement)
    - arg2_visual_view_el (HTMLElement)
    - arg3_html_view_el (HTMLElement)
- execDefaultAction()
    - arg0_action (String)
- execLinkAction()
    - arg0_modal_el (HTMLElement)
- handleBIUF()
    - arg0_e (HTMLElement)
- handleColourWheel()
    - arg0_parent_el_id (String)
- initBIUFToolbar()
    - arg0_parent_el_id (String)
- initWYSIWYG()
    - arg0_parent_el_id (String)
- parentTagActive()
    - arg0_el (HTMLElement)
- pasteEvent()
    - arg0_e (Event, Paste)
- restoreSelection()
    - arg0_saved_selection (Object)
- saveSelection()
- selectionChange()
    - arg0_e (Event, SelectionChange)
    - arg1_buttons (Array<HTMLElement, …>)
    - arg2_editor (HTMLElement)
- setColourWheelCursor()
    - arg0_parent_el_id (String)
    - arg1_colour (Array<Number, Number, Number>)
    - arg2_do_not_change (Boolean)
- updateBrightnessOpacityHeaders()
    - arg0_parent_el_id (String)

Colours.

Basic.

- componentToHex() - Fetches the hex of a single component.
    - c: (Number) - The individual r/g/b component to pass to the function.
    - Returns: (String)
- deltaE() - Calculates the deltaE between two RGB variables.
    - rgbA: (Array<Number, Number, Number>) - The 1st RGB code to pass.
    - rgbB: (Array<Number, Number, Number>) - The 2nd RGB code to pass.
    - Returns: (Number)
- generateRandomColour() - Generates a random RGB colour.
    - Returns: (Array<Number, Number, Number>)
- getColourDistance() - Fetches the absolute colour distance between two colours.
    - arg0_rgb: (Array<Number, Number, Number>) - The 1st RGB code to pass.
    - arg1_rgb: (Array<Number, Number, Number>) - The 2nd RGB code to pass
    - Returns: (Number).
- hexToRGB() - Converts a hex to RGB.
    - hex: (String) - The hex code to pass to the function.
    - Returns: (Array<Number, Number, Number>)
- RGBToHex() - Converts an RGB value to hex.
    - r: (Number) - The r value.
    - g: (Number) - The g value.
    - b: (Number) - The b value.
    - Returns: (String)
- RGB2Lab() - Converts an RGB value to lab distance.
    - rgb: (Array<Number, Number, Number>)
    - Returns: (Array<Number, Number, Number>)

Date.

DATATYPES.

Date.

- year: (Number) - The Gregorian year of the current date.
- month: (Number) - The month of the current date (1-12).
- day: (Number) - The day of the current date (1-31).
- minute: (Number) - The minute of the current date (0-59).

History Frame.

- …
- options: (Object)
    - history: (Object)
        - <keyframe_id>: (Object)
            - coords: (Array<Array<Array<Number, Number>, …>>)

Basic.

- daysInMonths() - Fetches the number of days already passed since the beginning of the year.
    - arg0_date_object: (Object, Date) - The date object/timestam[p to pass to the function.
    - Returns: (Number)
- getDateString() - Returns a formatted string from a date object.
    - arg0_date_object: (Object, Date) - The date object to pass to the function.
    - Returns: (String)
- getStandardYear() - Returns the standard numeric Gregorian year from a date object/timestamp [WIP]
    - arg0_date_object: (Object, Date) - The date object/timestamp to pass to the function.
    - Returns: (Number)
- getTimestamp() - Returns the amount of minutes in a date.
    - arg0_date_object: (Object, Date) - The date object/timestamp to pass to the function.
    - Returns: (String)
- initDateFramework() - Called to initialise date variables in the global scope.
- isLeapYear() - Whether the specified year is a leap year.
    - arg0_year: (Number) - The year to check for.
    - arg1_hanseceltican_standard: (Boolean) - Optional. Whether to account for Roman-errored leap years. False by default.
    - Returns: (Boolean)
- leapYearsBefore() - Fetches the number of leap years before a given year.
    - arg0_year: (Number) - The year to check for.
    - Returns: (Number)
- leapYearsBetween() - Fetches the number of leap years between two years.
    - arg0_start_year: (Number) - The beginning year.
    - arg1_end_year: (Number) - The ending year.
    - Returns: (Number)
- monthsFromDays() - Fetches the number of months from days, within the context of a date object.
    - arg0_date_object: (Object, Date) - The date object/timestamp to pass to the function.
    - Returns: (Number)
- parseTimestamp() - Parses a timestamp into a date object.
    - arg0_timestamp: (String) - The timestamp to parse.
    - Returns: (Object, Date)
- parseYears() - Returns days/months/years as an object depending on the year amount.
    - arg0_number: (Number) - The decimal number of years elapsed.
    - arg1_current_year: (Number) - Optional. The current year. Undefined by default.
    - Returns: (Object)
        - hour: (Number)
        - day: (Number)
        - month: (Number)
        - year: (Number)
- timestampToInt() - Converts a timestamp to its integer position [in minutes from AD1], assuming the Hanseceltican standard.
    - arg0_timestamp: (String) - The string of the timestamp to parse to an int.
    - Returns: (Number)

Conversion.

- convertTimestamp() - Converts a timestamp into a given date object.

Format.

History.

- adjustObjectHistory() - Adjusts an object history keyframe to that of another date/timestamp.
    - arg0_object: (Object) - The object being referenced.
    - arg1_date_object: (Object, Date) - The keyframe to move.
    - arg2_date_object: (Object, Date) - The date to move the keyframe to.
    - Returns: (Object)
- checkObjectHisotry() - Checks whether an object has a given property defined somewhere in its history.
    - arg0_object: (Object) - The object being referenced.
    - arg1_date_object: (Object, Date) - The date being referenced.
    - arg2_conditional_function: (Function) - The conditional function to check for in all history entries.
    - Returns: (Boolean/Variable)
- createObjectHistory() - Creates an object history keyframe at the current date.
    - arg0_object: (Object) - The object being referenced.
    - arg1_date_object: (Object, Date) - The date to create a history keyframe at.
    - arg2_options: (Object) - Optional. The actual .options styling date being carried at this frame. Undefined by default.
    - arg3_coords: (Array<Array<Number, Number>, ..>) - The coordinates to input for this frame. Defaults to old coordinates if available.
    - Returns: (Object)
- deleteObjectHistory() - Deletes an object history keyframe.
    - arg0_object: (Object) - The object being referenced.
    - arg1_date_object: (Object, Date) - The date to delete a history keyframe at.
    - Returns: (Object)/undefined if all history entries deleted.
- getFirstHistoryFrame() - Returns the first history frame of an object.
    - arg0_object: (Object) - The object being referenced.
    - Returns: (Object)
- getHistoryCoords() - Fetches the coords of an object at a certain date.
    - arg0_object: (Object) - The object being referenced.
    - arg1_date_object: (Object, Date) - The date being referenced.
    - Returns: (Array<Array<Number, Number>, …>)
- getHistoryFrame() - Returns the history frame of an entity.
    - arg0_object: (Object) - The object being referenced.
    - arg1_date_object: (Object, Date) - The date being referenced.
    - Returns: (Object)
- getLastCoords() - Fetches the last valid .coords field from an object.
    - arg0_object: (Object) - The object being referenced.
    - arg1_history_frame: (Object) - The history frame object being referenced.
    - Returns: (Array<Array<Number, Number>, …>)
- getLastIdenticalCoords() - Fetches the last identical coords prior to the current frame.
    - arg0_object: (Object) - The object being referenced.
    - arg1_history_frame: (Object) - The history frame object being referenced.
    - Returns: (Array<Array<Number, Number>, …>)
- getObjectHistory() - Returns a history frame for the specified date.
    - arg0_object: (Object) - The object being referenced.
    - arg1_date_object: (Object, Date) - The date being referenced.
    - arg2_options: (Object)
        - return_key: (Boolean) - Optional. Whether to return the key instead of the object. False by default.
    - Returns: (Object)

Files.

Basic.

- getAllFiles() - Fetches an array of all files in a given folder.
    - arg0_folder: (String) - The folder path.
    - Returns: (Array<String, ...>)
- importFile() - Imports a Node.js file.
    - arg0_require_obj: (Streing) - The file path to import.
- loadDirectory() - Loads the files in an immediate directory in chronological order.
    - arg0_folder: (String) - The directory to load.
    - arg1_options: (Object)
        - reverse: (Boolean) - Optional. Whether to reverse it or not. True by default.
- loadConfig() - Loads default config.
- loadFile() - Loads a file, similar to import but with eval.
    - arg0_file: (String) - The file path to load.

Log.

Basic.

- log.debug() - Logs debugging to the console.
    - options: (...)
        - flag: (Boolean) - Optional. Only outputs a debug log if this variable is true. global.debug by default.
- log.error() - Produces a log with error formatting.
- log.info() - Produces a log with info formatting.
- log.warn() - Produces a log with warning formatting.

Numbers.

DATATYPES.

Range.

Array<Number, Number>

Basic.

- alphabetiseNumber() - Alphabetises a number based on a0-j9.
    - arg0_string: (String)
    - Returns: (String)
- arabicise() - Arabicises a Roman numeral string.
    - arg0_string: (String) - The number to arabicise.
    - Returns: (Number)
- degreesToRadians() - Converts degrees to radians.
    - arg0_degrees: (Number) - The number of degrees.
    - Returns: (Number)
- deordinalise() - Deordinalises a string.
    - arg0_string: (String) - The string to deordinalise.
    - Returns: (String)
- exp() - Exponentiates a number.
    - arg0_number: (String) - The base to exponentiate.
    - arg1_number: (String) - The power to exponentiate by.
    - Returns: (Number)
- factorial() - Calculates the factorial of a number.
    - arg0_number: (Number) - The number to calculate for.
    - Returns: (Number)
- generateRandomID() - Generates a random ID.
    - arg0_object: (Object) - The object relative to which the ID is being generated; making sure to avoid duplicate IDs.
    - Returns: (Number)
- log() - Calculates log/natural log.
    - arg0_x: (Number) - The x to calculate the log for.
    - arg1_y: (Number) - The y to calculate the log for.
    - Returns: (Number)
- logFactorial() - Calculates the log of a factorial.
    - arg0_number: (Number) - The number to pass to the function.
    - Returns: (Number)
- max() - Fetches the maximum value inside a variable.
    - arg0_variable: (Array<Number, …>) - The array to calculate the max. val for.
    - Returns: (Number)
- min() - Fetches the minimum value inside a variable.
    - arg0_variable: (Array<Number, …>) - The array to calculate the max. val for.
    - Returns: (Number)
- numeriseAlphabet() - Numerises an alphabetical string, assuming a0-j9.
    - arg0_string: (String) - The string to numerise.
    - Returns: (String)
- oldDeordinalise() - Strip ordinals from a string and convert it to a number (e.g. ‘2nd’ = 2).
    - arg0_string: (String) - The string to deordinalise, using the old list specification pattern.
    - Returns: (String)
- ordinalise() - Ordinalises a number.
    - arg0_number: (Number) - The input number to pass.
    - Returns: (String)
- radiansToDegrees() - Converts radians to degrees.
    - arg0_radians: (Number) - The number of radians to pass.
    - Returns: (Number)
- randomNumber() - Generates a random number between min and max.
    - arg0_min: (Number) - The min range.
    - arg1_max: (Number) - The max range.
    - arg2_do_not_round: (Boolean) - Optional. Whether to round. False by default.
    - Returns: (Number)
- returnSafeNumber() - Returns a safe number.
    - arg0_operation: (Number) - The variable, preferably a number to check for.
    - arg1_default: (Number) - Optional. The default to pass. 0 by default.
    - Returns: (Number)
- romanise() - Romanises an arabic number and returns it as a string.
    - arg0_number: (Number) - The number to romanise.
    - Returns: (String)
- root() - Nth roots a number.
    - arg0_number: (Number) - The number to root.
    - arg1_root: (Number) - The root.
    - Returns: (Number)
- round() - Rounds a number to n places.
    - arg0_number: (Number) - The number to round.
    - arg1_rounding_places: (Number) - The number of places to round by.
    - Returns: (Number)
- sigfig() - Rounds a number to n significant figures.
    - arg0_number: (Number) - The number to round to significant figures.
    - arg1_sigfigs: (Number) - The number to sigfigs to round by.
    - Returns: (Number)
- splitNumber() - Splits a number randomly into multiple parts.
    - arg0_number: (Number) - The number to split.
    - arg1_parts: (Number) - How many parts to split it into.
    - Returns: (Array<Number, …>)
- splitNumberParts() - Internal helper function for splitNumber()
- unzero() - Makes sure to zero a figure. Useful to avoid dividing by 0. 1 by default.
    - arg0_number: (Number) - The number to zero.
    - arg1_default: (Number) - Optional. The default to set it to. 1 by default.
    - Returns: (Number)

Ranges.

- addRange()/modifyRange() - Adds a number to a range.
    - arg0_range: (Array<Number, Number>) - The range to add to.
    - arg1_number: (Number) - The number to add to the range.
    - Returns: (Array<Number, Number>)
- addRanges() - Adds a range by another.
    - arg0_range: (Array<Number, Number>) - The 1st range.
    - arg1_range: (Array<Number, Number>) - The 2nd range.
    - Returns: (Array<Number, Number>)
- divideRange() - Divides a range by another.
    - arg0_range: (Array<Number, Number>) - The range to pass.
    - arg1_number: (Number) - The number to divide by.
    - Returns: (Array<Number, Number>)
- divideRanges() - Divides a range by another.
    - arg0_range: (Array<Number, Number>) - The 1st range to pass.
    - arg1_range: (Array<Number, Number>) - The 2nd range to pass.
    - Returns: (Array<Number, Number>)
- exponentiateRange() - Exponentiates a range by another.
    - arg0_range: (Array<Number, Number>) - The 1st range to pass.
    - arg1_range: (Array<Number, Number>) - The 2nd range to pass.
    - Returns: (Array<Number, Number>)
- getMidpoint() - Fetches the midpoint of a range.
    - arg0_range: (Array<Number, Number>) - The range to pass.
    - Returns: (Number)
- getRange() - Gets a range from a given variable.
    - arg0_range: (Variable) - The variable to cast to a range.
    - Returns: (Array<Number, Number>)
- multiplyRange() - Multiplies a range by a number.
    - arg0_range: (Array<Number, Number>) - The range to pass.
    - arg1_number: (Number) - The number to pass to the function.
    - Returns: (Array<Number, Number>)
- multiplyRanges() - Multiplies a range by another.
    - arg0_range: (Array<Number, Number>) - The 1st range to pass.
    - arg1_range: (Array<Number, Number>) - The 2nd range to pass.
    - Returns: (Array<Number, Number>)
- rootRange() - Roots a range by a given number.
    - arg0_range: (Array<Number, Number>) - The range to pass.
    - arg1_root: (Number) - The number to root a range by.
    - Returns: (Array<Number, Number>)
- rootRanges() - Roots ranges by one another.
    - arg0_range: (Array<Number, Number>) - The 1st range to pass.
    - arg1_range: (Array<Number, Number>) - The 2nd range to pass.
    - Returns: (Array<Number, Number>)
- subtractRange() - Subtracts a number from a range.
    - arg0_range: (Array<Number, Number>) - The range to pass.
    - Returns: (Array<Number, Number>)
- subtractRanges() - Subtracts a range from another.
    - arg0_range: (Array<Number, Number>) - The 1st range to pass.
    - arg1_range: (Array<Number, Number>) - The 2nd range to pass.
    - Returns: (Array<Number, Number>)

Objects.

Basic.

- cleanObject() - Removes both zero values and undefined/null values from an object by default.
    - arg0_object: (Object) - The object to pass.
    - arg1_options: (Object)
        - remove_falsey: (Boolean) - Optional. Whether to remove falsey values. False by default.
        - remove_zeroes: (Boolean) - Optional. Whether to remove zero values from the cleaned object. False by default.
    - Returns: (Object)
- flattenObject() - Moves all keys into the 1st nesting.
    - arg0_object: (Object) - The object to pass.
    - Returns: (Object)
- getDepth() - Returns object depth as a number.
    - arg0_object: (Object) - The object to fetch depth for.
    - arg1_depth: (Number) - Optimisation parameter used as an internal helper.
    - Returns: (Number)
- getObjectKey() - Fetches object value from a string (e.g. ‘test.one.two’).
    - arg0_object: (Object) - The object to fetch the key from.
    - arg1_key: (String) - The string of the key to fetch from the object.
    - Returns: (Variable)
- getObjectList() - Returns object as an array list.
    - arg0_object_list: (Object) - The objectified list to pass.
    - Returns: (Array)
- getSubobject() - Fetches a subobject.
    - arg0_object: (Object) - The object to pass.
    - arg1_key: (String) - The key to recursively look for to fetch the local subobject.
    - arg2_restrict_search: (Boolean) - Whether to restrict the search to the 1st layer.
    - Returns: (Object)
- getSubobjectKeys() - Fetches the keys in a subobject that match the given criteria.
    - arg0_object: (Object) - The object to pass to the function.
    - arg1_options: (Object)
        - exclude_keys: (Array<String, …>) - Optional. A list of keys to exclude. [] by default.
        - include_objects: (Boolean) - Optional. Whether to include. False by default.
        - only_objects: (Boolean) - Optional. Whether to include. False by default.
    - Returns: (Array<String, …>)
- mergeObjects() - Merges two objects together.
    - arg0_object: (Object) - The 1st object to merge into.
    - arg1_object: (Object) - The 2nd object to concatenate/add.
    - arg2_options: (Object)
        - must_have_difference: (Boolean) - Optional. Whether values must be different before they can be added/subtracted from one another. False by default.
        - overwrite: (Boolean) - Optional. Whether to overwrite objects when merging. False by default.
        - recursive: (Boolean) - Optional. Whether merging is recursive. True by default.
    - Returns: (Object)
- removeZeroes() - Removes zero values from an object.
    - arg0_object: (Object) - The object to pass to the function.
    - Returns: (Object)
- sortObject() - Sorts an object.
    - arg0_object: (Object) - The object to sort.
    - arg1_options: (Object)
        - type: (String) - Optional. The order to sort the object in. ‘ascending’/’descending’. ‘descending’ by default.

Maths.

- addObject() - Adds a value to an object, recursively.
    - arg0_object: (Object) - The object to pass.
    - arg1_value: (Number) - The value to add to each variable in the object.
    - Returns: (Object)
- addObjects() - Adds values between two objects, recursively.
    - arg0_object: (Object) - The 1st object to pass.
    - arg1_object: (Object) - The 2nd object to pass.
    - arg2_options: (Object)
        - recursive: (Boolean) - Optional. Whether the operation is recursive. True by default.
    - Returns: (Object)
        - object: (Object) - The modified version of the 1st object.
        - ot_object: (Object) - The modified version of the 2nd object.
- changeObjectRange() - Changes object ranges, non-recursively, for a given key.
    - arg0_object: (Object) - The object to pass.
    - arg1_key: (String) - The key corresponding to the range to modify.
    - arg2_min_max_argument: (String) - Optional. Either ‘minimum’/’maximum’. ‘both’ by default.
    - arg3_value: (Number) - The number to change these ranges by.
    - Returns: (Object)
- divideObject() - Divides an object by a value, recursively.
    - arg0_object: (Object) - The object to pass.
    - arg1_value: (Number) - The value to divide each variable in the object by.
    - Returns: (Object)
- divideObjects() - Divides two objects, recursively.
    - arg0_object: (Object) - The 1st object to pass.
    - arg1_object: (Object) - The 2nd object to pass.
    - arg2_options: (Object)
        - recursive: (Boolean) - Optional. Whether the operation is recursive. True by default.
    - Returns: (Object)
        - object: (Object) - The modified version of the 1st object.
        - ot_object: (Object) - The modified version of the 2nd object.
- getObjectMaximum() - Fetches the maximum value within an object.
    - arg0_object: (Object) - The object to pass.
    - arg1_options: (Object)
        - include_ranges: (Boolean) - Optional. Whether to include ranges. False by default.
        - recursive: (Boolean) - Optional. Whether the function is recursive. True by default.
    - Returns: (Number)
- getObjectMinimum() - Fetches the minimum value within an object.
    - arg0_object: (Object) - The object to pass.
    - arg1_options: (Object)
        - include_ranges: (Boolean) - Optional. Whether to include ranges. False by default.
        - recursive: (Boolean) - Optional. Whether the function is recursive. True by default.
    - Returns: (Number)
- getObjectSum() - Fetches the object sum, recursively.
    - arg0_object: (Object) - The object to pass.
    - arg1_options: (Object)
        - recursive: (Boolean) - Optional. Whether to sum recursively. True by default.
    - Returns: (Number)
- invertFractionObject() - Inverts a fraction object, fetching the reciprocal of percentage values.
    - arg0_object: (Object) - The object to pass.
    - Returns: (Object)
- modifyObjectRange() - Modifies ranges in an object recursively, by operating on objects.
    - arg0_object: (Object) - The object to pass.
    - arg1_value: (Number) - The value to modify ranges by.
    - arg2_options: (Object)
        - include_numbers: (Number) - Optional. Whether to include single numbers. True by default.
    - Returns: (Object)
- multiplyObject() - Multiplies an object by a value, recursively.
    - arg0_object: (Object) - The object to pass.
    - arg1_value: (Number) - The value to add to each variable in the object.
    - Returns: (Object)
- operateObject() - Performs an operation on a single object, recursively.
    - arg0_object: (Object) - The object to pass to operateObject().
    - arg1_equation: (String) - The string literal to use as an equation.
        - ‘n’ represents the corresponding element of the first object.
    - arg2_options: (Object)
        - log_errors: (Boolean) - Optional. Whether to log errors. Fale by default.
        - only_numbers: (Boolean) - Optional. Whether only numbers can be operated on. True by default
        - recursive: (Boolean) - Optional. Whether the operation is recursive. True by default.
    - Returns: (Object)
- operateObjects() - Performs an operation on two objects together, recursively.
    - arg0_object: (Object) - The 1st object to pass to operateObjects()
    - arg1_object: (Object) - The 2nd object to pass to operateObjects()
    - arg2_equation: (String) - The string literal to use as an equation (e.g. i = i + x).
        - 'i' represents the corresponding element of the first object,
        - 'x' represents the corresponding element of the second object, undefined values are represented as zero.
    - arg3_options: (Object)
        - log_errors: (Boolean) - Optional. Whether to log errors. False by default.
        - only_numbers: (Boolean) - Optional. Whether only numbers can be operated on. True by default.
        - recursive: (Boolean) - Optional. Whether the operation is recursive. True by default.
    - Returns: (Object)
        - object: (Object) - The modified version of the 1st object.
        - ot_object: (Object) - The modified version of the 2nd object.
- standardiseFraction() - Standardises the object to maximum = 1, with each other value being adjusted to a value.
    - arg0_object: (Object) - The object to pass.
    - Returns: (Object)
- standardisePercentage() - Standardises the object to a given total.
    - arg0_object: (Object) - THe object to pass.
    - arg1_total: (Number) - The total figure to adjust the object to.
    - arg2_round: (Boolean) - Whether to force rounding when standardising.
    - Returns: (Object)
- subtractObject() - Subtracts a value from an object, recursively.
    - arg0_object: (Object) - The object to pass.
    - arg1_value: (Number) - The value to add to each variable in the object.
    - Returns: (Object)
- subtractObjects() - Subtracts one object from another, recursively.
    - arg0_object: (Object) - The 1st object to pass.
    - arg1_object: (Object) - The 2nd object to pass.
    - arg2_options: (Object)
        - recursive: (Boolean) - Optional. Whether the operation is recursive. True by default.
    - Returns: (Object)
        - object: The modified version of the 1st object.
        - ot_object: The modified version of the 2nd object.

Smart Search.

- createObjectSearch() - Creates a function to search an object regularly using a substring. Similar to createSmartSearch(), but creates a 'relevancy index' for each potential entry and affixes them to a return object.
    - arg0_options: (Object)
        - exclude_zero_relevance: (Boolean) - Optional. Whether to exclude entries with zero or less relevance from the end result. True by default.
        - function_name: (String) - The function name to define this search as in the global namespace.
        - priority_compounding: (String) - Optional. Either 'linear'/'multiplicative'. 'multiplicative' by default.
        - priority_order: (Array<String, ...>) - The order in which to search, both soft/hard. First is most important, last is least important. 'key' defines base key. Note that these values compound on top of each other.
    - Returns: (Function)
- createSmartSearch() - Defines a smart search function off of which various attributes are checked in a specific order, both soft and hard.
    - arg0_options: (Object)
        - function_name: (String) - The function name to define this search as in the global namespace.
        - priority_order: (Array<String, ...>) - The order in which to search, both soft/hard. First is most important, last is least important. 'key' defines the base key.
        - hard_search: (Boolean) - Optional. True by default.
        - soft_search: (Boolean) - Optional. True by default.
    - Returns: (Function)
- deleteSmartSearch() - Deletes a smart search function.
    - arg0_name: (String) - The .function_name of the smart search to delete.

Pathfinding.

A*.

- aStar() - Performs the A* algorithm between a starting point and destination within an object graph.
    - arg0_graph: (Object) - The graph to pass.
    - arg1_start_key: (String) - The node key to start in.
    - arg2_end_key: (String) - The node key to end in.
    - Returns: (Array<String, …>)
- aStarHeuristicCost() - Currently a placeholder function. Returns 0.
- getLowestFScoreNode() - Fetches the node within the lowest F-score.
    - arg0_nodes: (Array<String, …>) - The nodes to pass to the function.
    - arg1_f_score: (Number) - The F-score to compare to.
    - Returns: (String)
- getReverseNeighbours() - Fetches the reverse neighbours in a path graph.
    - arg0_graph: (Object) - The graph to pass.
    - arg1_node: (String) - The key of the node to reverse neighbours for.
    - Returns: (Object)
- reconstructPath() - Internal helper function for reconstructing a path.
    - arg0_came_from: (Object) - The starting node.
    - arg1_current: (Object) - The ending node.
    - Returns: (Array<String, …>)

Strings.

Basic.

- capitaliseWords() - Capitalises all the words in a string.
    - arg0_input_string: (String) - The string to pass to the function.
    - Returns: (String)
- cleanStringify() - Cleans an input object to be compatible with JSON.stringify().
    - arg0_input_object: (String) - The object to pass to the function.
    - Returns: (Object)

Cleaning.

- stripMarkdown() - Strips markdown from a string.
    - arg0_input_string: (String) - The string to pass to the function.
    - Returns: (String)
- stripNonNumerics() - Strips all non-numeric characters (0-9) from a string.
    - arg0_input_string: (String) - The string to pass to the function.
    - Returns: (String)

Split.

- split() - Splits a string in two based on a character index.
    - arg0_input_string: (String) - The string to pass to the function.
    - arg1_index: (Number) - Optional. The index to split the string on. 0 by default.
    - Returns: (Array<String, String>)
- splitMarkdownString() - Splits a string according to Markdown, preserving lists, with \n as breakpoint.
    - arg0_input_string: (String) - The input string to pass to the function.
    - arg1_options: (Object)
        - maximum_characters: (Number) - Optional. The maximum characters per page. 1024 by default.
        - maximum_lines: (Number) - Optional. The maximum lines per page. Undefined by default.
        - split_bullet_points: (Boolean) - Optional. Whether to try and keep boolean points together. False by default
    - Returns: (Array<String, …>)
- splitString() - Splits a string equally by character count.
    - arg0_input_string: (String) - The string to pass to the function.
    - arg1_length: (Number) - Optional. The number of characters to allow per page. 200 by default.
- truncateString() - Truncates a string after to a given max. character len.
    - arg0_input_string: (String) - The string to pass to the function.
    - arg1_length: (Number) - Optional. The number of max characters to display. 80 by default.
    - arg2_do_not_show_dots: (Boolean) - Optional. Whether to show dots at the end. False by default.

Context Menus.

DATATYPES.

Hierarchy. (To be redocumented after being patched up)

<hierarchy_key>: (Object)  
items: (Array<Object>) - Contains all the items of a given hierarchy.  
[...]: (Object)  
id: (String) - The ID of the given item.  
groups: (Object) - Contains groups/subgroups within the hierarchy.  
<group_key>: (Object)  
id: (String) - The ID of the given group.  
name: (String) - Its human-readable name.

items: (Array<String>)  
subgroups*: (Array<String>)