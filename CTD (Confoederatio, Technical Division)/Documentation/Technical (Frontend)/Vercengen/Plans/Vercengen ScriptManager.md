- Adjustable height for scene in view settings DONE
- Better console using ve.ObjectInspector where possible (for very large objects, a confirmation prompt will be given) DONE
- Global find and replace/context-aware search DONE
- Manual synchronisation between blocks and code as default DONE
	- Red/green border highlighting for saved/unsaved states DONE
- Multifile search select bar at the bottom to which you can pin files, with per file symbol styling (i.e. colour/text coding)
    - Save indicator for multifile search select as bottom underline plus asterisk
- Progress indicator under multifile search select for progress on indexing new project folders DONE
- Progress indicator for indexing for global find and replace DONE

- Multi-language syntax support DONE
- Project folder documentation/JSDoc compatibility via indexing DONE

**Current Monaco options (default).**
```js
{
	autoIndent: "advanced",  
	automaticLayout: true,  
	contextmenu: true,  
	detectIndentation: false,  
	fixedOverflowWidgets: true,  
	fontFamily: computed_style_obj.getPropertyValue("--monospace-font-family").replace(/"/gm, ""),  
	fontLigatures: true,  
	fontSize: 14,  
	formatOnPaste: false,  
	insertSpaces: true,  
	minimap: { enabled: true },  
	tabSize: 2,
}
```

**Revised ScriptManager TODO.**

1. Folder/file context menus, mark as excluded. This should be writen at the project level as a dotfile if possible, but can be cached and held in state. DONE
	1. Index documentation needs to be aborted upon reindexing DONE
2. Refactor ScriptManager such that the main class is broken up and private modules have better documentation. WIP
3. Bottombar with file switching. Files in the bottombar can be reordered and closed at will.  DONE
4. Autosave should be on by default in a project folder with manual synchronisation, which is prompted upon changing code in one view and clicking in the other. This can be changed in settings DONE
5. Add options for indentation, changing font family, and changing the background image for ve.ScriptManager DONE
6. Override file type DONE
7. Excluded folders should be excluded from search DONE

**Revised ScriptManager Features TODO.**
- Bottombars should be saved with and automatically opened based on the extant project file
- Child ScriptManager tracking to keep track so that files can be merged back into parent bottombar
- Files should close when deleted from the bottombar
- Open File in New Instance (opens file in a separate ScriptManager tab and splits it off)