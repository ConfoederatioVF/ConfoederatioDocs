Known by Echarts as `polar`, without an `Axis` suffix.

- .id: string - Echarts: `options.polar.id`
  
- .center=\["50%", "50%"\]: Array<string, string>|Array<number, number> - Echarts: `options.polar.center`
- .coordinate_system="none": string - Echarts: `options.polar.coordinateSystem`. Either 'none'/'calendar'/'matrix'.
- .radius: number|string|Array<number|string, number|string> - Echarts: `options.polar.radius`
- .z_index=2: number - Echarts: `options.polar.z`

- .calendar_id: number - Echarts: `options.polar.calendarId`
- .calendar_index: number - Echarts: `options.polar.calendarIndex`
- .matrix_id: number - Echarts: `options.polar.matrixId`
- .matrix_index: number - Echarts: `options.polar.matrixIndex`

**Tooltip**
- .tooltip: Object - Tooltips are disabled if undefined.
	- .label_symbol: [[Echarts Label Symbol]] - Echarts: `options.polar.tooltip.textStyle`
	- ...[[Echarts Tooltip Symbol]]: Object - Echarts: `options.polar.tooltip`