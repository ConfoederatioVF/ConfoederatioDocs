This page was last updated on **20 January 2026**. In the meantime, it may have become outdated. Please check in with Vercengen's documentation website for up-to-date information. Single-file documentation pages are mainly meant for AI models to ingest.

**ve.Feature**:
```js
/**
 * <span color = "yellow">{@link ve.Feature}</span>: Features in Vercengen represent special containers such as panels, windows, tooltips, or interface which encapsulate <span color = "yellow">{@link ve.Component}</span> types. 
 * 
 * Used to automatically destructure `arg0_components_obj`.
 * 
 * ##### Constructor:
 * - `arg0_components_obj`: {@link function}|{@link Object}<{@link ve.Component}>|{@link string}|{@link ve.Component}
 * - `arg1_options`: {@link Object} - Fed into this.options for localised parsing.
 * 
 * ##### DOM:
 * - `.instance`: this:{@link ve.Component}
 * 
 * ##### Instance:
 * - `.child_class=this.constructor`: {@link ve.Feature} - The constructor object of the child class.
 * - `.child_class_obj=ve[htis.child_class.prototype.constructor.name]`: {@link ve.Feature} - The actual object of the child class.
 * - `.components_obj`: {@link Array}<{@link ve.Component}>
 * - `.id`: {@link string}
 * - `.is_vercengen_feature=true`: {@link boolean} - Whether to mark this ve.Feature as a Vercengen feature.
 * - `.options`: {@link Object}
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.Feature.addComponents|addComponents}</span>(arg0_components_obj:{@link Object}<{@link ve.Component}>) - Appends new components to the present ve.Feature.
 * - <span color=00ffff>{@link ve.Feature.close|close}</span>() - Alias for .remove()
 * - <span color=00ffff>{@link ve.Feature.remove|remove}</span>() - Removes the current feature.
 * - <span color=00ffff>{@link ve.Feature.removeComponents|removeComponents}</span>(arg0_components_obj:{@link Object}<{@link ve.Component}>) - Removes components from the current {@link this.element} based on key names.
 * - <span color=00ffff>{@link ve.Feature.updateOwner|updateOwner}</span>() - Updates the `.owner`/`.owners` fields for all encapsulated components to ve.Feature if no {@link ve.Class} owner could be found.
 * 
 * ##### Static Fields:
 * - `.instances`: {@link Array}<{@link ve.Feature}>
 * 
 * ##### Types:
 * - {@link ve.Feature.ve.Confirm|ve.Confirm}(arg0_components_obj:{@link Object}<{@link ve.Component}>, arg1_options:{@link Object}) - Confirm dialogue/modal.
 * - {@link ve.Feature.ve.ContextMenu|ve.ContextMenu}(arg0_components_obj:{@link Object}<{@link ve.Component}>, arg1_options:{@link Object}) - Pop-up context menu located at the cursor with an assigned `.id` to prevent duplicates.
 * - {@link ve.Feature.ve.Modal|ve.Modal}(arg0_components_obj:{@link Object}<{@link ve.Component}>, arg1_options:{@link Object}) - Overlays a modal on top of the current Vercengen overlay interface. Must be responded to before conventional windows.
 * - {@link ve.Feature.ve.Navbar|ve.Navbar}(arg0_navbar_obj:{@link Object}, arg1_options:{@link Object}) - Creates an action topbar with recursive dropdown menus and keybind settings.
 * - {@link ve.Feature.ve.PageMenuWindow|ve.PageMenuWindow}(arg0_page_obj:{@link Object}, arg1_options:{@link Object}) - Creates a page menu window, which encapsulates components in pages instead of interfaces.
 * - {@link ve.Feature.ve.Scene|ve.Scene}(arg0_components_obj:{@link Object}<{@link ve.Component}>, arg1_options:{@link Object}) - Creates a full-viewport rendering scene.
 * - {@link ve.Feature.ve.Toast|ve.Toast}(arg0_components_obj:{@link Object}<{@link ve.Component}>|{@link string}, arg1_options:{@link Object}) - Spawns a toast at the current cursor.
 * - {@link ve.Feature.ve.Tooltip|ve.Tooltip}(arg0_components_obj:{@link Object}<{@link ve.Component}>|{@link string}|{@link ve.Component}, arg1_options:{@link Object}) - Spawns a tooltip for the given `.options.element`.
 * - {@link ve.Feature.ve.Window|ve.Window}(arg0_components_obj:{@link Object}<{@link ve.Component}>|{@link string}, arg1_options:{@link Object}) - Default ve.Feature for encapsulating components in <span color = "yellow">{@link ve.Class}</span>.
 * 
 * @class
 * @memberof ve
 * @namespace ve.Feature
 * @type {ve.Feature}
 */
```

**ve.Confirm**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Feature}</span> for methods or fields inherited from the parent, such as automatic destructuring.
 * 
 * Confirmation prompt used for executing a `.options.special_function` call.
 * - Functional binding: <span color=00ffff>veConfirm</span>().
 * - Inherits Feature: {@link ve.Modal}
 * 
 * ##### Constructor:
 * - `arg0_components_obj`: {@link function}|{@link Object}<{@link ve.Component}>|{@link string}|{@link ve.Component}
 * - `arg1_options`: {@link Object} - Superset of `.options` for {@link ve.Modal}.
 *   - `.do_not_close`: {@link boolean} - Whether to keep the confirmation prompt if `.special_function` is properly fired.
 *   - `.special_function`: {@link function}(v:{@link function}, e:{@link ve.Button})
 * 
 * ##### Methods::
 * - <span color=00ffff>{@link ve.Confirm.close|close}</span>()
 *
 * @augments ve.Feature
 * @memberof ve.Feature
 * @type {ve.Confirm}
 */
```

**ve.ContextMenu**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Feature}</span> for methods or fields inherited from the parent, such as automatic destructuring.
 * 
 * Represents a ContextMenu Feature that contains a set of components. {@link ve.Window} instances are stored in `.windows`. Recursive.
 * - Functional binding: <span color=00ffff>veContextMenu</span>().
 * - Inherits feature: {@link ve.Window}
 * 
 * The immediate {@link ve.Button} element bound to the ContextMenu instance is contained in `.element`.
 * 
 * ##### Constructor:
 * - `arg0_components_obj`: {@link Object}<{@link ve.Component}>
 * - `arg1_options`: {@link Object}
 *   - `.anchor="left"/"right"` - Either 'left'/'right'. Position defaults to the side that has the most space.
 *   - `.button_options`: {@link ve.Button|ve.Button.options}
 *   - `.height`: {@link string}
 *   - `.id`: {@link string}
 *   - `.mode="static_ui"` - Either 'static_ui'/'static_window'/'window'.
 *   - `.width`: {@link string}
 *   - `.x=HTML.mouse_x`: {@link number}
 *   - `.y=HTML.mouse_y`: {@link number}
 *   
 * ##### Methods:
 * - <span color=00ffff>{@link ve.ContextMenu.addContextMenu|addContextMenu}</span>(arg0_components_obj: {@link Object}<{@link ve.Component}>, arg1_options: {@link ve.Window|ve.Window.options}) | {@link ve.Window} - The return `.index`: {@link number} contains the index of the opened window.
 *   - `arg1_options`: {@link ve.Window|ve.Window.options}
 *     - `.id`: {@link string} - The ID to prevent duplicate context menus from being opened.
 * - <span color=00ffff>{@link ve.ContextMenu.close|close}</span>() | this:{@link ve.ContextMenu}
 * - <span color=00ffff>{@link ve.ContextMenu.getCurrentOffset|getCurrentOffset}</span>() | {@link number}
 * - <span color=00ffff>{@link ve.ContextMenu.open|open}</span>() | this:{@link ve.ContextMenu}
 * - <span color=00ffff>{@link ve.ContextMenu.removeContextMenu|removeContextMenu}</span>(arg0_index: this:{@link number}) | {@link ve.ContextMenu}
 * 
 * @augments ve.Feature
 * @memberof ve.Feature
 * @type {ve.ContextMenu}
 */
```

**ve.Modal**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Feature}</span> for methods or fields inherited from the parent, such as automatic destructuring.
 * 
 * Represents a Modal Feature that contains a set of components which are wrapped inside a ve.Modal.
 * - Functional binding: <span color=00ffff>veModal</span>().
 * - Inherited by: {@link ve.Confirm}
 * - Inherits Feature: {@link ve.Window}
 * 
 * ##### Constructor:
 * - `arg0_components_obj`: {@link function}|{@link Object}<{@link ve.Component}>|{@link string}|{@link ve.Component}
 * - `arg1_options`: {@link Object} - Set of `.options` for {@link ve.Window}
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.Modal.close|close}</span>()
 * 
 * @augments ve.Feature
 * @memberof ve.Feature
 * @type {ve.Modal}
 */
```

**ve.Navbar**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Feature}</span> for methods or fields inherited from the parent, such as automatic destructuring. 
 * 
 * Represents a Navbar Feature, ideally at the global level (unless it is specifically bound to an element in .options).
 * - Functional binding: <span color=00ffff>veNavbar</span>().
 * 
 * ##### Constructor:
 * - `arg0_navbar_obj`: {@link Object}
 *   - `<tab_key>`: {@link Object}
 *     - `name`: {@link string}
 *     - 
 *     - `active`: {@link boolean}
 *     - `<dropdown_key>`: {@link Object}
 *       - `<dropdown_key>`: {@link Object} - Nested dropdown if available.
 *       - `.active`: {@link boolean}
 *       - `.onclick`: {@link function}({@link HTMLElement})
 *       - `.keybind`: {@link string} - Mousetrap key combo which triggers the bound `.onclick` event if possible.
 *       - `.name`: {@link string}
 * - `arg1_options`: {@link Object}
 *   - `.anchor_element`: {@link HTMLElement}|{@link string}
 *   - `.attributes`: {@link Object}
 *     - `<attribute_key>`: {@link string}
 *   - `.name`: {@link string}
 *   - `.style`: {@link Object}
 *     - `<style_key>`: {@link string}
 *     
 * ##### Methods:
 * - <span color=00ffff>{@link ve.Navbar.generateHTMLRecursively|generateHTMLRecursively}</span>(arg0_navbar_obj: {@link Object}) | {@link HTMLUListElement}
 * 
 * @augments ve.Feature
 * @memberof ve.Feature
 * @type {ve.Navbar}
 */
```

**ve.PageMenuWindow**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Feature}</span> for methods or fields inherited from the parent, such as automatic destructuring.
 * 
 * Represents a PageMenuWindow Feature that contains a page_obj type directly analogous to that used in {@link ve.PageMenu}. The associated {@link ve.Window} is stored in `.window`.
 * - Functional binding: <span color=00ffff>vePageMenuWindow</span>().
 * 
 * ##### Constructor:
 * - `arg0_page_obj`: {@link Object}
 *   - `<page_key>`: {@link Object}
 *     - `.name`: {@link string} - '<page_key>' by default.
 *     - `.components_obj:` {@link Object}<{@link ve.Component}>
 *     - `.options`: {@link Object} - Options for the {@link ve.Interface} .components_obj will be wrapped inside.
 * - `arg1_options`: {@link Object} - Superset of `.options` for {@link ve.Window}.
 *   - `anchor="top_left"` - Either 'bottom_left'/'bottom_right'/'top_left'/'top_right'.
 *   - `height="12rem"`: {@link number}
 *   - `width="12rem"`: {@link number}
 *   - `x=HTML.mouse_x`: {@link number}
 *   - `y=HTML.mouse_y`: {@link number}
 *   -
 *   - `mode="window"`: {@link string} - Either 'static_ui'/'static_window'/'window'.
 *   - `name=""`: {@link string} - Auto-resolves to 'Window' instead if `.can_rename=true`.
 *   - `theme`: {@link string} - The CSS theme to apply to the Feature.
 *   -
 *   - `can_close`: {@link boolean}
 *   - `can_rename`: {@link boolean}
 *   - `draggable`: {@link boolean}
 *   - `headless`: {@link boolean}
 *   - `resizeable`: {@link boolean}
 *   - Inherited from {@link ve.PageMenu|ve.PageMenu.options}
 *   - `.page_menu_options`: {@link Object}
 *     - `.attributes`: {@link Object}
 *       - `<attribute_key>`: {@link string}
 *     - `.name`: {@link string} - Refers to the name of the current page.
 *     - `.onchange`: {@link function}(this:{@link ve.PageMenu})
 *     - `.style`: {@link Object}
 *       - `<style_key>`: {@link string}
 *       
 * ##### Methods:
 * - <span color=00ffff>{@link ve.PageMenuWindow.close|close}</span>()
 *
 * @augments ve.Feature
 * @memberof ve.Feature
 * @type {ve.PageMenuWindow}
 */
```

**ve.Scene**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Feature}</span> for methods or fields inherited from the parent, such as automatic destructuring.
 * 
 * Creates a background scene, typically meant as a full viewport screen with a draw/initialisation loop. Elements are mounted to {@link ve.scene_el}.
 * - Functional binding: <span color=00ffff>veScene</span>().
 * 
 * ##### Constructor:
 * - `arg0_components_obj`: {@link function}|{@link Object}<{@link ve.Component}>|{@link string}|{@link ve.Component}
 * - `arg1_options`: {@link Object}
 * 
 * ##### Instance:
 * - `.v`: {@link Object}<{@link ve.Component}>
 * 
 * @augments ve.Feature
 * @memberof ve.Feature
 * @type {ve.Scene}
 */
```

**ve.Toast**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Feature}</span> for methods or fields inherited from the parent, such as automatic destructuring.
 * 
 * Creates a toast spawned at the present cursor. For this component, it is recommended to use a string rather than {@link ve.Component} types for the first parameter (`arg0_components_obj`).
 * - Functional binding: <span color=00ffff>veToast</span>().
 * 
 * ##### Constructor:
 * - `arg0_components_obj`: {@link function}|{@link Object}<{@link ve.Component}>|{@link string}|{@link ve.Component}
 * - `arg1_options`: {@link Object}
 *   - `.duration=1200`: {@link number} - The duration the toast should last in ms. 1,2 seconds by default.
 * 
 * ##### Methods:
 * - <span color=00ffff>{@link ve.Toast.refresh|refresh}</span>(arg0_components_obj:{@link Object}<{@link ve.Component}>) - Refreshes the Toast display if possible.
 * 
 * @augments ve.Feature
 * @memberof ve.Feature
 * @type {ve.Toast}
 */
```

**ve.Tooltip**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Feature}</span> for methods or fields inherited from the parent, such as automatic destructuring.
 * 
 * Represents a Tooltip Feature that contains a set of components which are wrapped inside an Interface. This uses a {@link tippy} element.
 * - Functional binding: <span color=00ffff>veTooltip</span>().
 * 
 * ##### Constructor:
 * - `arg0_components_obj`: {@link function}|{@link Object}<{@link ve.Component}>|{@link string}
 * - `arg1_options`: {@link Object}
 *   - `attributes`: {@link Object}<{@link string}>
 *   - `element`: {@link HTMLElement}|{@link string} - The anchor element that ve.Tooltip should be bound to.
 *   - `style`: {@linK Object}<{@link string}>
 *     
 * ##### Instance:
 * - `.anchor_element`: {@link HTMLElement}
 * - `.v`: {@link HTMLElement}
 *     
 * @augments ve.Feature
 * @memberof ve.Feature
 * @type {ve.Tooltip}
 */
```

**ve.Window**:
```js
/**
 * Refer to <span color = "yellow">{@link ve.Feature}</span> for methods or fields inherited from the parent, such as automatic destructuring.
 * 
 * Represents a Window Feature that contains a set of components which are wrapped inside an Interface.
 * - Inherited by: {@link ve.ContextMenu}, {@link ve.Modal}, {@link ve.PageMenuWindow}
 *
 * ##### Constructor:
 * - `arg0_components_obj`: {@link Object}<{@link ve.Component}>
 * - `arg1_options`: {@link Object}
 *   - `.anchor="top_left"` - Either 'bottom_left'/'bottom_right'/'top_left'/'top_right'.
 *   - `.height="auto"`: {@link number}
 *   - `.width="12rem"`: {@link number}
 *   - `.x=HTML.mouse_x`: {@link function}|{@link number} - If the type is a function, it must return a number.
 *   - `.y=HTML.mouse_y`: {@link function}|{@link number} - If the type is a function, it must return a number.
 *   -
 *   - `.do_not_wrap=false`: {@link boolean} - Whether to disable wrapping in an always open {@link ve.Interface}.
 *   - `.id`: {@link string}
 *   - `.mode="window"`: {@link string} - Either 'static_ui'/'static_window'/'window'.
 *   - `.name=""`: {@link string} - Auto-resolves to 'Window' instead if `.can_rename=true`.
 *   - `.theme`: {@link string} - The CSS theme to apply to the Feature.
 *   -
 *   - `.can_close`: {@link boolean}
 *   - `.can_rename`: {@link boolean}
 *   - `.draggable`: {@link boolean}
 *   - `.headless`: {@link boolean}
 *   - `.resizeable`: {@link boolean}
 *   - 
 *   - `.onuserchange`: {@link function}(arg0_v:{@link Object}, arg1_e:{@link Event}) - Fires upon user changes to the window. Changes are discrete, and the set of Object keys may vary.
 *     - `arg0_v`: {@link Object}
 *       - `.close`: {@link boolean} - Whether the change is a close event.
 *       - `.name`: {@link string}
 *     - `arg1_e`: {@link Object}
 *       - `.instance`: {@link ve.Window}
 *   
 * ##### Instance:
 * - `.v`: {@link Object}<{@link ve.Component}>
 *
 * ##### Methods:
 * - <span color=00ffff>{@link ve.Window.getZIndex|getZIndex}</span>() | {@link number}
 * - <span color=00ffff>{@link ve.Window.select|select}</span>()
 * - <span color=00ffff>{@link ve.Window.setCoords|setCoords}</span>(arg0_x:{@link number}, arg1_y:{@link number})
 * - <span color=00ffff>{@link ve.Window.setName|setName}</span>(arg0_name:{@link string})
 * - <span color=00ffff>{@link ve.Window.setSize|setSize}</span>(arg0_width:{@link number}|{@link string}, arg1_height:{@link number}|{@link string})
 * - <span color=00ffff>{@link ve.Window.refresh|refresh}</span>(arg0_components_obj:{@link Object}<{@link ve.Component}>)
 * 
 * ##### Static Fields:
 * - `.instances`: {@link Array}<{@link ve.Window}>
 * 
 * ##### Static Methods:
 * - <span color=00ffff>{@link ve.Window.getHighestZIndex}</span>(arg0_options:{ return_object=false: {@link boolean} }) | {@link number}|{@link ve.Window}
 *   
 * @augments ve.Feature
 * @memberof ve.Feature
 * @type {ve.Window}
 */
```