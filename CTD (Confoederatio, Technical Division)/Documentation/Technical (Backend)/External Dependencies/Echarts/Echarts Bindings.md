The following notes are dedicated to [Echarts Documentation](https://echarts.apache.org/en/option.html) since its styling is by and large difficult to follow otherwise. As such, documents below refer to temporary bindings between [[Vercengen]] and [[Echarts]], and are regarded as live planning documentation which may not necessarily be up-to-date with current Vercengen features.

> [!NOTE]
> Graph types in Echarts are held in **Series Symbols** as part of their optioning, not as part of general graph types, which is the approach that Vercengen takes, since it would be more familiar to viewers.

> [!WARNING]
> Current binding documentation is a work-in-progress (WIP). Bindings are complete for chart types up to sunburst.
## Echarts Symbol Types

- [[Echarts Fill Symbol|Fill Symbol]]
- [[Echarts Point Symbol|Point Symbol]] - Used for datapoints.
	- [[Echarts Label Symbol|Label Symbol]] - Used for text on top of or underneath points
- [[Echarts Stroke Symbol|Stroke Symbol]] - Used for the patterned line itself. All graph data originates as a patterned line, including for bar, pie, etc.
- [[Echarts Text Symbol|Text Symbol]]
- [[Echarts Tooltip Symbol|Tooltip Symbol]]

**Chart Specific:** \[WIP] - Handle all chart types specified in [[Vercengen DatavisSuite]] planning

| Chart Type    | Name                 | Page                             |
| ------------- | -------------------- | -------------------------------- |
| line          | Line                 | None                             |
| bar           | Bar                  | [[Echarts Bar Chart]]            |
| pie           | Pie                  | [[Echarts Pie Chart]]            |
| scatter       | Scatterplot          | [[Echarts Scatterplot]]          |
| effectScatter | Animated Scatterplot | [[Echarts Animated Scatterplot]] |
| radar         | Radar                | [[Echarts Radar]]                |
| tree          | Tree                 | [[Echarts Tree]]                 |
| treemap       | Treemap              | [[Echarts Treemap]]              |
| sunburst      | Sunburst             | [[Echarts Sunburst]]             |
| boxplot       | Boxplot              | [[Echarts Boxplot]]              |
| candlestick   | Candlestick          | [[Echarts Candlestick]]          |
| heatmap       | Heatmap              | [[Echarts Heatmap]]              |
| map           | Map                  | [[Echarts Map]]                  |
| parallel      | Parallel             | [[Echarts Parallel]]             |
| lines         | Lines                | [[Echarts Lines]]                |
| graph         | Network Graph        | [[Echarts Network Graph]]        |
| sankey        | Alluvial             | [[Echarts Alluvial]]             |
| funnel        | Funnel               | [[Echarts Funnel]]               |
| gauge         | Gauge                | [[Echarts Gauge]]                |
| pictorialBar  | Pictorial Bar        | [[Echarts Pictorial Bar]]        |
| themeRiver    | River                | [[Echarts River]]                |
| chord         | Chord                | [[Echarts Chord]]                |
| custom        | Custom               | [[Echarts Custom Chart]]         |
## Vercengen Symbol Guide

**Axis Symbols:**
- .x_axis: Object - Echarts: `options.xAxis`
	- ...[[Echarts X Axis Symbol]]
- y_axis: Object - Echarts: `options.yAxis`
	- ...[[Echarts Y Axis Symbol]]

**Graph Symbols:**
- .background_colour: string - Echarts: `options.backgroundColor`
- .default_colours: string[] - Echarts: `options.color` - Determines the default colours each data series takes on.
- .text_symbol: [[Echarts Text Symbol]]
  
- visual_map: Object - Echarts: `options.visualMap`
	- Coords are bound to `options.visualMap.bottom/left/top/right`
	- .anchor: string|undefined
	- .center: Array<number|string, number|string>
	- .x: number|undefined
	- .y: number|undefined
	  
	- .colour: string - `options.visualMap.pieces[n].color`
	- .gt: number - Lower bound - `options.visualMap.pieces[n].gt`
	- .lte: number - Upper bound - `options.visualMap.pieces[n].lte`
### **Series Symbols:**

.symbol: Object
- .custom_type_enabled=false: boolean. Determines if `.symbol.type` should override the graph type.
- .type: string|undefined - Echarts: `options.series[n].type` - Either 'line'/'bar'/'pie'/'scatter'/'effectScatter'/'radar'/'tree'/'treemap'/'sunburst'/'boxplot'/'candlestick'/'heatmap'/'map'/'parallel'/'lines'/'graph'/'sankey'/'funnel'/'gauge'/'pictorialBar'/'themeRiver'/'chord'/'custom'.
  
- .name: string - Echarts: `options.series[n].name`
- ...[[Echarts Fill Symbol]]: Object - Echarts: `options.series[n].areaStyle`, `options.series[n].backgroundStyle`
- ...[[Echarts Stroke Symbol]]: Object - Echarts: `options.series[n].lineStyle`
  
  **Animation:**
- initial_animation: Object
	- delay=0: function|number - Echarts: `options.series[n].animationDelay` - If a function, must return a number.
	- delay_update=300: function|number - Echarts `options.series[n].animationDelayUpdate`
	- duration=1000: function|number - Echarts: `options.series[n].animationDuration` - If a function, must return a number.
	- duration_update=300: function|number - Echarts: `options.series[n].animationDurationUpdate`
	- easing="cubicOut": string - Echarts: `options.series[n].animationEasing` - Easing effects must be predefined, see [Echarts Easing Examples](https://echarts.apache.org/examples/en/editor.html?c=line-easing)
	- easing_update="cubicOut": string - Echarts: `options.series[n].animationEasingUpdate` - Easing effects must be predefined, see [Echarts Easing Examples](https://echarts.apache.org/examples/en/editor.html?c=line-easing)
	- threshold=2000: number
	- universal_transition: Object - Echarts: `options.series[n].universalTransition`
		- enabled=false: boolean - Echarts: `options.series[n].universalTransition.enabled`
		  
		- delay: function - Echarts: `options.series[n].universalTransition.delay` - Needs to return a number.
		- divide_shape: string - Echarts: `options.series[n].universalTransition.divideShape` - Either 'split'/'clone'.
		- series_key: string[] - Echarts: `options.series[n].universalTransition.seriesKey`
  
  **Behaviour:**
- .colour_scheme="series": string - Echarts: `options.series[n].colorBy` - Either 'series'/'data'.
- .interactive=true: boolean - Echarts: `options.series[n].silent`
- .interpolate=false: boolean|number - Echarts: `options.series[n].smooth`. If a number, then the value is from 0 to 1 (tolerance).
- .sampling: string|undefined - Echarts: `options.series[n].sampling`. Either 'lttb'/'average'/'min'/'max'/'minmax'/'sum'.
- .smoothing: string|undefined - Echarts: `options.series[n].smoothMonotone`. Either 'x'/'y' to keep the smoothing on the X/Y axis.
- .z_index: number|undefined - Echarts: `options.series[n].z`
  
- .stack: string|undefined - Echarts: `options.series[n].stack` - The name of the given stack.
- .stack_mode="samesign": string|undefined - Echarts: `options.series[n].stackStrategy` - Either 'samesign'/'all'/'positive'/'negative'.
- stack_order="seriesAsc" - Echarts: `options.series[n].stackOrder` - 'seriesAsc' = ascending, 'seriesDesc' = descending
  
  **Behaviour (Advanced):**
- .blend_mode="source-over": string - Echarts: `options.blendMode`. Either 'source-over'/'lighter'.
- .cursor="pointer": string - Echarts: `options.cursor`
- .hover_layer_threshold=3000: number - Echarts: `options.hoverLayerThreshold`. 
- .rich_text_inherits_plain_label=false: boolean - Echarts: `options.richInheritPlainLabel`.
- .use_UTC=false: boolean - Echarts: `options.useUTC`
  
  **Coordinates:**
- .anchor: string|undefined
- .height="auto": number|string - Echarts: `options.height`
- .width="auto": number|string - Echarts: `options.width`
- .x: number|undefined - Echarts: `options.left/right`
- .y: number|undefined - Echarts: `options.bottom/top`
  
- .coordinate_system="cartesian2d" - Echarts: `options.series[n].coordinateSystem` - Either 'cartesian2d'/'polar'.
- .polar_index: number - Echarts: `options.series[n].polarIndex` - The polar axis to base the chart upon.
- .x_axis_index: number - Echarts: `options.series[n].xAxisIndex`. The X axis to base the chart upon.
- .y_axis_index: number - Echarts: `options.series[n].yAxisIndex`. The Y axis to base the chart upon.
  
- .calendar_id=undefined: string|undefined - Echarts: `options.series[n].calendarId`
- .calendar_index: number - Echarts: `options.series[n].calendarIndex`
- .geo_id=undefined: string|undefined - Echarts: `options.series[n].geoId`
- .geo_index: number - Echarts: `options.series[n].geoIndex`
- .matrix_id=undefined: string|undefined - Echarts: `options.series[n].matrixId`
- .matrix_index: number - Echarts: `options.series[n].matrixIndex`
  
  **Events:**
- .onblur - Object - Echarts: `options.series[n].blur`. Available when `.symbol.onhover.focus` is set.
	- .end_label_symbol: [[Echarts Label Symbol]] - Echarts: `options.series[n].blur.endLabel`
	- .fill_symbol: [[Echarts Fill Symbol]] - Echarts: `options.series[n].blur.areaStyle`
	- .label_symbol: [[Echarts Label Symbol]] - Echarts: `options.series[n].blur.label`
	- .label_stroke_symbol: [[Echarts Stroke Symbol]] - Echarts: `options.series[n].blur.labelLine.lineStyle`
	- .point_symbol: [[Echarts Point Symbol]] - Echarts: `options.series[n].blur.itemStyle`
	- .stroke_symbol: [[Echarts Stroke Symbol]] - Echarts: `options.series[n].blur.lineStyle`
- .onhover: Object - Echarts: `options.series[n].emphasis`. If undefined, onhover effects are disabled by default.
	- .focus="series": string - Echarts: `options.series[n].emphasis.focus` - Either 'series'/'self'.
	- .highlight=true: boolean - Echarts: `options.series[n].legendHoverLink`
	- .scale=true|1.1: boolean|number - Echarts: `options.series[n].emphasis.scale`
	  
	- .blur_scope="coordinateSystem": string - Echarts: `options.series[n].emphasis.blurScope` - Either 'coordinateSystem'/'series'/'global'
	  
	- .end_label_symbol: [[Echarts Label Symbol]] - Echarts: `options.series[n].emphasis.endLabel`
	- .fill_symbol: [[Echarts Fill Symbol]] - Echarts: `options.series[n].emphasis.areaStyle`
	- .label_symbol: [[Echarts Label Symbol]] - Echarts: `options.series[n].emphasis.label`
	- .point_symbol: [[Echarts Point Symbol]] - Echarts: `options.series[n].emphasis.itemStyle`
	- .stroke_symbol: [[Echarts Stroke Symbol]] - Echarts: `options.series[n].emphasis.lineStyle`
- .onselect: Object - Echarts: `options.series[n].select`. Available when `.symbol.onselect.select_mode` is set.
	- .select_mode=false: boolean|string - Echarts: `options.series[n].selectedMode` - Either 'disabled'/single'/'multiple'/'series'
	  
	- .end_label_symbol: [[Echarts Label Symbol]] - Echarts: `options.series[n].select.endLabel`
	- .fill_symbol: [[Echarts Fill Symbol]] - Echarts: `options.series[n].select.areaStyle`
	- .label_symbol: [[Echarts Label Symbol]] - Echarts: `options.series[n].select.label`
	- .label_stroke_symbol: [[Echarts Stroke Symbol]] - Echarts: `options.series[n].select.labelLine.lineStyle`
	- .point_symbol: [[Echarts Point Symbol]] - Echarts: `options.series[n].select.itemStyle`
	- .stroke_symbol: [[Echarts Stroke Symbol]] - Echarts: `options.series[n].select.lineStyle`
  
  **Tooltip**
- .tooltip: Object - Tooltips are disabled if undefined.
	- .label_symbol: [[Echarts Label Symbol]] - Echarts: `options.series[n].tooltip.textStyle`
	- ...[[Echarts Tooltip Symbol]]: Object - Echarts: `options.series[n].tooltip`
	  
  **Optimisation:**
- .large=false: boolean - Echarts: `options.series[n].large`
- .large_threshold=400: number - Echarts: `options.series[n].largeThreshold`
- .progressive=5000: number - Echarts: `options.series[n].progressive`
- .progressive_chunk_mode="mod" - Echarts: `options.series[n].progressiveThreshold`. Either 'mod'/'sequential'.
- .progressive_threshold=3000: number - Echarts: `options.series[n].progressiveThreshold`