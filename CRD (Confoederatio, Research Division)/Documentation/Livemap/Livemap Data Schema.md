**Abstract.**

Because of the complex nature of live data, Livemap/Collation (referred to as **Collation** from this point on) should ideally be structured similarly to distributed software along the lines of Palantir Foundry, with several modifications to deal with issues of scale.

The core of the system will be Workers, who will have routine tasks at set intervals to fetch data from constituent data sources, and will relay back the time of the last successful task with failures being flagged for manual repair and a debug log that can be viewed to see where it failed.

The dynamic database will be the ledger from which all ontology is hydrated and then processed by models into the end view layer, which can be seen in [[Naissance HGIS]] with a dedicated 'Livemap' mapmode, whose specification would require sub-mapmodes underneath it for clarity. In addition, workers should ideally share a set number of browsers (1 for testing) to avoid flooding traffic and performance overheads.

**Hierarchy.**

1. Scrapers/Workers
2. Dynamic Database
3. Ontology (hydrated from Database)
4. Models
5. View

**Dynamic Database Design (3D):**
- Dynamic databases should be partitioned into a JSON object per line, with each line being streamed in and hydrated into Ontology upon arrival. Ontologies can then be packed back out into CSVs chronologically.
- Each CSV should contain a 1-day time period, allowing for chronological loading of most recent data first, followed by less recent data.
- Ontologies should be hashed such that when their ID is re-encountered, their state is mutated from header if there are any substantial changes.

**Scraper API:**
Scrapers should have access to both a .nodeapi and a .webapi. This will be implemented in Puppeteer at first, but can be transported over to Selenium in the future.

**Worker Contract:**

Blacktraffic Workers are manifested from the `livemap/1.workers/types` folder, and hydrated from `livemap/1.workers/dashboard`.

**Blacktraffic.Worker: class**
Blacktraffic.Worker logs should be coordinated with **log.Channel**.

- static saves_folder: string - Also determines the logs folder
- static workers_obj: Object\<Worker\>
  
- .config: Object
- .is_enabled: boolean
- .name: string - The human readable name for this worker
- .options: boolean
	- .config_json: string - The config JSON5 file to load. Accessible as this.config
	- .do_not_close_tab=false: boolean
	- .log_channel: string - `worker_${type}` by default
	- .tags: string[] - Any tags associated with the given worker
- .type: string
  
- getBrowser(): AgentBrowserPuppeteer. If the browser is not currently open, a new browser will be opened (shared across all Blacktraffic.Worker instances)
- getTab(): PuppeteerTab. If the tab is not currently open, a new tab will be opened.
  
- async disable() - Disables the current worker.
- async enable() - Enables the current worker.
- getCurrentTimeStatus(): { status: "done"/"running", timestamp: number }
- getCurrentStatus(): string - EIther 'idle'/'failed'/'partially_failed'/'running'/'done'.
- getCurrentStatusElement(): HTMLElement - Either 'Failed', 'Partially Failed', 'Running (Time Elapsed) - Started [Time]', 'Done'.
- getLastSuccessfulJob(): Date
- getJobList(): Object[] - Returns a list of jobs in chronological order, with status and debug logs
	- \[n\]: Object
		- log_file_path: string|undefined
		- status: string
		- time_elapsed: number
		- timestamp: number
- remove() - Deletes the current worker.
- async run() | Ontology[] - Opens a designated tab and runs the worker on it. Once it finishes, the tab is closed unless specified otherwise. Returns an array of Ontology objects.
  
- fromJSON() - Converts the current worker from JSON.
- toJSON() - Converts the worker's current data into JSON.
- static fromJSON() - Converts all workers to JSON.
- static toJSON() - Hydrates all workers from JSON.

**Ontology Contract:**

RelationObject:
- .id: string - The other Ontology associated with this one.
- .type: string[]|undefined - Assumed to be 'relation' by default. The type of relationship held with the other Onttology.

Object:
- static queue: Ontology[] - Current ontologies that have arrived in the last 100ms for ID assignment. Immediately cleared thereafter.

- .id: string - Unique Ontology ID. This should be done by hashing the inception date alongside the Ontology instances in queue.
- .geometries: maptalks.Geometry[]
- .worker_type - The worker type that this Ontology originally came from

- .state (Object[]):
	- .date: number - The timestamp at which this state mutation occurred.
	- .data: Object - Concatenated state mutation.
	  
	- .add_relations: RelationObject[]
	- .add_tags: string[]
	- .remove_relations: RelationObject[]|string[] - Ontology IDs.
	- .remove_tags: string[]
	- .set_tags: string[] - Override.
	- .set_relations: RelationObject[] - Override. 
	
- addRelation()
- draw() - Draws the current Ontology and appends them to this.geometries.
- getElement(arg0_options) - Returns the current HTMLElement that would represent this Ontology. Options include `.do_not_show_timeline`
- getState(arg0_date) - Gets the state at a current date in time.
- getTimelineElement(arg0_options) - Returns the current HTMLElement that would represent this Ontology's timeline. Options include `.start_date`, `.end_date`
- remove()
- removeRelation()
- removeRelations()
  
- addKeyframe()
- deleteKeyframe()
- getFirstKeyframeWithProperty()
- getLastKeyframeWithProperty()
- moveKeyframe()
- jumpToKeyframe()