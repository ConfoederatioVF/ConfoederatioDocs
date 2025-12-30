> [!WARNING]
> This is an **exterior dependency**. Content has not been authored by members of *Confoederatio*, but rather the Turf.js team at [https://turfjs.org/](https://turfjs.org/).

#wip #exteriordependency
# Introduction

**_A modular geospatial engine written in JavaScript_**

---

[Turf](https://turfjs.org) is a [JavaScript library](https://en.wikipedia.org/wiki/JavaScript_library) for [spatial analysis](https://en.wikipedia.org/wiki/Spatial_analysis). It includes traditional spatial operations, helper functions for creating [GeoJSON](https://geojson.org) data, and data classification and statistics tools. Turf can be added to your website as a client-side plugin, or you can [run Turf server-side](https://www.npmjs.com/package/@turf/turf) with [Node.js](https://nodejs.org/).

[Skip to main content](https://turfjs.org/docs/next/api/along#__docusaurus_skipToContent_fallback)

![Turf.js Logo](https://turfjs.org/img/logo.svg)

**Turf.js**](https://turfjs.org/)[Docs](https://turfjs.org/docs/next/intro)[API](https://turfjs.org/docs/next/api/along)[Blog](https://turfjs.org/blog)

[GitHub](https://github.com/Turfjs/turf)

- [Measurement](https://turfjs.org/docs/next/api/along#)
    
    - [along](https://turfjs.org/docs/next/api/along)
    - [area](https://turfjs.org/docs/next/api/area)
    - [bbox](https://turfjs.org/docs/next/api/bbox)
    - [bboxPolygon](https://turfjs.org/docs/next/api/bboxPolygon)
    - [bearing](https://turfjs.org/docs/next/api/bearing)
    - [center](https://turfjs.org/docs/next/api/center)
    - [centerOfMass](https://turfjs.org/docs/next/api/centerOfMass)
    - [centroid](https://turfjs.org/docs/next/api/centroid)
    - [destination](https://turfjs.org/docs/next/api/destination)
    - [distance](https://turfjs.org/docs/next/api/distance)
    - [envelope](https://turfjs.org/docs/next/api/envelope)
    - [greatCircle](https://turfjs.org/docs/next/api/greatCircle)
    - [length](https://turfjs.org/docs/next/api/length)
    - [midpoint](https://turfjs.org/docs/next/api/midpoint)
    - [pointOnFeature](https://turfjs.org/docs/next/api/pointOnFeature)
    - [pointToLineDistance](https://turfjs.org/docs/next/api/pointToLineDistance)
    - [pointToPolygonDistance](https://turfjs.org/docs/next/api/pointToPolygonDistance)
    - [polygonTangents](https://turfjs.org/docs/next/api/polygonTangents)
    - [rhumbBearing](https://turfjs.org/docs/next/api/rhumbBearing)
    - [rhumbDestination](https://turfjs.org/docs/next/api/rhumbDestination)
    - [rhumbDistance](https://turfjs.org/docs/next/api/rhumbDistance)
    - [square](https://turfjs.org/docs/next/api/square)
- [Coordinate Mutation](https://turfjs.org/docs/next/api/along#)
    
    - [cleanCoords](https://turfjs.org/docs/next/api/cleanCoords)
    - [flip](https://turfjs.org/docs/next/api/flip)
    - [rewind](https://turfjs.org/docs/next/api/rewind)
    - [round](https://turfjs.org/docs/next/api/round)
    - [truncate](https://turfjs.org/docs/next/api/truncate)
- [Transformation](https://turfjs.org/docs/next/api/along#)
    
    - [bboxClip](https://turfjs.org/docs/next/api/bboxClip)
    - [bezierSpline](https://turfjs.org/docs/next/api/bezierSpline)
    - [buffer](https://turfjs.org/docs/next/api/buffer)
    - [circle](https://turfjs.org/docs/next/api/circle)
    - [clone](https://turfjs.org/docs/next/api/clone)
    - [concave](https://turfjs.org/docs/next/api/concave)
    - [convex](https://turfjs.org/docs/next/api/convex)
    - [difference](https://turfjs.org/docs/next/api/difference)
    - [dissolve](https://turfjs.org/docs/next/api/dissolve)
    - [intersect](https://turfjs.org/docs/next/api/intersect)
    - [lineOffset](https://turfjs.org/docs/next/api/lineOffset)
    - [polygonSmooth](https://turfjs.org/docs/next/api/polygonSmooth)
    - [simplify](https://turfjs.org/docs/next/api/simplify)
    - [tesselate](https://turfjs.org/docs/next/api/tesselate)
    - [transformRotate](https://turfjs.org/docs/next/api/transformRotate)
    - [transformScale](https://turfjs.org/docs/next/api/transformScale)
    - [transformTranslate](https://turfjs.org/docs/next/api/transformTranslate)
    - [union](https://turfjs.org/docs/next/api/union)
    - [voronoi](https://turfjs.org/docs/next/api/voronoi)
- [Feature Conversion](https://turfjs.org/docs/next/api/along#)
    
    - [combine](https://turfjs.org/docs/next/api/combine)
    - [explode](https://turfjs.org/docs/next/api/explode)
    - [flatten](https://turfjs.org/docs/next/api/flatten)
    - [lineToPolygon](https://turfjs.org/docs/next/api/lineToPolygon)
    - [polygonToLine](https://turfjs.org/docs/next/api/polygonToLine)
    - [polygonize](https://turfjs.org/docs/next/api/polygonize)
- [Misc](https://turfjs.org/docs/next/api/along#)
    
    - [kinks](https://turfjs.org/docs/next/api/kinks)
    - [lineArc](https://turfjs.org/docs/next/api/lineArc)
    - [lineChunk](https://turfjs.org/docs/next/api/lineChunk)
    - [lineIntersect](https://turfjs.org/docs/next/api/lineIntersect)
    - [lineOverlap](https://turfjs.org/docs/next/api/lineOverlap)
    - [lineSegment](https://turfjs.org/docs/next/api/lineSegment)
    - [lineSlice](https://turfjs.org/docs/next/api/lineSlice)
    - [lineSliceAlong](https://turfjs.org/docs/next/api/lineSliceAlong)
    - [lineSplit](https://turfjs.org/docs/next/api/lineSplit)
    - [mask](https://turfjs.org/docs/next/api/mask)
    - [nearestPointOnLine](https://turfjs.org/docs/next/api/nearestPointOnLine)
    - [sector](https://turfjs.org/docs/next/api/sector)
    - [shortestPath](https://turfjs.org/docs/next/api/shortestPath)
    - [unkinkPolygon](https://turfjs.org/docs/next/api/unkinkPolygon)
- [Helper](https://turfjs.org/docs/next/api/along#)
    
    - [feature](https://turfjs.org/docs/next/api/feature)
    - [featureCollection](https://turfjs.org/docs/next/api/featureCollection)
    - [geometryCollection](https://turfjs.org/docs/next/api/geometryCollection)
    - [lineString](https://turfjs.org/docs/next/api/lineString)
    - [multiLineString](https://turfjs.org/docs/next/api/multiLineString)
    - [multiPoint](https://turfjs.org/docs/next/api/multiPoint)
    - [multiPolygon](https://turfjs.org/docs/next/api/multiPolygon)
    - [point](https://turfjs.org/docs/next/api/point)
    - [polygon](https://turfjs.org/docs/next/api/polygon)
- [Random](https://turfjs.org/docs/next/api/along#)
    
    - [randomLineString](https://turfjs.org/docs/next/api/randomLineString)
    - [randomPoint](https://turfjs.org/docs/next/api/randomPoint)
    - [randomPolygon](https://turfjs.org/docs/next/api/randomPolygon)
    - [randomPosition](https://turfjs.org/docs/next/api/randomPosition)
- [Data](https://turfjs.org/docs/next/api/along#)
    
    - [sample](https://turfjs.org/docs/next/api/sample)
- [Interpolation](https://turfjs.org/docs/next/api/along#)
    
    - [interpolate](https://turfjs.org/docs/next/api/interpolate)
    - [isobands](https://turfjs.org/docs/next/api/isobands)
    - [isolines](https://turfjs.org/docs/next/api/isolines)
    - [planepoint](https://turfjs.org/docs/next/api/planepoint)
    - [tin](https://turfjs.org/docs/next/api/tin)
- [Joins](https://turfjs.org/docs/next/api/along#)
    
    - [pointsWithinPolygon](https://turfjs.org/docs/next/api/pointsWithinPolygon)
    - [tag](https://turfjs.org/docs/next/api/tag)
- [Grids](https://turfjs.org/docs/next/api/along#)
    
    - [hexGrid](https://turfjs.org/docs/next/api/hexGrid)
    - [pointGrid](https://turfjs.org/docs/next/api/pointGrid)
    - [squareGrid](https://turfjs.org/docs/next/api/squareGrid)
    - [triangleGrid](https://turfjs.org/docs/next/api/triangleGrid)
- [Classification](https://turfjs.org/docs/next/api/along#)
    
    - [nearestPoint](https://turfjs.org/docs/next/api/nearestPoint)
- [Aggregation](https://turfjs.org/docs/next/api/along#)
    
    - [clustersDbscan](https://turfjs.org/docs/next/api/clustersDbscan)
    - [clustersKmeans](https://turfjs.org/docs/next/api/clustersKmeans)
    - [collect](https://turfjs.org/docs/next/api/collect)
- [Meta](https://turfjs.org/docs/next/api/along#)
    
    - [clusterEach](https://turfjs.org/docs/next/api/clusterEach)
    - [clusterReduce](https://turfjs.org/docs/next/api/clusterReduce)
    - [coordAll](https://turfjs.org/docs/next/api/coordAll)
    - [coordEach](https://turfjs.org/docs/next/api/coordEach)
    - [coordReduce](https://turfjs.org/docs/next/api/coordReduce)
    - [featureEach](https://turfjs.org/docs/next/api/featureEach)
    - [featureReduce](https://turfjs.org/docs/next/api/featureReduce)
    - [flattenEach](https://turfjs.org/docs/next/api/flattenEach)
    - [flattenReduce](https://turfjs.org/docs/next/api/flattenReduce)
    - [geomEach](https://turfjs.org/docs/next/api/geomEach)
    - [geomReduce](https://turfjs.org/docs/next/api/geomReduce)
    - [getCluster](https://turfjs.org/docs/next/api/getCluster)
    - [getCoord](https://turfjs.org/docs/next/api/getCoord)
    - [getCoords](https://turfjs.org/docs/next/api/getCoords)
    - [getGeom](https://turfjs.org/docs/next/api/getGeom)
    - [getType](https://turfjs.org/docs/next/api/getType)
    - [propEach](https://turfjs.org/docs/next/api/propEach)
    - [propReduce](https://turfjs.org/docs/next/api/propReduce)
    - [segmentEach](https://turfjs.org/docs/next/api/segmentEach)
    - [segmentReduce](https://turfjs.org/docs/next/api/segmentReduce)
- [Assertions](https://turfjs.org/docs/next/api/along#)
    
    - [collectionOf](https://turfjs.org/docs/next/api/collectionOf)
    - [containsNumber](https://turfjs.org/docs/next/api/containsNumber)
    - [featureOf](https://turfjs.org/docs/next/api/featureOf)
    - [geojsonType](https://turfjs.org/docs/next/api/geojsonType)
- [Booleans](https://turfjs.org/docs/next/api/along#)
    
    - [booleanClockwise](https://turfjs.org/docs/next/api/booleanClockwise)
    - [booleanConcave](https://turfjs.org/docs/next/api/booleanConcave)
    - [booleanContains](https://turfjs.org/docs/next/api/booleanContains)
    - [booleanCrosses](https://turfjs.org/docs/next/api/booleanCrosses)
    - [booleanDisjoint](https://turfjs.org/docs/next/api/booleanDisjoint)
    - [booleanEqual](https://turfjs.org/docs/next/api/booleanEqual)
    - [booleanIntersects](https://turfjs.org/docs/next/api/booleanIntersects)
    - [booleanOverlap](https://turfjs.org/docs/next/api/booleanOverlap)
    - [booleanParallel](https://turfjs.org/docs/next/api/booleanParallel)
    - [booleanPointInPolygon](https://turfjs.org/docs/next/api/booleanPointInPolygon)
    - [booleanPointOnLine](https://turfjs.org/docs/next/api/booleanPointOnLine)
    - [booleanTouches](https://turfjs.org/docs/next/api/booleanTouches)
    - [booleanWithin](https://turfjs.org/docs/next/api/booleanWithin)
- [Unit Conversion](https://turfjs.org/docs/next/api/along#)
    
    - [azimuthToBearing](https://turfjs.org/docs/next/api/azimuthToBearing)
    - [bearingToAzimuth](https://turfjs.org/docs/next/api/bearingToAzimuth)
    - [convertArea](https://turfjs.org/docs/next/api/convertArea)
    - [convertLength](https://turfjs.org/docs/next/api/convertLength)
    - [degreesToRadians](https://turfjs.org/docs/next/api/degreesToRadians)
    - [lengthToDegrees](https://turfjs.org/docs/next/api/lengthToDegrees)
    - [lengthToRadians](https://turfjs.org/docs/next/api/lengthToRadians)
    - [radiansToDegrees](https://turfjs.org/docs/next/api/radiansToDegrees)
    - [radiansToLength](https://turfjs.org/docs/next/api/radiansToLength)
    - [toMercator](https://turfjs.org/docs/next/api/toMercator)
    - [toWgs84](https://turfjs.org/docs/next/api/toWgs84)
- [Other](https://turfjs.org/docs/next/api/along#)
    
    - [angle](https://turfjs.org/docs/next/api/angle)
    - [booleanValid](https://turfjs.org/docs/next/api/booleanValid)
    - [centerMean](https://turfjs.org/docs/next/api/centerMean)
    - [centerMedian](https://turfjs.org/docs/next/api/centerMedian)
    - [directionalMean](https://turfjs.org/docs/next/api/directionalMean)
    - [distanceWeight](https://turfjs.org/docs/next/api/distanceWeight)
    - [ellipse](https://turfjs.org/docs/next/api/ellipse)
    - [findPoint](https://turfjs.org/docs/next/api/findPoint)
    - [findSegment](https://turfjs.org/docs/next/api/findSegment)
    - [geometry](https://turfjs.org/docs/next/api/geometry)
    - [isNumber](https://turfjs.org/docs/next/api/isNumber)
    - [isObject](https://turfjs.org/docs/next/api/isObject)
    - [lineEach](https://turfjs.org/docs/next/api/lineEach)
    - [lineReduce](https://turfjs.org/docs/next/api/lineReduce)
    - [lineStrings](https://turfjs.org/docs/next/api/lineStrings)
    - [moranIndex](https://turfjs.org/docs/next/api/moranIndex)
    - [nearestNeighborAnalysis](https://turfjs.org/docs/next/api/nearestNeighborAnalysis)
    - [nearestPointToLine](https://turfjs.org/docs/next/api/nearestPointToLine)
    - [pNormDistance](https://turfjs.org/docs/next/api/pNormDistance)
    - [points](https://turfjs.org/docs/next/api/points)
    - [polygons](https://turfjs.org/docs/next/api/polygons)
    - [quadratAnalysis](https://turfjs.org/docs/next/api/quadratAnalysis)
    - [rbush](https://turfjs.org/docs/next/api/rbush)
    - [rectangleGrid](https://turfjs.org/docs/next/api/rectangleGrid)
    - [standardDeviationalEllipse](https://turfjs.org/docs/next/api/standardDeviationalEllipse)
- [Type Definitions](https://turfjs.org/docs/next/api/along#)
    
    - [AllGeoJSON](https://turfjs.org/docs/next/api/types/AllGeoJSON)
    - [AreaUnits](https://turfjs.org/docs/next/api/types/AreaUnits)
    - [Corners](https://turfjs.org/docs/next/api/types/Corners)
    - [Dbscan](https://turfjs.org/docs/next/api/types/Dbscan)
    - [DbscanProps](https://turfjs.org/docs/next/api/types/DbscanProps)
    - [DirectionalMeanLine](https://turfjs.org/docs/next/api/types/DirectionalMeanLine)
    - [Grid](https://turfjs.org/docs/next/api/types/Grid)
    - [Lines](https://turfjs.org/docs/next/api/types/Lines)
    - [MoranIndex](https://turfjs.org/docs/next/api/types/MoranIndex)
    - [NearestNeighborStatistics](https://turfjs.org/docs/next/api/types/NearestNeighborStatistics)
    - [NearestNeighborStudyArea](https://turfjs.org/docs/next/api/types/NearestNeighborStudyArea)
    - [QuadratAnalysisResult](https://turfjs.org/docs/next/api/types/QuadratAnalysisResult)
    - [Units](https://turfjs.org/docs/next/api/types/Units)
    - [clusterEachCallback](https://turfjs.org/docs/next/api/types/clusterEachCallback)
    - [clusterReduceCallback](https://turfjs.org/docs/next/api/types/clusterReduceCallback)
    - [coordEachCallback](https://turfjs.org/docs/next/api/types/coordEachCallback)
    - [coordReduceCallback](https://turfjs.org/docs/next/api/types/coordReduceCallback)
    - [featureEachCallback](https://turfjs.org/docs/next/api/types/featureEachCallback)
    - [featureReduceCallback](https://turfjs.org/docs/next/api/types/featureReduceCallback)
    - [flattenEachCallback](https://turfjs.org/docs/next/api/types/flattenEachCallback)
    - [flattenReduceCallback](https://turfjs.org/docs/next/api/types/flattenReduceCallback)
    - [geomEachCallback](https://turfjs.org/docs/next/api/types/geomEachCallback)
    - [geomReduceCallback](https://turfjs.org/docs/next/api/types/geomReduceCallback)
    - [lineEachCallback](https://turfjs.org/docs/next/api/types/lineEachCallback)
    - [lineReduceCallback](https://turfjs.org/docs/next/api/types/lineReduceCallback)
    - [propEachCallback](https://turfjs.org/docs/next/api/types/propEachCallback)
    - [propReduceCallback](https://turfjs.org/docs/next/api/types/propReduceCallback)
    - [segmentEachCallback](https://turfjs.org/docs/next/api/types/segmentEachCallback)
    - [segmentReduceCallback](https://turfjs.org/docs/next/api/types/segmentReduceCallback)
- [Constants](https://turfjs.org/docs/next/api/along#)
    
    - [K_TABLE](https://turfjs.org/docs/next/api/constants/K_TABLE)
    - [areaFactors](https://turfjs.org/docs/next/api/constants/areaFactors)
    - [earthRadius](https://turfjs.org/docs/next/api/constants/earthRadius)
    - [factors](https://turfjs.org/docs/next/api/constants/factors)

This is unreleased documentation for Turf.js **Next** version.

For up-to-date documentation, see the **[latest version](https://turfjs.org/docs/api/along)** (7.3.0).

- [](https://turfjs.org/)

- Measurement
- along

Version: Next

# along

### Description

Takes a [LineString](https://tools.ietf.org/html/rfc7946#section-3.1.4) and returns a [Point](https://tools.ietf.org/html/rfc7946#section-3.1.2) at a specified distance along the line.

### Parameters

|Name|Type|Description|
|---|---|---|
|line|**[Feature](https://tools.ietf.org/html/rfc7946#section-3.2)<[LineString](https://tools.ietf.org/html/rfc7946#section-3.1.4)> \| [LineString](https://tools.ietf.org/html/rfc7946#section-3.1.4)**|input line|
|distance|**[number](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)**|distance along the line|
|options_?_|**[Object](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)**|Optional parameters _(default {})_|
|options.units_?_|**[Units](https://turfjs.org/docs/next/api/types/Units)**|Supports all valid Turf [Units](https://turfjs.org/docs/api/types/Units). _(default "kilometers")_|

### Returns

**[Feature](https://tools.ietf.org/html/rfc7946#section-3.2)<[Point](https://tools.ietf.org/html/rfc7946#section-3.1.2)>** Point `distance` `units` along the line

### Examples

```
var line = turf.lineString([  [-83, 30],  [-84, 36],  [-78, 41],]);var options = { units: "miles" };var along = turf.along(line, 200, options);
```

[+](https://turfjs.org/docs/next/api/along# "Zoom in")[-](https://turfjs.org/docs/next/api/along# "Zoom out")

[](https://turfjs.org/docs/next/api/along# "Layers")

[](https://www.mapbox.com/about/maps "Mapbox")[](https://www.openstreetmap.org/copyright/ "OpenStreetMap")[](https://www.mapbox.com/contribute/#/-81.000/35.689/4 "Improve this map")

### Installation

```
$ npm install @turf/alongimport { along } from "@turf/along";const result = along(...);
```

```
$ npm install @turf/turfimport * as turf from "@turf/turf";const result = turf.along(...);
```

[](https://github.com/facebook/docusaurus/tree/main/packages/create-docusaurus/templates/shared/docs/api/along.mdx)

[Edit this page](https://github.com/facebook/docusaurus/tree/main/packages/create-docusaurus/templates/shared/docs/api/along.mdx)

[

Next

area

](https://turfjs.org/docs/next/api/area)

- [Description](https://turfjs.org/docs/next/api/along#description)
- [Parameters](https://turfjs.org/docs/next/api/along#parameters)
- [Returns](https://turfjs.org/docs/next/api/along#returns)
- [Examples](https://turfjs.org/docs/next/api/along#examples)
- [Installation](https://turfjs.org/docs/next/api/along#installation)

Docs

- [Introduction](https://turfjs.org/docs/intro)
- [Getting Started](https://turfjs.org/docs/getting-started)
- [API](https://turfjs.org/docs/api/along)

Community

- [Stack Overflow](https://stackoverflow.com/questions/tagged/turfjs)

- [Twitter](https://twitter.com/turfjs)

More

- [Blog](https://turfjs.org/blog)
- [GitHub](https://github.com/Turfjs/turf)