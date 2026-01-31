---
cover: https://i.postimg.cc/qvvmDC6H/embed-template.png
description: Specifications for file and class organisation for complex models and their resultant databases and data portals.
---

Complex databases need to be well-organised, in both their data structure as well as their given class structure. Because of this, [[Confoederatio]] databases are split up into discrete **Tasks** grouped into **Stages**, which parse a common config.

This allows for databases to be structured more like iterative software as opposed to single-use pipelines, allowing for refactoring down the line.
## Complex Data Schema (CDS):

1. **Data Scraping**
   Data scrapes contain raw artefacts of data that have not yet been mutated by the given database or cleaned. Their file formats may have been converted, but all transformations at this stage are guaranteed to be lossless.
   
	1. `1.data_scraping/`
		1. `<variable_name>_<database_name>/`
2. **Data Cleaning**
   Initial databases have had their data structures mutated for easier manipulation and unification in the merging phase. This often includes data interpolation and statistical techniques to make data series comparable to one another (i.e. in the case of proxy variables).
   
   All intermediate databases at this stage (i.e. KK10LUH2 for Velkscala) should be made available here, since they have technically been cleaned and are not primary. They should be prefixed with a `$` sign.
   
	1. `2.data_cleaning/`
		1. `$<variable_name>_<intermediate_database_name>/` - Intermediate databases should **NOT** have UIs, since they are temporary and can be regenerated at any time.
		2. `<variable_name>_<input_database_name>/`
		3. `<variable_name>_UI/`
		4. `<variable_name>_UI.js` - Used for editing GUIs that bind the current database to a visualisation when its view is toggled. Note that it must support adding/removing its visualisation to the scene. Encapsulated by a class.
3. **Data Merging**
   The goal of data merging is unification and the collation of all previous cleaned datasets into a single cross-comparable object. This typically takes multiple stages, whose goal is to flatten the data as much as possible for easier parsing whilst preserving fidelity. (The UUD in [[Stadestér]] is an example of Data Merging).
   
	1. `3.data_merging/`
		1. `<variable_name>_[n].<merge_type>/`
4. **Data Processing**
   Any data massaging or processing (i.e. metro buffering) is done at this step, which mutate a unified merged layer but are necessary to final outputs and the ability to perform statistical analysis and verification.
   
	1. `4.data_processing/`
		1. `<variable_name>/`
5. **Data Post-Processing**
   Creates final artefacts for eventual Data Visualisation. These refer to raw image graphs, output rasters, etc., which must still be made readable in a GUI format, or in a final methodological paper.
   
	1. `5.data_post_processing/`
		1. `<variable_name>/`
6. **Data Visualisation**
   Contains most app/GUI code, as well as scripts that assemble the final methodological paper/data portal. This should be a unified app with the ability for cross comparison.
   
	1. `6.data_visualisation/`
		1. `analysis/`
			1. `<tool_class_name>/`
			2. `<tool_class_name>.js`
		2. `<mapmode_name>/`

**App/GUI:**
A main dashboard app, from which tasks can be multithreaded is provided as `./autorun.bat`, and serves as the main entry point into a complex database. It is divided into the following views:

1. **Processing** - Directed Acyclic Graph (DAG) dashboard which is used to orchestrate and visualise tasks and methodology.
2. **Visualisation** - 3D map and data viewer with floating windows for geostatistical context. It may also contain GUIs for tracing data provenance, helping with copychecking.
3. **Papers** - Sorts papers by version and automatically produces them (similar to an R pipeline). This should help with reproducibility, especially surroundin given charts.
   
   [[Echarts]] should be used for chart production, and inline scripts should be referenced and linked.