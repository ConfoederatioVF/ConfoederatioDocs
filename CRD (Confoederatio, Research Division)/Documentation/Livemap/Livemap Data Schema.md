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