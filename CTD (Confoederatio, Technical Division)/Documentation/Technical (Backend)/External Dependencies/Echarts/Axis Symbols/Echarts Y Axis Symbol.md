Known by Echarts as `yAxis`.

- .id: string|undefined - Echarts: `options.yAxis.id`
- .show=true: boolean - Echarts: `options.yAxis.show`
  
- .name: string - Echarts: `options.yAxis.name`
- .name_gap=15: number - Echarts: `options.yAxis.nameGap`
- .name_location: string - Echarts: `options.yAxis.nameEnd` - Either 'start'/'middle'/'end'.
- .name_move_overlap=true: boolean - Echarts: `options.yAxis.nameMoveOverlap`
- .name_rotate: number - Echarts: `options.yAxis.nameRotate`
- .name_truncate: Object - Echarts: `options.yAxis.nameTruncate`
	- .ellipsis="...": string - Echarts: `options.yAxis.nameTruncate.ellipsis`
	- .max_width: number - Echarts: `options.yAxis.nameTruncate.maxWidth`
- .type="category": string - Echarts: `options.yAxis.type` - Either 'value'/'category'/'time'/'log'.

- .data: Object[]|string[] - Echarts: `options.yAxis.data`
	- [n].label_symbol: Object - Echarts: `options.yAxis.data[n].labelSymbol`
		- ...[[Echarts Label Symbol]]
	- [n].value: string - Echarts: `options.yAxis.data[n].value`

- .axis_label: Object - Echarts: `options.yAxis.axisLabel`
	- .show=true: boolean - Echarts: `options.yAxis.axisLabel.show`
	  
	- .align_max_label: string - Echarts: `options.yAxis.axisLabel.alignMaxLabel`. Either 'left'/'center'/'right'/null.
	- .align_min_label: string - Echarts: `options.yAxis.axisLabel.alignMinLabel`. Either 'left'/'center'/'right'/null.
	- .custom_values: number[] - Echarts: `options.yAxis.axisLabel.customValues`
	- .formatter: string - Echarts: `options.yAxis.axisLabel.formatter`. Valid variables: {value}, {index}, {extraZ}, as well as time variables (i.e. {YYYY}) for 'time' axis.
	- .hide_overlap=false - Echarts: `options.yAxis.axisLabel.hideOverlap`
	- .inside=false: boolean - Echarts: `options.yAxis.axisLabel.inside`
	- .interval="auto": string|number|function - Echarts: `options.yAxis.axisLabel.interval` - If a function, must return a number.
	- .margin=0: number - Echarts: `options.yAxis.axisLabel.margin`
	- .rotate=0: number - Echarts: `options.yAxis.axisLabel.rotate`
	- .show_max_label=false: boolean - Echarts: `options.yAxis.axisLabel.showMaxLabel`
	- .show_min_label=false: boolean - Echarts: `options.yAxis.axisLabel.showMinLabel`
	- ...[[Echarts Label Symbol]]
	- ...[[Echarts Stroke Symbol]]
- .axis_line: Object - Echarts: `options.yAxis.axisLine`
	- .show=true: boolean - Echarts: `options.yAxis.axisLine.show`
	  
	- .on_zero=true: boolean - Echarts: `options.yAxis.axisLine.onZero`
	- .on_zero_axis_index: number - Echarts: `options.yAxis.axisLine.onZeroAxisIndex`
	- .stroke_symbol: Object - Echarts: `options.yAxis.axisLine.lineStyle`
		- ...[[Echarts Stroke Symbol]]
	- .symbol="none": string|Array<string, string> - Echarts: `options.yAxis.axisLine.symbol` - Either 'none'/'arrow' for string arguments.
	- .symbol_size=\[10, 15]: Array<number, number> - Echarts: `options.yAxis.axisLine.symbolSize`
	- .symbol_offset=\[0, 0]: Array<number, number> - Echarts: `options.yAxis.axisLine.symbolOffset`
- .axis_pointer - Object - Echarts: `options.yAxis.axisPointer`
	- .show=false: boolean - Echarts: `options.yAxis.axisPointer.show`
	  
	- .label_symbol: Object - Echarts: `options.yAxis.axisPointer.label`
		- ...[[Echarts Label Symbol]]
	- .on_hover_emphasis=true: boolean - Echarts: `options.yAxis.axisPointer.triggerEmphasis
	- .on_hover_tooltip=true: boolean - Echarts: `options.yAxis.axisPointer.triggerTooltip`
	- .shadow_blur: number - Echarts `options.yAxis.axisPointer.shadowStyle.shadowBlur`
	- .shadow_colour="#000": string - Echarts: `options.yAxis.axisPointer.shadowStyle.shadowColor`
	- .shadow_offset_x: number - Echarts: `options.yAxis.axisPointer.shadowStyle.shadowOffsetX`
	- .shadow_offset_y: number - Echarts: `options.yAxis.axisPointer.shadowStyle.shadowOffsetY
	- .snap_to=false: boolean - Echarts: `options.yAxis.axisPointer.snap`
	- .status=false: boolean - Echarts: `options.yAxis.axisPointer.status`
	- .stroke_symbol: Object - Echarts: `options.yAxis.axisPointer.lineStyle`
		- ...[[Echarts Stroke Symbol]]
	- .type="line": string - Echarts: `options.yAxis.axisPointer.type` - Either 'line'/'shadow'/'none'.
	- .value: number - Echarts: `options.yAxis.axisPointer.value`
	- .z_index: number - Echarts: `options.yAxis.axisPointer.z`
- .axis_tick: Object - Echarts: `options.yAxis.axisTick`
	- .show=true: boolean - Echarts: `options.yAxis.axisTick.show`
	  
	- .align_with_label=false: boolean - Echarts: `options.yAxis.axisTick.alignWithLabel`
	- .custom_values: number[] - Echarts: `options.yAxis.axisTick.customValues`
	- .inside=false: boolean - Echarts: `options.yAxis.axisTick.inside`
	- .interval="auto": number|function|string - Echarts: `options.yAxis.axisTick.interval`. If a function, it must return a number.
	- .length=5: number - Echarts: `options.yAxis.axisTick.number`
	- .stroke_symbol: Object - Echarts: `options.yAxis.axisTick.lineStyle`
		- ...[[Echarts Stroke Symbol]]
- .move_overlap="auto": string|boolean - Echarts: `options.yAxis.breakLabelLayout.moveOverlap` - Either 'auto'/true/false.
- .minor_split_line: Object - Echarts: `options.yAxis.minorSplitLine`
	- .show=false: boolean - Echarts: `options.yAxis.minorSplitLine.show`
	- .stroke_symbol: Object - Echarts: `options.yAxis.minorSplitLine.lineStyle`
		- ...[[Echarts Stroke Symbol]]
- .minor_tick: Object - Echarts: `options.yAxis.minorTick`
	- .show=false: boolean - Echarts: `options.yAxis.minorTick.show`
	  
	- .length=3: number - Echarts: `options.yAxis.minorTick.length`
	- .split_number=5: number - Echarts: `options.yAxis.minorTick.splitNumber`
	- .stroke_symbol: Object - Echarts: `options.yAxis.minorTick.lineStyle`
		- ....[[Echarts Stroke Symbol]]
- .split_area: Object - Echarts: `options.yAxis.splitArea`
	- .show=false: boolean - Echarts: `options.yAxis.splitArea.show`
	  
	- .fill_symbol: Object - Echarts: `options.yAxis.splitArea.areaStyle`
		- ...[[Echarts Fill Symbol]]
	- .interval="auto": number|function - Echarts: `options.yAxis.splitArea.interval`. If a function, must return a number.
- .split_line: Object - Echarts: `options.yAxis.splitLine`
	- show=true: boolean - Echarts: `options.yAxis.splitLine.show`
	  
	- .interval="auto": number|function - Echarts: `options.yAxis.splitLine.interval`. If a function, must return a number.
	- .show_max_line=true: boolean - Echarts: `options.yAxis.splitLine.showMaxLine`
	- .show_min_line=true: boolean - Echarts: `options.yAxis.splitLine.showMinLine`
	- .stroke_symbol: Object - Echarts: `options.yAxis.splitLine.lineStyle`
		- ....[[Echarts Stroke Symbol]]

- .break_area: Object - Echarts: `options.yAxis.breakArea` [WIP]
	- .show=true: boolean - Echarts: `options.yAxis.breakArea.show`
	  
	- .expand_on_click=true: boolean - Echarts: `options.yAxis.breakArea.expandOnClick`
	- .point_symbol: Object - Echarts: `options.yAxis.breakArea.itemStyle`
		- ...[[Echarts Point Symbol]]
	- .zigzag_amplitude=4: number - Echarts: `options.yAxis.breakArea.zigzagAmplitude`
	- .zigzag_max_span=4: number - Echarts: `options.yAxis.breakArea.zigzagMaxSpan
	- .zigzag_min_span=4: number - Echarts: `options.yAxis.breakArea.zigzagMinSpan
	- .zigzag_z_index=100: number - Echarts: `options.yAxis.breakArea.zigzagZ
- .breaks: Array\<Object\> - Echarts: `options.yAxis.breaks`
	- .breaks[n].gap: number|string - Echarts: `options.yAxis.breaks[n].gap`
	- .breaks[n].end: Date|number|string - Echarts: `options.yAxis.breaks[n].end`
	- .breaks[n].is_expanded: boolean - Echarts: `options.yAxis.breaks[n].isExpanded`
	- .breaks[n].start: Date|number|string - Echarts: `options.yAxis.breaks[n].start
  
- .align_ticks=true: boolean - Echarts: `options.yAxis.alignTicks`
- .boundary_gap: boolean|Array<string, string> - Echarts: `options.yAxis.boundaryGap`
- .grid_index: number - Echarts: `options.yAxis.gridIndex`
- .interactive=true: boolean - Echarts: `options.yAxis.triggerEvent`
- .interval: number - Echarts: `options.yAxis.interval`
- .inverse=false: boolean - Echarts: `options.yAxis.inverse`
- .log_base=10: number - Echarts: `options.yAxis.logBase`
- .jitter=false: boolean - Echarts: `options.yAxis.jitter` - Applicable only to [[Echarts Scatterplot]]
- .jitter_margin=2: number - Echarts: `options.yAxis.jitterMargin` - Applicable only to [[Echarts Scatterplot]]
- .jitter_overlap=true: boolean - Echarts: `options.yAxis.jitterOverlap` - Applicable only to [[Echarts Scatterplot]]
- .max: number|string|function - Echarts: `options.yAxis.max` - If a function, must return a number.
- .max_interval: number - Echarts: `options.yAxis.maxInterval`
- .min: number|string|function - Echarts: `options.yAxis.min` - If a function, must return a number.
- .min_interval: number - Echarts: `options.yAxis.minInterval`
- .offset=0: number - Echarts: `options.yAxis.offset`
- .scale=false: boolean - Echarts: `options.yAxis.scale`
- .silent=false: boolean - Echarts: `options.yAxis.silent`
- .split_number=5: number - Echarts: `options.yAxis.splitNumber`
- .start_value: number - Echarts: `options.yAxis.startValue`
- .text_symbol: Object - Echarts: `options.yAxis.nameTextStyle`
	- ...[[Echarts Text Symbol]]
- .z_index: number - Echarts: `options.yAxis.z`

- .tooltip: Object - Echarts: `options.yAxis.tooltip
	- .label_symbol: [[Echarts Label Symbol]] - Echarts: `options.yAxis.tooltip.textStyle`
	- ...[[Echarts Tooltip Symbol]]: Object - Echarts: `yAxis.tooltip`

- .animation: Object - Echarts: `options.yAxis`
	- delay=0: function|number - Echarts: `options.yAxis.animationDelay` - If a function, must return a number.
	- delay_update=300: function|number - Echarts `options.yAxis.animationDelayUpdate`
	- duration=1000: function|number - Echarts: `options.yAxis.animationDuration` - If a function, must return a number.
	- duration_update=300: function|number - Echarts: `options.yAxis.animationDurationUpdate`
	- easing="cubicOut": string - Echarts: `options.yAxis.animationEasing` - Easing effects must be predefined, see [Echarts Easing Examples](https://echarts.apache.org/examples/en/editor.html?c=line-easing)
	- easing_update="cubicOut": string - Echarts: `options.yAxis.animationEasingUpdate` - Easing effects must be predefined, see [Echarts Easing Examples](https://echarts.apache.org/examples/en/editor.html?c=line-easing)

**Unique to Y Axis:**
- .position: string - Echarts: `options.yAxis.position`. Either 'left'/'right'.