Known by Echarts as 'treemap' internally.

- .drill_down_icon="▶": string - Echarts: `options.series[n].drillDownIcon`
- .leaf_depth=null|undefined: number - Echarts: `options.series[n].leafDepth` - The default drill down depth.
- .node_click="zoomToNode": boolean|string - Echarts: `options.series[n].nodeClick` - Either false/'zoomToNode'/'link'.
- .scale_limit_max: number - Echarts: `options.series[n].scaleLimit.max`
- .scale_limit_min: number - Echarts: `options.series[n].scaleLimit.min`
- .square_ratio=0.5*(1 + Math.sqrt(5)): number - Echarts: `options.series[n].squareRatio` - The expected square ratio. Layout approaches the ratio as close as possible.
- .zoom_to_node_ratio=0.32\*0.32: number - Echarts: `options.series[n].zoomToNodeRatio`

- .children_visible_min: number - Echarts: `options.series[n].childrenVisibleMin`
- .colour_alpha: Array<number, number> - Echarts: `options.series[n].colorAlpha`
- .colour_map_by="index": string - Echarts: `options.series[n].colorMappingBy` - Either 'index'/'value'/'id'.
- .colour_saturation: Array<number, number> - Echarts: `options.series[n].colorSaturation`
- .visible_min=10: number - Echarts: `options.series[n].visibleMin`
- .visual_dimension: number - Echarts: `options.series[n].visualDimension`
- .visual_max: number - Echarts: `options.series[n].visualMax`
- .visual_min: number - Echarts: `options.series[n].visualMin`