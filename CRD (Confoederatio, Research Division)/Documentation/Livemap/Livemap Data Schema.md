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

**Worker Contract:**

Blacktraffic Workers are manifested from the `livemap/1.workers/types` folder, and hydrated from `livemap/1.workers/dashboard`.

**Blacktraffic.Worker: class**
- static saves_folder: string - Also determines the logs folder
  
- .config: Object
- .is_enabled: boolean
- .name: string - The human readable name for this worker
- .options: boolean
	- .config_json: string - The config JSON5 file to load. Accessible as this.config
	- .do_not_close_tab=false: boolean
- .tags: string[] - Any tags associated with the given worker
- .type: string
  
- get browser(): AgentBrowserPuppeteer. If the browser is not currently open, a new browser will be opened (shared across all Blacktraffic.Worker instances)
- get tab_obj(): PuppeteerTab. If the tab is not currently open, a new tab will be opened.
  
- async disable() - Disables the current worker.
- async enable() - Enables the current worker.
- getCurrentTimeStatus(): { status: "done"/"running", timestamp: number }
- getCurrentStatus(): string - EIther 'failed'/'partially_failed'/'running'/'done'.
- getCurrentStatusElement(): HTMLElement - Either 'Failed', 'Partially Failed', 'Running (Time Elapsed) - Started [Time]', 'Done'.
- getLastSuccessfulJob(): Date
- getJobList(): Object[] - Returns a list of jobs in chronological order, with status and debug logs
	- \[n\]: Object
		- log_file_path: string|undefined
		- status: string
		- time_elapsed: number
		- timestamp: number
- async run() - Opens a designated tab and runs the worker on it. Once it finishes, the tab is closed unless specified otherwise.
  
- fromJSON() - Converts the current worker from JSON.
- toJSON() - Converts the worker's current data into JSON.
- static fromJSON() - Converts all workers to JSON.
- static toJSON() - Hydrates all workers from JSON.