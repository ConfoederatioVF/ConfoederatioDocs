[![echarts logo](https://echarts.apache.org/en/images/logo.png?_v_=20240226)](https://echarts.apache.org/en/index.html)

> [!NOTE]
> If you are looking for Echarts-[[Vercengen]] bindings, please view [[Echarts Bindings]].

- [Home](https://echarts.apache.org/en/index.html)
- [Docs](https://echarts.apache.org/en/feature.html#)
- [Download](https://echarts.apache.org/en/feature.html#)
- [Examples](https://echarts.apache.org/examples/en/index.html)
- [Resources](https://echarts.apache.org/en/feature.html#)
- [Community](https://echarts.apache.org/en/feature.html#)
- [ASF](https://echarts.apache.org/en/feature.html#)

- 中文
- [](https://github.com/apache/echarts)

# Features

Apache EChartsTM

#### Features

- [Abundant Chart Types](https://echarts.apache.org/en/feature.html#chart-types)
- [Multiple Data Format Ready-To-Use](https://echarts.apache.org/en/feature.html#dataset)
- [Large-Scale Data Visualizations](https://echarts.apache.org/en/feature.html#big-data)
- [Mobile Optimization](https://echarts.apache.org/en/feature.html#mobile)
- [Multiple Rendering Methods and Cross-Platform Support](https://echarts.apache.org/en/feature.html#mult-platform)
- [Interactive Data Exploration](https://echarts.apache.org/en/feature.html#interaction)
- [Multi-Dimensional Data Support](https://echarts.apache.org/en/feature.html#visual-mapping)
- [Dynamic Data](https://echarts.apache.org/en/feature.html#dynamic-data)
- [Special Effects](https://echarts.apache.org/en/feature.html#fancy-effects)
- [More Powerful 3D Visualizations with GL](https://echarts.apache.org/en/feature.html#gl)
- [Accessibility](https://echarts.apache.org/en/feature.html#aria)

Apache EChartsTM is an open-source JavaScript visualization library, optimized for both PC and mobile devices. Compatible with most modern web browsers, including IE9/10/11, Chrome, Firefox and Safari, ECharts uses [ZRender](https://github.com/ecomfe/zrender), a graphic rendering engine, to create intuitive, interactive, and highly-customizable charts.

## Abundant Chart Types

ECharts supports [line series](https://echarts.apache.org/en/option.html#series-line), [bar series](https://echarts.apache.org/en/option.html#series-bar), [scatter series](https://echarts.apache.org/en/option.html#series-scatter), [pie charts](https://echarts.apache.org/en/option.html#series-pie), [candle-stick series](https://echarts.apache.org/en/option.html#series-candlestick), [boxplot series](https://echarts.apache.org/en/option.html#series-boxplot) for statistics, [map series](https://echarts.apache.org/en/option.html#series-map), [heatmap series](https://echarts.apache.org/en/option.html#series-heatmap), [lines series](https://echarts.apache.org/en/option.html#series-lines) for directional information, [graph series](https://echarts.apache.org/en/option.html#series-graph) for relationships, [treemap series](https://echarts.apache.org/en/option.html#series-treemap), [sunburst series](https://echarts.apache.org/en/option.html#series-sunburst), [parallel series](https://echarts.apache.org/en/option.html#series-parallel) for multi-dimensional data, [funnel series](https://echarts.apache.org/en/option.html#series-funnel) and [gauge series](https://echarts.apache.org/en/option.html#series-gauge). It's easy to create combinations of these visualization types with ECharts.

Besides the built-in chart types, ECharts also provides a [custom series](https://echarts.apache.org/en/option.html#series-custom) for users to create more specific chart types. To use it, just pass the _renderItem_ callback function and return any graphic elements you wish to draw, according to the data. ECharts supports native interactivity and so there is no need for further configuration.

ECharts is highly optimised, but if the default package size is too large for you, you can select the chart types and components you need and download them via [the online builder](https://echarts.apache.org/en/builder.html).

## Multiple Data Format Ready-To-Use

The built-in `dataset` attribute from ECharts v4.0 supports different data formats, including two-dimensional tables, key-value objects, and more. Data mapping structures can easily be modified with the `encode` attribute. This makes developing charts much more intuitive, saving time normally spent writing data conversion algorithms. It also saves memory as different components can rely on one dataset rather than multiple copies.

ECharts supports `TypedArray`, which uses less memory than a standard array and works better with garbage collection. For larger data visualization, TypedArray significantly improves performance.

## Large-Scale Data Visualizations

EChart v4.0's incremental rendering technique and other optimizations allows it to visualize millions of data points. Interactions like scaling and panning continue to work well even with these large-scale visualizations.

Using this many data points is usually very memory intensive. ECharts supports streaming data since v4.0, allowing you to render as much data as possible using WebSocket. Data can be rendered even when the complete dataset has not yet loaded.

![](https://echarts.apache.org/en/images/features/scatterGL.jpg?_v_=20240226)  
![](https://echarts.apache.org/en/images/features/scatterGL2.jpg?_v_=20240226)![](https://echarts.apache.org/en/images/features/scatterGL3.jpg?_v_=20240226)

## Mobile Optimization

ECharts has been carefully optimized for mobile interaction, such as zooming and panning on small screens. PC users can still use the mouse wheel to perform the same interactions.

The packaging utility allows ECharts to have a small package size on mobile, with the optional SVG rendering engine further reducing memory usage.

## Multiple Rendering Methods and Cross-Platform Support

ECharts supports rendering with Canvas, SVG (v4.0+), and VML elements. VML is compatible with older versions of IE; SVG reduces the memory cost on mobiles; and Canvas can easily handle large data visualization and special rendering effects.

In addition to PC and mobile browsers, ECharts can also be used with node-canvas on Node for efficient server-side rendering (SSR). It also supports [WeChat MiniProgram](https://github.com/ecomfe/echarts-for-weixin) since v4.0.

Community contributors also develop [extensions for various programming languages](https://echarts.apache.org/en/download-extension.html), such as [pyecharts](https://github.com/pyecharts/pyecharts) for Python, [echarty](https://github.com/helgasoft/echarty) for R and [ECharts.jl](https://github.com/randyzwitch/ECharts.jl) for Julia.

With our wide platform and programming language support, ECharts lets developers focus on the visualisation, rather than the technical details.

## Interactive Data Exploration

Interaction is key to understanding data. On initial view, ECharts provides an overview that can be zoomed, panned and filtered to provide more granular information.

Optional elements can be enabled to further interactivity. The [legend](https://echarts.apache.org/en/option.html#legend), [visualMap](https://echarts.apache.org/en/option.html#visualMap), [dataZoom](https://echarts.apache.org/en/option.html#dataZoom), [tooltip](https://echarts.apache.org/en/option.html#tooltip), [brush](https://echarts.apache.org/en/option.html#brush) and other ready-to-use components allow users to interact with data in multiple dimensions.

## Multi-Dimensional Data Support

ECharts 3 strengthened support for multi-dimensional data. In addition to common multi-dimensional data visualization elements, such as parallel coordinates for traditional scatter plots, the input data can also be rendered in multiple dimensions. With the intuitive functions provided by the visual mapping component [visualMap](https://echarts.apache.org/en/option.html#visualMap), different dimensions can be mapped to color, size, transparency, shading and more.

## Dynamic Data

Changes in the underlying dataset will be reflected in real time on charts. Implementing dynamic data is simple, just import the data as normal and ECharts will automatically find the difference between the two sets of data and then use the appropriate animation to represent the data changes. The [timeline](https://echarts.apache.org/en/option.html#timeline) component can present data in other time dimensions as well.

## Special Effects

ECharts provides eye-catching effects for the visualization of all data types, whether point, line or geographic.

## More Powerful 3D Visualizations with GL

ECharts even allows you to perform 3D visualizations in VR and other large screen scenes. The WebGL-based ECharts GL lets you render a 3D Earth, buildings, and population distribution histograms as easily as other ECharts components. To add, simple configuration items let you add effects with just a few lines of configuration changes.

![](https://echarts.apache.org/en/images/features/flowGL-line.jpg?_v_=20240226)![](https://echarts.apache.org/en/images/features/buildings-ny.jpg?_v_=20240226)  
![](https://echarts.apache.org/en/images/features/capetown-taxi.jpg?_v_=20240226)![](https://echarts.apache.org/en/images/features/population.jpg?_v_=20240226)

## Accessibility

When thinking about a visualization, we naturally associate it with what you see, but there are other dimensions to viewing. The W3C has developed the Accessible Rich Internet Applications Suite (WAI-ARIA), which aims to make web content and web applications accessible to more people with disabilities.

ECharts 4.0 complies with this specification and supports automatic generation of descriptions based on chart configuration items, enabling people with visual disabilities to understand the chart content with screenreaders, so that charts are accessible to all.

Copyright © 2017-2025, The Apache Software Foundation. Apache ECharts, ECharts, Apache, the Apache logo, and the Apache ECharts project logo are either registered trademarks or trademarks of the Apache Software Foundation.

[![](https://echarts.apache.org/en/images/asf_logo.svg?_v_=20240226)](https://www.apache.org)