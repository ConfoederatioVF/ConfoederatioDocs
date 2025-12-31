## Abstract.

The file structure of a Mod determines how Deepscript is loaded and parsed within the main gamestate and Editor context. Additional JSON is typically placed in mod.txt, which is used to determine other display metadata, particularly for revamped or later mod loaders.

## (Data Structure) Mod File.

//Default attributes.  
Name: (String)  
ChangeNote: (String)  
Description: (String)  
Tags: (Array\<String\>)

//Deepscript attributes.  
order: (Number) \- The order in which this mod is loaded in terms of DeepScript.

deepscript\_file\_extensions: \[‘.ds’, ‘.js’\] //Deepscript file extensions to parse. Used for external editor syntax highlighting if necessary. ‘.ds’ by default.