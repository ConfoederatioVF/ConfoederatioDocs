#Y2025 #TODO #plans #vercengen
See also: [[Vercengen Plans]]
## Description

**Data Series**:
Fundamentally, graphs are images. When thinking about selecting data series that work with graphs, they should be thought of as patterned lines to which a modifier (line, bar, pie, candlestick, boxplot, etc). is applied. This means that all lines should be 2 columns wide, and the leftmost column taken as the attribute if the selection is only 1 column wide. The user then has the following checkbox options per series:
- Leftmost Column Type: Either 'category'/'value'/'time'/'log'
- Pivot Selection (pivots to horizontal layout instead of vertical)
- Use Leftmost Column in Table as X axis/series iterator

If the series is more than 2 columns wide, this creates a 'Series Group', where other data values are lined up to the leftmost available column as selected by the user. This creates groupings in the form of stacked charts where applicable. If not all columns can be used, a debug warning will pop up in the Graph Creation screen.

**GraphChart Symbols:**
Each series then has a symbol menu depending on the currently rendered ve.GraphChart that determines how it displays for the given GraphChart component. These symbols function as a GUI for Echarts bindings per graph type.

**Graph Symbols:**
The composite graph also has multiple symbols available:
- Title (Singleton)
- ve.GraphLegend (Component)
- ve.GraphText (Component) - WYSIWYG overlay

**The important thing is to support all Echarts API bindings naturally. View them here:** [Echarts API](https://echarts.apache.org/en/option.html)
In terms of timing, the basic framework (such that only new types of GraphCharts and bindings must be created) should be finished by the end of the current year (2025).
## TODO Components
- Finish 'All' tab for ve.NodeEditor DONE
- ve.DatavisSuite
	- ve.Graph
	- ve.GraphChart
	- ve.GraphLegend
	- ve.GraphText
	- ve.ObjectInspector DONE
		- Options per ObjectInspector so that they can be expanded/closed at will DONE
## TODO

Add Chart button/Remove Chart button with drag and drop table layout
- dragging ve.GraphChart components are freeform within the ve.Graph panel/space, ad they can overlap
Graph types:
- line chart
- line chart (composition) - shared with pie chart
- line chart (ordinal)
- line chart (polar)
- line chart (stacked)

- bar chart
- bar chart (composition) - shared with pie chart
- bar chart (grouped)
- bar chart (polar)
- bar chart (radial)
- bar chart (stacked)
- bar chart (stacked, polar)
- bar chart (stacked, radial)

- pie chart
- pie chart (doughnut)
- pie chart (nested)

- scatterplot
- scatterplot (axial)
- scatterplot (geo)

- geo (choropleth)
- geo (hexagonal)

- alluvial
- calendar
- candlestick
- chord
- boxplot
- funnel
- gauge
- graph (flowchart)
- graph (network)
- graph (radial)
- heatmap
- matrix
- parallel
- radar
- river
- sunburst
- tree
- treemap

- 3D globe
- 3D bar
- 3D lines
- 3D map
- 3D scatter
- 3D surface

- Advanced options scripting using NodeEditor with preview options Object via ve.ObjectInspector
- Race options for each graph