Known by Echarts as `xAxis`.

- .id: string|undefined - Echarts: `options.xAxis.id`
- .show=true: boolean - Echarts: `options.xAxis.show`
  
- .name: string - Echarts: `options.xAxis.name`
- .name_gap=15: number - Echarts: `options.xAxis.nameGap`
- .name_location: string - Echarts: `options.xAxis.nameEnd` - Either 'start'/'middle'/'end'.
- .name_move_overlap=true: boolean - Echarts: `options.xAxis.nameMoveOverlap`
- .name_rotate: number - Echarts: `options.xAxis.nameRotate`
- .name_truncate: Object - Echarts: `options.xAxis.nameTruncate`
	- .ellipsis="...": string - Echarts: `options.xAxis.nameTruncate.ellipsis`
	- .max_width: number - Echarts: `options.xAxis.nameTruncate.maxWidth`
- .type="category": string - Echarts: `options.xAxis.type` - Either 'value'/'category'/'time'/'log'.

- .data: Object[]|string[] - Echarts: `options.xAxis.data`
	- [n].label_symbol: Object - Echarts: `options.xAxis.data[n].labelSymbol`
		- ...[[Echarts Label Symbol]]
	- [n].value: string - Echarts: `options.xAxis.data[n].value`

- .axis_label: Object - Echarts: `options.xAxis.axisLabel`
	- .show=true: boolean - Echarts: `options.xAxis.axisLabel.show`
	  
	- .align_max_label: string - Echarts: `options.xAxis.axisLabel.alignMaxLabel`. Either 'left'/'center'/'right'/null.
	- .align_min_label: string - Echarts: `options.xAxis.axisLabel.alignMinLabel`. Either 'left'/'center'/'right'/null.
	- .custom_values: number[] - Echarts: `options.xAxis.axisLabel.customValues`
	- .formatter: string - Echarts: `options.xAxis.axisLabel.formatter`. Valid variables: {value}, {index}, {extraZ}, as well as time variables (i.e. {YYYY}) for 'time' axis.
	- .hide_overlap=false - Echarts: `options.xAxis.axisLabel.hideOverlap`
	- .inside=false: boolean - Echarts: `options.xAxis.axisLabel.inside`
	- .interval="auto": string|number|function - Echarts: `options.xAxis.axisLabel.interval` - If a function, must return a number.
	- .margin=0: number - Echarts: `options.xAxis.axisLabel.margin`
	- .rotate=0: number - Echarts: `options.xAxis.axisLabel.rotate`
	- .show_max_label=false: boolean - Echarts: `options.xAxis.axisLabel.showMaxLabel`
	- .show_min_label=false: boolean - Echarts: `options.xAxis.axisLabel.showMinLabel`
	- ...[[Echarts Label Symbol]]
	- ...[[Echarts Stroke Symbol]]
- .axis_line: Object - Echarts: `options.xAxis.axisLine`
	- .show=true: boolean - Echarts: `options.xAxis.axisLine.show`
	  
	- .on_zero=true: boolean - Echarts: `options.xAxis.axisLine.onZero`
	- .on_zero_axis_index: number - Echarts: `options.xAxis.axisLine.onZeroAxisIndex`
	- .stroke_symbol: Object - Echarts: `options.xAxis.axisLine.lineStyle`
		- ...[[Echarts Stroke Symbol]]
	- .symbol="none": string|Array<string, string> - Echarts: `options.xAxis.axisLine.symbol` - Either 'none'/'arrow' for string arguments.
	- .symbol_size=\[10, 15]: Array<number, number> - Echarts: `options.xAxis.axisLine.symbolSize`
	- .symbol_offset=\[0, 0]: Array<number, number> - Echarts: `options.xAxis.axisLine.symbolOffset`
- .axis_pointer - Object - Echarts: `options.xAxis.axisPointer`
	- .show=false: boolean - Echarts: `options.xAxis.axisPointer.show`
	  
	- .label_symbol: Object - Echarts: `options.xAxis.axisPointer.label`
		- ...[[Echarts Label Symbol]]
	- .on_hover_emphasis=true: boolean - Echarts: `options.xAxis.axisPointer.triggerEmphasis
	- .on_hover_tooltip=true: boolean - Echarts: `options.xAxis.axisPointer.triggerTooltip`
	- .shadow_blur: number - Echarts `options.xAxis.axisPointer.shadowStyle.shadowBlur`
	- .shadow_colour="#000": string - Echarts: `options.xAxis.axisPointer.shadowStyle.shadowColor`
	- .shadow_offset_x: number - Echarts: `options.xAxis.axisPointer.shadowStyle.shadowOffsetX`
	- .shadow_offset_y: number - Echarts: `options.xAxis.axisPointer.shadowStyle.shadowOffsetY
	- .snap_to=false: boolean - Echarts: `options.xAxis.axisPointer.snap`
	- .status=false: boolean - Echarts: `options.xAxis.axisPointer.status`
	- .stroke_symbol: Object - Echarts: `options.xAxis.axisPointer.lineStyle`
		- ...[[Echarts Stroke Symbol]]
	- .type="line": string - Echarts: `options.xAxis.axisPointer.type` - Either 'line'/'shadow'/'none'.
	- .value: number - Echarts: `options.xAxis.axisPointer.value`
	- .z_index: number - Echarts: `options.xAxis.axisPointer.z`
- .axis_tick: Object - Echarts: `options.xAxis.axisTick`
	- .show=true: boolean - Echarts: `options.xAxis.axisTick.show`
	  
	- .align_with_label=false: boolean - Echarts: `options.xAxis.axisTick.alignWithLabel`
	- .custom_values: number[] - Echarts: `options.xAxis.axisTick.customValues`
	- .inside=false: boolean - Echarts: `options.xAxis.axisTick.inside`
	- .interval="auto": number|function|string - Echarts: `options.xAxis.axisTick.interval`. If a function, it must return a number.
	- .length=5: number - Echarts: `options.xAxis.axisTick.number`
	- .stroke_symbol: Object - Echarts: `options.xAxis.axisTick.lineStyle`
		- ...[[Echarts Stroke Symbol]]
- .move_overlap="auto": string|boolean - Echarts: `options.xAxis.breakLabelLayout.moveOverlap` - Either 'auto'/true/false.
- .minor_split_line: Object - Echarts: `options.xAxis.minorSplitLine`
	- .show=false: boolean - Echarts: `options.xAxis.minorSplitLine.show`
	- .stroke_symbol: Object - Echarts: `options.xAxis.minorSplitLine.lineStyle`
		- ...[[Echarts Stroke Symbol]]
- .minor_tick: Object - Echarts: `options.xAxis.minorTick`
	- .show=false: boolean - Echarts: `options.xAxis.minorTick.show`
	  
	- .length=3: number - Echarts: `options.xAxis.minorTick.length`
	- .split_number=5: number - Echarts: `options.xAxis.minorTick.splitNumber`
	- .stroke_symbol: Object - Echarts: `options.xAxis.minorTick.lineStyle`
		- ....[[Echarts Stroke Symbol]]
- .split_area: Object - Echarts: `options.xAxis.splitArea`
	- .show=false: boolean - Echarts: `options.xAxis.splitArea.show`
	  
	- .fill_symbol: Object - Echarts: `options.xAxis.splitArea.areaStyle`
		- ...[[Echarts Fill Symbol]]
	- .interval="auto": number|function - Echarts: `options.xAxis.splitArea.interval`. If a function, must return a number.
- .split_line: Object - Echarts: `options.xAxis.splitLine`
	- show=true: boolean - Echarts: `options.xAxis.splitLine.show`
	  
	- .interval="auto": number|function - Echarts: `options.xAxis.splitLine.interval`. If a function, must return a number.
	- .show_max_line=true: boolean - Echarts: `options.xAxis.splitLine.showMaxLine`
	- .show_min_line=true: boolean - Echarts: `options.xAxis.splitLine.showMinLine`
	- .stroke_symbol: Object - Echarts: `options.xAxis.splitLine.lineStyle`
		- ....[[Echarts Stroke Symbol]]

- .break_area: Object - Echarts: `options.xAxis.breakArea` [WIP]
	- .show=true: boolean - Echarts: `options.xAxis.breakArea.show`
	  
	- .expand_on_click=true: boolean - Echarts: `options.xAxis.breakArea.expandOnClick`
	- .point_symbol: Object - Echarts: `options.xAxis.breakArea.itemStyle`
		- ...[[Echarts Point Symbol]]
	- .zigzag_amplitude=4: number - Echarts: `options.xAxis.breakArea.zigzagAmplitude`
	- .zigzag_max_span=4: number - Echarts: `options.xAxis.breakArea.zigzagMaxSpan
	- .zigzag_min_span=4: number - Echarts: `options.xAxis.breakArea.zigzagMinSpan
	- .zigzag_z_index=100: number - Echarts: `options.xAxis.breakArea.zigzagZ
- .breaks: Array\<Object\> - Echarts: `options.xAxis.breaks`
	- .breaks[n].gap: number|string - Echarts: `options.xAxis.breaks[n].gap`
	- .breaks[n].end: Date|number|string - Echarts: `options.xAxis.breaks[n].end`
	- .breaks[n].is_expanded: boolean - Echarts: `options.xAxis.breaks[n].isExpanded`
	- .breaks[n].start: Date|number|string - Echarts: `options.xAxis.breaks[n].start
  
- .align_ticks=true: boolean - Echarts: `options.xAxis.alignTicks`
- .boundary_gap: boolean|Array<string, string> - Echarts: `options.xAxis.boundaryGap`
- .grid_index: number - Echarts: `options.xAxis.gridIndex`
- .interactive=true: boolean - Echarts: `options.xAxis.triggerEvent`
- .interval: number - Echarts: `options.xAxis.interval`
- .inverse=false: boolean - Echarts: `options.xAxis.inverse`
- .log_base=10: number - Echarts: `options.xAxis.logBase`
- .jitter=false: boolean - Echarts: `options.xAxis.jitter` - Applicable only to [[Echarts Scatterplot]]
- .jitter_margin=2: number - Echarts: `options.xAxis.jitterMargin` - Applicable only to [[Echarts Scatterplot]]
- .jitter_overlap=true: boolean - Echarts: `options.xAxis.jitterOverlap` - Applicable only to [[Echarts Scatterplot]]
- .max: number|string|function - Echarts: `options.xAxis.max` - If a function, must return a number.
- .max_interval: number - Echarts: `options.xAxis.maxInterval`
- .min: number|string|function - Echarts: `options.xAxis.min` - If a function, must return a number.
- .min_interval: number - Echarts: `options.xAxis.minInterval`
- .offset=0: number - Echarts: `options.xAxis.offset`
- .scale=false: boolean - Echarts: `options.xAxis.scale`
- .silent=false: boolean - Echarts: `options.xAxis.silent`
- .split_number=5: number - Echarts: `options.xAxis.splitNumber`
- .start_value: number - Echarts: `options.xAxis.startValue`
- .text_symbol: Object - Echarts: `options.xAxis.nameTextStyle`
	- ...[[Echarts Text Symbol]]
- .z_index: number - Echarts: `options.xAxis.z`

- .tooltip: Object - Echarts: `options.xAxis.tooltip
	- .label_symbol: [[Echarts Label Symbol]] - Echarts: `options.xAxis.tooltip.textStyle`
	- ...[[Echarts Tooltip Symbol]]: Object - Echarts: `optionsxAxis.tooltip`

- .animation: Object - Echarts: `options.xAxis`
	- delay=0: function|number - Echarts: `options.xAxis.animationDelay` - If a function, must return a number.
	- delay_update=300: function|number - Echarts `options.xAxis.animationDelayUpdate`
	- duration=1000: function|number - Echarts: `options.xAxis.animationDuration` - If a function, must return a number.
	- duration_update=300: function|number - Echarts: `options.xAxis.animationDurationUpdate`
	- easing="cubicOut": string - Echarts: `options.xAxis.animationEasing` - Easing effects must be predefined, see [Echarts Easing Examples](https://echarts.apache.org/examples/en/editor.html?c=line-easing)
	- easing_update="cubicOut": string - Echarts: `options.xAxis.animationEasingUpdate` - Easing effects must be predefined, see [Echarts Easing Examples](https://echarts.apache.org/examples/en/editor.html?c=line-easing)

**Unique to X Axis:**
- .position: string - Echarts: `options.xAxis.position`. Either 'top'/'bottom'.