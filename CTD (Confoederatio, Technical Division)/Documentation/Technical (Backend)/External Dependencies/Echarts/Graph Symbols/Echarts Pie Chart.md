Known in Echarts as 'pie'.

- .clockwise=true: boolean - Echarts: `options.series[n].clockwise`
- .empty_circle_style: Object - Echarts: `options.series[n].emptyCircleStyle`
	- ...[[Echarts Stroke Symbol]]
- .end_angle="auto": number|string - Echarts: `options.series[n].endAngle` - If a string, must be 'auto'.
- .min_angle: number - Echarts: `options.series[n].minAngle`
- .min_show_label_angle: number - Echarts: `options.series[n].minShowLabelAngle`
- .rose_type: boolean|string - Echarts: `options.series[n].roseType` - If a string, must either be 'radius'/'area'.
- .pad_angle: number - Echarts: `options.series[n].padAngle`
- .start_angle=90: number - Echarts: `options.series[n].startAngle`
  
  **Behaviour:**
- .avoid_label_overlap=true: boolean - Echarts: `options.series[n].avoidLabelOverlap`
- .cursor="pointer"
- .percent_precision=2: number - Echarts: `options.series[n].percentPrecision`
- .show_empty_circle=true: boolean - Echarts: `options.series[n].showEmptyCircle`
- .still_show_zero_sum=true: boolean - Echarts: `options.series[n].stillShowZeroSum`
  
  **Events:**

- .onselect: Object
	- .selected_offset=10: number - Echarts: `options.series[n].selectedOffset`