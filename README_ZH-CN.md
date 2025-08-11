ThreeJS Globe Visualization
===========================

[![NPM package][npm-img]][npm-url]
[![Build Size][build-size-img]][build-size-url]
[![NPM Downloads][npm-downloads-img]][npm-downloads-url]
[English](./README.md)
[中文](./README_ZH-CN.md)
<p align="center">
  <a href="//vasturiano.github.io/three-globe/example/basic/"><img width="80%" src="https://vasturiano.github.io/three-globe/example/preview.png"></a>
</p>

深受 [WebGL Globe](https://experiments.withgoogle.com/chrome/globe) 的启发，这是一个 [ThreeJS](https://threejs.org/) WebGL 类，用于在地球上表示数据可视化层，使用球面投影。

See also the [standalone version](https://github.com/vasturiano/globe.gl), and the [react-three-fiber bindings](https://github.com/vasturiano/r3f-globe).

#### 查看示例：
* [Basic](https://vasturiano.github.io/three-globe/example/basic/) ([source](https://github.com/vasturiano/three-globe/blob/master/example/basic/index.html))
* [Arc Links](https://vasturiano.github.io/three-globe/example/links/) ([source](https://github.com/vasturiano/three-globe/blob/master/example/links/index.html))
* [Country Polygons](https://vasturiano.github.io/three-globe/example/country-polygons/) ([source](https://github.com/vasturiano/three-globe/blob/master/example/country-polygons/index.html))
* [Path lines](https://vasturiano.github.io/three-globe/example/paths/) ([source](https://github.com/vasturiano/three-globe/blob/master/example/paths/index.html))
* [Heatmap](https://vasturiano.github.io/three-globe/example/heatmap/) ([source](https://github.com/vasturiano/three-globe/blob/master/example/heatmap/index.html))
* [Hexagonal Binning](https://vasturiano.github.io/three-globe/example/hexbin/) ([source](https://github.com/vasturiano/three-globe/blob/master/example/hexbin/index.html))
* [Hexed Country Polygons](https://vasturiano.github.io/three-globe/example/hexed-polygons/) ([source](https://github.com/vasturiano/three-globe/blob/master/example/hexed-polygons/index.html))
* [Tiles](https://vasturiano.github.io/three-globe/example/tiles/) ([source](https://github.com/vasturiano/three-globe/blob/master/example/tiles/index.html))
* [Ripple Rings](https://vasturiano.github.io/three-globe/example/ripples/) ([source](https://github.com/vasturiano/three-globe/blob/master/example/ripples/index.html))
* [Clouds](https://vasturiano.github.io/three-globe/example/clouds/) ([source](https://github.com/vasturiano/three-globe/blob/master/example/clouds/index.html))
* [Day/Night Cycle](https://vasturiano.github.io/three-globe/example/day-night-cycle/) ([source](https://github.com/vasturiano/three-globe/blob/master/example/day-night-cycle/index.html))
* [Solar Terminator](https://vasturiano.github.io/three-globe/example/solar-terminator/) ([source](https://github.com/vasturiano/three-globe/blob/master/example/solar-terminator/index.html))
* [Labels](https://vasturiano.github.io/three-globe/example/labels/) ([source](https://github.com/vasturiano/three-globe/blob/master/example/labels/index.html))
* [HTML Markers](https://vasturiano.github.io/three-globe/example/html-markers/) ([source](https://github.com/vasturiano/three-globe/blob/master/example/html-markers/index.html))
* [Satellites](https://vasturiano.github.io/three-globe/example/satellites/) ([source](https://github.com/vasturiano/three-globe/blob/master/example/satellites/index.html))
* [Tiled Map Engine](https://vasturiano.github.io/three-globe/example/tile-engine/) ([source](https://github.com/vasturiano/three-globe/blob/master/example/tile-engine/index.html))
* [Custom Globe Material](https://vasturiano.github.io/three-globe/example/custom-material/) ([source](https://github.com/vasturiano/three-globe/blob/master/example/custom-material/index.html))
* [Custom Layer](https://vasturiano.github.io/three-globe/example/custom/) ([source](https://github.com/vasturiano/three-globe/blob/master/example/custom/index.html))

## ❤️ 支持这个项目

如果你发现这个模块有用并想支持它的开发，你可以[请我喝杯咖啡](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=L398E7PKP47E8&currency_code=USD&source=url)。你的贡献有助于保持开源的可持续性！
[![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_donations&business=L398E7PKP47E8&currency_code=USD&source=url)

## 快速开始

```js
import ThreeGlobe from 'three-globe';
```
或者使用 *script* 标签
```html
<script src="//cdn.jsdelivr.net/npm/three-globe"></script>
```
然后
```js
const myGlobe = new ThreeGlobe()
  .globeImageUrl(myImageUrl)
  .pointsData(myData);

const myScene = new THREE.Scene();
myScene.add(myGlobe);
```

## API 参考

- [ThreeJS Globe Visualization](#threejs-globe-visualization)
      - [查看示例：](#%E6%9F%A5%E7%9C%8B%E7%A4%BA%E4%BE%8B%EF%BC%9A)
  - [❤️ 支持这个项目](#%EF%BC%A5%EF%BC%A5-%E6%94%AF%E6%8C%81%E8%BF%99%E4%B8%AA%E9%A1%B9%E7%9B%AE)
  - [快速开始](#%E5%BF%AB%E9%80%9F%E5%BC%80%E5%A7%8B)
  - [API 参考](#api-%E5%8F%82%E8%80%83)
    - [初始化](#initialisation)
    - [地球图层](#globe-layer)
    - [点图层](#points-layer)
    - [弧线图层](#arcs-layer)
    - [多边形图层](#polygons-layer)
    - [路径图层](#paths-layer)
    - [热力图图层](#heatmaps-layer)
    - [六边形分箱图层](#hex-bin-layer)
    - [六边形多边形图层](#hexed-polygons-layer)
    - [瓦片图层](#tiles-layer)
    - [粒子图层](#particles-layer)
    - [环图层](#rings-layer)
    - [文本标签图层](#labels-layer)
    - [HTML元素图层](#html-elements-layer)
    - [3D对象图层](#3d-objects-layer)
    - [自定义图层](#custom-layer)
    - [工具函数](#utility)
    - [渲染选项](#render-options)

### 初始化
```js
new ThreeGlobe({ configOptions })
```

| 配置选项 | 描述 | 默认值 |
| --- | --- | :--: |
| <b>waitForGlobeReady</b>: <i>boolean</i> | 是否等待地球包裹图像完全加载后再渲染地球或任何数据层。 | `true` |
| <b>animateIn</b>: <i>boolean</i> | 是否通过缩放和旋转地球到初始位置来动画化地球初始化。 | `true` |

### 地球图层 

| 方法 | 描述 | 默认值 |
| --- | --- | :--: |
| <b>globeImageUrl</b>([<i>url</i>]) | 用于包裹地球的材质中使用的图像URL的getter/setter。此图像应遵循[等矩形投影](https://en.wikipedia.org/wiki/Equirectangular_projection)。如果未提供图像，地球将表示为黑色球体。 | `null` |
| <b>bumpImageUrl</b>([<i>url</i>]) | 用于在材质中创建[凹凸贴图](https://threejs.org/docs/#api/en/materials/MeshStandardMaterial.bumpMap)以表示地球地形的图像URL的getter/setter。此图像应遵循[等矩形投影](https://en.wikipedia.org/wiki/Equirectangular_projection)。 | `null` |
| <b>showGlobe</b>([<i>boolean</i>]) | Getter/setter for whether to show the globe surface itself. | `true` |
| <b>showGraticules</b>([<i>boolean</i>]) | 是否显示每10度标记纬度和经度线的网格的getter/setter。 | `false` |
| <b>showAtmosphere</b>([<i>boolean</i>]) | 是否显示环绕地球的明亮光晕（代表大气层）的getter/setter。 | `true` |
| <b>atmosphereColor</b>([<i>str</i>]) | 地球大气层颜色的getter/setter。 | `lightskyblue` |
| <b>atmosphereAltitude</b>([<i>str</i>]) | 地球大气层最大高度的getter/setter，以地球半径单位表示。 | 0.15 |
| <b>globeTileEngineUrl</b>([<i>fn(x, y, l)</i>]) | 定义用于覆盖地球表面的[滑动地图](https://en.wikipedia.org/wiki/Tiled_web_map)瓦片引擎URL的函数的getter/setter。滑动地图坐标`x`、`y`和`l`（缩放级别）作为参数传递，函数应返回URL字符串。假值将禁用瓦片引擎。 | - |
| <b>globeTileEngineMaxZoom</b>([<i>num</i>]) | 瓦片引擎最大缩放级别的getter/setter。 | `17` |
| <b>globeCurvatureResolution</b>([<i>number</i>]) | 球体曲率的角度分辨率的getter/setter。分辨率越高，地球越会被分割成更小的面来近似球形表面，但会以性能为代价。 | `4` |
| <b>globeMaterial</b>([<i>material</i>]) | 用于包裹地球的ThreeJS材质的getter/setter。可用于更高级的地球样式，如[此示例](https://github.com/vasturiano/three-globe/blob/master/example/custom-material/index.html)所示。 | [MeshPhongMaterial](https://threejs.org/docs/#api/en/materials/MeshPhongMaterial) |
| <b>onGlobeReady</b>(<i>fn</i>) | 地球初始化并在场景上可见后立即调用的回调函数。 | - |

### Points Layer 点图层

| 方法 | 描述 | 默认值 |
| --- | --- | :--: |
| <b>pointsData</b>([<i>array</i>]) | 点地图图层中要表示的点列表的获取/设置器。每个点显示为从地球表面垂直升起的圆柱形3D对象。 | `[]` |
| <b>pointLat</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 点对象访问器函数、属性或圆柱中心纬度坐标的数值常量。 | `lat` |
| <b>pointLng</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 点对象访问器函数、属性或圆柱中心经度坐标的数值常量。 | `lng` |
| <b>pointColor</b>([<i>str</i> or <i>fn</i>]) | Point object accessor function or attribute for the cylinder color. | `() => '#ffffaa'` |
| <b>pointAltitude</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 点对象访问器函数、属性或圆柱高度的数值常量，以地球半径单位表示（`0` = 0高度（平圆），`1` = 地球半径）。 | 0.1 |
| <b>pointRadius</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 点对象访问器函数、属性或圆柱半径的数值常量，以角度度数表示。 | 0.25 |
| <b>pointResolution</b>([<i>num</i>]) | 获取/设置每个圆柱的径向几何分辨率，表示将圆周划分为多少个切片段。值越高，圆柱越平滑。 | 12 |
| <b>pointsMerge</b>([<i>boolean</i>]) | 获取/设置是否将所有点网格合并为单个ThreeJS对象，以提高渲染性能。视觉上两种选项效果相同，设置此选项仅影响ThreeJS对象的内部组织。 | `false` |
| <b>pointsTransitionDuration</b>([<i>num</i>]) | 获取/设置用于动画点几何修改变化的过渡持续时间（毫秒）。值为`0`将立即移动对象到最终位置。新对象通过从地面向上缩放进行动画。仅在`pointsMerge`禁用时有效。 | 1000 |

### Arcs Layer 弧线

| 方法 | 描述 | 默认值 |
| --- | --- | :--: |
| <b>arcsData</b>([<i>array</i>]) | 弧线地图图层中要表示的连接线列表的getter/setter。每条连接线显示为从地球表面升起的弧线，连接起点和终点坐标。 | `[]` |
| <b>arcStartLat</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 弧线对象访问器函数、属性或线的起点纬度坐标的数值常量。 | `startLat` |
| <b>arcStartLng</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 弧线对象访问器函数、属性或线的起点经度坐标的数值常量。 | `startLng` |
| <b>arcStartAltitude</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 弧线对象访问器函数、属性或线的起点高度的数值常量。 | 0 |
| <b>arcEndLat</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 弧线对象访问器函数、属性或线的终点纬度坐标的数值常量。 | `endLat` |
| <b>arcEndLng</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 弧线对象访问器函数、属性或线的终点经度坐标的数值常量。 | `endLng` |
| <b>arcEndAltitude</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 弧线对象访问器函数、属性或线的终点高度的数值常量。 | 0 |
| <b>arcColor</b>([<i>str</i>, <i>[str, ...]</i> or <i>fn</i>]) | 弧线对象访问器函数或属性，用于线的颜色。还支持通过传递颜色数组或颜色插值函数来实现颜色渐变。 | `() => '#ffffaa'` |
| <b>arcAltitude</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 弧线对象访问器函数、属性或弧线最大高度的数值常量（出现在两点间的中点位置），以地球半径单位表示（`0` = 0高度（地面线），`1` = 地球半径）。如果使用`null`或`undefined`值，高度将根据`arcAltitudeAutoScale`设置的比例自动按两点间距离成比例设置。 | `null` |
| <b>arcAltitudeAutoScale</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 弧线对象访问器函数、属性或弧线自动高度的比例系数，以两点间大圆弧距离的单位表示。值为`1`表示弧线高度应与其地面长度相同。仅在未设置`arcAltitude`时适用。 | 0.5 |
| <b>arcStroke</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 弧线对象访问器函数、属性或线的直径数值常量，以角度度数表示。值为`null`或`undefined`将渲染[ThreeJS Line](https://threejs.org/docs/#api/objects/Line)，其宽度与相机距离无关（`1px`）。否则，将使用[TubeGeometry](https://threejs.org/docs/#api/en/geometries/TubeGeometry)。 | `null` |
| <b>arcCurveResolution</b>([<i>num</i>]) | 获取/设置弧线的曲线分辨率，表示将曲线划分为多少条直线段。值越高，曲线越平滑。 | 64 |
| <b>arcCircularResolution</b>([<i>num</i>]) | 获取/设置每条线的径向几何分辨率，表示将管的圆周划分为多少个切片段。仅在使用Tube几何图形（定义了`arcStroke`）时适用。 | 6 |
| <b>arcDashLength</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 弧线对象访问器函数、属性或弧线中虚线段长度的数值常量，以整条线的相对长度表示（`1` = 线的完整长度）。 | 1 |
| <b>arcDashGap</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 弧线对象访问器函数、属性或虚线段之间间隙长度的数值常量，以线的相对长度表示。 | 0 |
| <b>arcDashInitialGap</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 弧线对象访问器函数、属性或第一个虚线段前初始间隙长度的数值常量，以线的相对长度表示。 | 0 |
| <b>arcDashAnimateTime</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 弧线对象访问器函数、属性或动画虚线位置从起点移动到终点的持续时间（以`ms`为单位）。值为`0`时禁用动画。 | 0 |
| <b>arcsTransitionDuration</b>([<i>num</i>]) | 获取/设置用于动画弧线几何修改变化的过渡持续时间（毫秒）。值为`0`将立即移动弧线到最终位置。新弧线通过从地面升起进行动画。 | 1000 |

### Polygons 多边形图层 

| 方法 | 描述 | 默认值 |
| --- | --- | :--: |
| <b>polygonsData</b>([<i>array</i>]) | 多边形地图图层中要表示的多边形形状列表的getter/setter。每个多边形显示为从地球表面突出的成形锥体。 | `[]` |
| <b>polygonGeoJsonGeometry</b>([<i>str</i> or <i>fn</i>]) | 多边形对象访问器函数或属性，用于多边形形状的GeoJson几何规范。返回值应至少包含两个字段：`type`和`coordinates`。仅支持类型为`Polygon`或`MultiPolygon`的GeoJson几何，其他类型将被跳过。 | `geometry` |
| <b>polygonCapColor</b>([<i>str</i> or <i>fn</i>]) | 多边形对象访问器函数或属性，用于顶面的颜色。 | `() => '#ffffaa'` |
| <b>polygonCapMaterial</b>([<i>material</i>, <i>str</i> or <i>fn</i>]) | 多边形对象访问器函数、属性或材质对象，用于顶面使用的[ThreeJS材质](https://threejs.org/docs/#api/en/materials/Material)。此属性优先于`polygonCapColor`，如果两者都定义，则`polygonCapColor`将被忽略。 | - |
| <b>polygonSideColor</b>([<i>str</i> or <i>fn</i>]) | 多边形对象访问器函数或属性，用于锥体侧面的颜色。 | `() => '#ffffaa'` |
| <b>polygonSideMaterial</b>([<i>material</i>, <i>str</i> or <i>fn</i>]) | 多边形对象访问器函数、属性或材质对象，用于锥体侧面使用的[ThreeJS材质](https://threejs.org/docs/#api/en/materials/Material)。此属性优先于`polygonSideColor`，如果两者都定义，则`polygonSideColor`将被忽略。 | - |
| <b>polygonStrokeColor</b>([<i>str</i> or <i>fn</i>]) | 多边形对象访问器函数或属性，用于描边多边形周长的颜色。假值将禁用描边。 | - |
| <b>polygonAltitude</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 多边形对象访问器函数、属性或数值常量，用于多边形锥体的高度，以地球半径单位表示（`0` = 0高度（平多边形），`1` = 地球半径）。 | 0.01 |
| <b>polygonCapCurvatureResolution</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 多边形对象访问器函数、属性或数值常量，用于顶面曲率的分辨率（以角度为单位）。分辨率越高，多边形越会被分割成更小的面来近似球形表面，但会以性能为代价。 | 5 |
| <b>polygonsTransitionDuration</b>([<i>num</i>]) | 用于动画化多边形高度变化的过渡持续时间（毫秒）的getter/setter。值为`0`将立即将锥体调整到最终高度。新多边形通过从地面上升来进行动画化。 | 1000 |

### Paths 路径图层

| 方法 | 描述 | 默认值 |
| --- | --- | :--: |
| <b>pathsData</b>([<i>array</i>]) | 路径地图图层中要表示的线列表的getter/setter。每个路径显示为连接路径数组中所有坐标对的线。 | `[]` |
| <b>pathPoints</b>([<i>array</i>, <i>str</i> or <i>fn</i>]) | 路径对象访问器函数、属性或数组，用于定义路径线的点集。默认情况下，每个路径点被假定为2位置数组（`[<lat>, <lon>]`）。可以使用`pathPointLat`和`pathPointLng`方法修改此默认行为。 | `pnts => pnts` |
| <b>pathPointLat</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 路径点对象访问器函数、属性或纬度坐标的数值常量。 | `arr => arr[0]` |
| <b>pathPointLng</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 路径点对象访问器函数、属性或经度坐标的数值常量。 | `arr => arr[1]` |
| <b>pathPointAlt</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 路径点对象访问器函数、属性或点高度的数值常量，以地球半径单位表示（`0` = 0高度（地面），`1` = 地球半径）。 | 0.001 |
| <b>pathResolution</b>([<i>num</i>]) | 获取/设置路径的角度分辨率，以纬度/经度度数表示。如果两个相邻路径点之间的地面距离（不包括高度）大于此值，则线段将被插值以近似球面曲率。较低的值会产生更完美的曲线，但会牺牲性能。 | 2 |
| <b>pathColor</b>([<i>str</i>, <i>[str, ...]</i> or <i>fn</i>]) | 路径对象访问器函数或属性，用于线的颜色。还支持通过传递颜色数组或颜色插值函数来实现颜色渐变。设置宽度的Fat Lines不支持透明颜色。 | `() => '#ffffaa'` |
| <b>pathStroke</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 路径对象访问器函数、属性或数值常量，用于线的直径，以角度为单位。值为`null`或`undefined`将渲染一个[ThreeJS Line](https://threejs.org/docs/#api/objects/Line)，其宽度与相机距离无关（`1px`）。否则，将使用[FatLine](https://github.com/vasturiano/three-fatline)。 | `null` |
| <b>pathDashLength</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 路径对象访问器函数、属性或数值常量，用于路径线中虚线段的长度，以整个线的相对长度表示（`1` = 全线长度）。 | 1 |
| <b>pathDashGap</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 路径对象访问器函数、属性或数值常量，用于虚线段之间的间隙长度，以相对线长度表示。 | 0 |
| <b>pathDashInitialGap</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 路径对象访问器函数、属性或数值常量，用于第一个虚线段之前的初始间隙长度，以相对线长度表示。 | 0 |
| <b>pathDashAnimateTime</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 路径对象访问器函数、属性或数值常量，用于动画化虚线位置从起点到终点的运动持续时间（以`ms`为单位），持续整个线长度。值为`0`将禁用动画。 | 0 |
| <b>pathTransitionDuration</b>([<i>num</i>]) | 用于动画化路径变化的过渡持续时间（毫秒）的getter/setter。值为`0`将立即将路径移动到最终位置。新路径从头到尾进行动画化。 | 1000 |

### Heatmaps 热力图图层

| 方法 | 描述 | 默认值 |
| --- | --- | :--: |
| <b>heatmapsData</b>([<i>array</i>]) | 热力图地图图层中要表示的热力图数据集列表的getter/setter。根据点密度，每组点被表示为具有不同颜色和/或高度的单独全局热力图。它使用[高斯KDE](https://en.wikipedia.org/wiki/Kernel_density_estimation)基于点之间的大圆弧距离执行密度估计。 | `[]` |
| <b>heatmapPoints</b>([<i>array</i>, <i>str</i> or <i>fn</i>]) | 热力图对象访问器函数、属性或数组，用于定义热力图的点集。默认情况下，每个点被假定为2位置数组（`[<lat>, <lon>]`）。可以使用`heatmapPointLat`和`heatmapPointLng`方法修改此默认行为。 | `pnts => pnts` |
| <b>heatmapPointLat</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 热力图点对象访问器函数、属性或纬度坐标的数值常量。 | `arr => arr[0]` |
| <b>heatmapPointLng</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 热力图点对象访问器函数、属性或经度坐标的数值常量。 | `arr => arr[1]` |
| <b>heatmapPointWeight</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 热力图点对象访问器函数、属性或点的权重的数值常量。点的权重决定了它对周围区域密度的影响。 | 1 |
| <b>heatmapBandwidth</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 热力图对象访问器函数、属性或热力图带宽的数值常量，以角度为单位。带宽是[高斯核函数](https://en.wikipedia.org/wiki/Gaussian_function)的内部参数，定义了点对远距离位置的影响程度。较窄的带宽导致更尖峰的表示，而较宽的带宽则有更平滑的曲线。 | 2.5 |
| <b>heatmapColorFn</b>([<i>str</i> or <i>fn</i>]) | 热力图对象访问器函数或属性，用于表示热力图中密度的颜色插值函数。此函数应接收`0`到`1`之间的数字（如果饱和度>1，则可能更高），并返回颜色字符串。 | [Turbo颜色映射](https://blog.research.google/2019/08/turbo-improved-rainbow-colormap-for.html)插值器，具有渐隐透明度 |
| <b>heatmapColorSaturation</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 热力图对象访问器函数、属性或颜色比例尺饱和度的数值常量。饱和度是传递给颜色插值函数之前归一化密度值（`[0,1]`）的乘数。它可用于抑制密度中的异常峰值并使数据底部可见。 | 1.5 |
| <b>heatmapBaseAltitude</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 热力图对象访问器函数、属性或热力图基础高度的数值常量，以地球半径单位表示（`0` = 0高度，`1` = 地球半径）。 | 0.01 |
| <b>heatmapTopAltitude</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 热力图对象访问器函数、属性或热力图顶部峰值高度的数值常量，以地球半径单位表示（`0` = 0高度，`1` = 地球半径）。与基础高度相等的值将产生表面平坦的热力图。如果设置了顶部高度，则密度变化将用于定义基础和顶部之间的高度曲线。 | - |
| <b>heatmapsTransitionDuration</b>([<i>num</i>]) | 用于动画化热力图变化的过渡持续时间（毫秒）的getter/setter。值为`0`将立即将热力图颜色/高度设置为最终位置。新热力图通过从地面上升并通过颜色比例尺轻轻淡入来进行动画化。 | 0 |

### hexBinPoint 六边形 点 分箱图层

| 方法 | 描述 | 默认值 |
| --- | --- | :--: |
| <b>hexBinPointsData</b>([<i>array</i>]) | 六边形分箱地图图层中用于聚合的点列表的getter/setter。每个点被添加到表示空间细分部分内所有点的六边形棱柱3D对象中。 | `[]` |
| <b>hexBinPointLat</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 点对象访问器函数、属性或纬度坐标的数值常量。 | `lat` |
| <b>hexBinPointLng</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 点对象访问器函数、属性或经度坐标的数值常量。 | `lng` |
| <b>hexBinPointWeight</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 点对象访问器函数、属性或点的权重的数值常量。同一分箱内点的权重相加，决定了六边形的默认高度。 | 1 |
| <b>hexBinResolution</b>([<i>num</i>]) | 由[H3](https://uber.github.io/h3/#/documentation/core-library/resolution-table)定义的地理分箱分辨率。确定平铺地球表面的六边形区域。接受`0`到`15`之间的值。级别0将地球划分为122个（主要是）六边形单元。每个后续级别将前一个级别细分为大约7个六边形。 | 4 |
| <b>hexMargin</b>([<i>num</i> or <i>fn</i>]) | 每个六边形的径向边距。边距大于`0`将在相邻六边形之间创建间隙，仅用于视觉目的，因为边距内的数据点仍会贡献到六边形的数据中。边距以六边形表面直径的分数表示。不建议使用小于`0`或大于`1`的值。此属性还支持使用基于六边形聚合数据的访问器方法，语法如下：`hexMargin(({ points, sumWeight, center: { lat, lng }}) => ...)`。此方法应返回数值常量。 | 0.2 |
| <b>hexAltitude</b>([<i>num</i> or <i>fn</i>]) | 每个六边形的高度，以地球半径单位表示（`0` = 0高度（平六边形），`1` = 地球半径）。此属性还支持使用基于六边形聚合数据的访问器方法，语法如下：`hexAltitude(({ points, sumWeight, center: { lat, lng }}) => ...)`。此方法应返回数值常量。 | `({ sumWeight }) => sumWeight * 0.01` |
| <b>hexTopCurvatureResolution</b>([<i>num</i>]) | 顶部表面曲率的分辨率（以角度为单位）。分辨率越高，顶部区域越会被分割成更小的面来近似球形表面，但会以性能为代价。 | 5 |
| <b>hexTopColor</b>([<i>fn</i>]) | 每个六边形顶部颜色的访问器方法。该方法应遵循签名：`hexTopColor(({ points, sumWeight, center: { lat, lng }}) => ...)`并返回颜色字符串。 | `() => '#ffffaa'` |
| <b>hexSideColor</b>([<i>fn</i>]) | 每个六边形侧面颜色的访问器方法。该方法应遵循签名：`hexSideColor(({ points, sumWeight, center: { lat, lng }}) => ...)`并返回颜色字符串。 | `() => '#ffffaa'` |
| <b>hexBinMerge</b>([<i>boolean</i>]) | 是否将所有六边形网格合并到单个ThreeJS对象中的getter/setter，以提高渲染性能。视觉上两种选项是等效的，设置此选项仅影响ThreeJS对象的内部组织。 | `false` |
| <b>hexTransitionDuration</b>([<i>num</i>]) | 用于动画化与几何修改（高度、半径）相关的六边形变化的过渡持续时间（毫秒）的getter/setter。值为`0`将立即将六边形移动到最终位置。新六边形通过从地面向上缩放来进行动画化。仅在`hexBinMerge`禁用时有效。 | 1000 |

### hexPolygons 六边形多边形图层

| 方法 | 描述 | 默认值 |
| --- | --- | :--: |
| <b>hexPolygonsData</b>([<i>array</i>]) | 六边形多边形地图图层中要表示的多边形形状列表的getter/setter。每个多边形根据`hexPolygonResolution`中指定的分辨率，显示为近似多边形形状的六边形组。 | `[]` |
| <b>hexPolygonGeoJsonGeometry</b>([<i>str</i> or <i>fn</i>]) | 六边形多边形对象访问器函数或属性，用于多边形形状的GeoJson几何规范。返回值应至少包含两个字段：`type`和`coordinates`。仅支持类型为`Polygon`或`MultiPolygon`的GeoJson几何，其他类型将被跳过。 | `geometry` |
| <b>hexPolygonColor</b>([<i>str</i> or <i>fn</i>]) | 六边形多边形对象访问器函数或属性，用于多边形中每个六边形的颜色。 | `() => '#ffffaa'` |
| <b>hexPolygonAltitude</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 六边形多边形对象访问器函数、属性或数值常量，用于多边形六边形的高度，以地球半径单位表示（`0` = 0高度，`1` = 地球半径）。 | 0.001 |
| <b>hexPolygonResolution</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 六边形多边形对象访问器函数、属性或由[H3](https://uber.github.io/h3/#/documentation/core-library/resolution-table)定义的地理分箱分辨率的数值常量。确定平铺地球表面的六边形区域。接受`0`到`15`之间的值。级别0将地球划分为122个（主要是）六边形单元。每个后续级别将前一个级别细分为大约7个六边形。 | 3 |
| <b>hexPolygonMargin</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 六边形多边形对象访问器函数、属性或每个六边形的径向边距的数值常量。边距大于`0`将在多边形内的相邻六边形之间创建间隙。边距以六边形表面直径的分数表示。不建议使用小于`0`或大于`1`的值。 | 0.2 |
| <b>hexPolygonUseDots</b>([<i>boolean</i>, <i>str</i> or <i>fn</i>]) | 六边形多边形对象访问器函数、属性或布尔常量，用于确定是否将每个多边形点表示为圆点而不是六边形。 | `false` |
| <b>hexPolygonCurvatureResolution</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 六边形多边形对象访问器函数、属性或每个六边形多边形表面曲率的分辨率（以角度为单位）的数值常量。分辨率越高，多边形六边形越会被分割成更小的面来近似球形表面，但会以性能为代价。 | 5 |
| <b>hexPolygonDotResolution</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 六边形多边形对象访问器函数、属性或每个圆点的分辨率的数值常量，表示为将圆周分成多少个切片段。值越高，圆越平滑，但会以性能为代价。这仅适用于圆点表示模式。 | 12 |
| <b>hexPolygonsTransitionDuration</b>([<i>num</i>]) | 用于动画化六边形多边形高度和边距变化的过渡持续时间（毫秒）的getter/setter。值为`0`将立即将六边形移动到最终状态。新六边形多边形通过将每个六边形从`0`半径调整大小来进行动画化。 | 0 |

### tiles 瓦片图层

| 方法 | 描述 | 默认值 |
| --- | --- | :--: |
| <b>tilesData</b>([<i>array</i>]) | 瓦片地图图层中表示的瓦片列表的 getter/setter。每个瓦片显示为一个球面分段。这些分段可以并排放置形成一个 tiled 表面，每个都可以单独设置样式。 | `[]` |
| <b>tileLat</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 瓦片对象访问器函数、属性或数值常量，用于分段的质心纬度坐标。 | `lat` |
| <b>tileLng</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 瓦片对象访问器函数、属性或数值常量，用于分段的质心经度坐标。 | `lng` |
| <b>tileAltitude</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 瓦片对象访问器函数、属性或数值常量，用于分段的高度（以地球半径单位表示）。 | 0.01 |
| <b>tileWidth</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 瓦片对象访问器函数、属性或数值常量，用于分段的经度宽度（以角度表示）。 | 1 |
| <b>tileHeight</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 瓦片对象访问器函数、属性或数值常量，用于分段的纬度高度（以角度表示）。 | 1 |
| <b>tileUseGlobeProjection</b>([<i>boolean</i>, <i>str</i> or <i>fn</i>]) | 瓦片对象访问器函数、属性或布尔常量，用于确定是否使用地球投影将分段塑造为其相对瓦片位置 (`true`)，或者脱离此投影并将分段塑造为直接位于赤道周长上的形状 (`false`)。 | `true` |
| <b>tileMaterial</b>([<i>material</i>, <i>str</i> or <i>fn</i>]) | 瓦片对象访问器函数、属性或材质对象，用于设置分段表面样式的 [ThreeJS 材质](https://threejs.org/docs/#api/en/materials/Material)。 | `() => new MeshLambertMaterial({ color: '#ffbb88' })` |
| <b>tileCurvatureResolution</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 瓦片对象访问器函数、属性或数值常量，用于表面曲率的分辨率（以角度表示）。分辨率越高，瓦片几何体越会被分割成更小的面来近似球面，代价是性能。 | 5 |
| <b>tilesTransitionDuration</b>([<i>num</i>]) | 用于动画化涉及几何体修改的瓦片变化的过渡持续时间（毫秒）的 getter/setter。值为 `0` 将使瓦片立即移动到最终位置。新瓦片通过从质心向外缩放来进行动画处理。 | 1000 |

### particles 粒子图层

| 方法 | 描述 | 默认值 |
| --- | --- | :--: |
| <b>particlesData</b>([<i>array</i>]) | 粒子地图图层中表示的粒子集列表的 getter/setter。每个粒子集显示为一组 [Points](https://threejs.org/docs/#api/en/objects/Points)。组中的每个点都是一个几何体顶点，可以相对于地球单独定位在任何位置。 | `[]` |
| <b>particlesList</b>([<i>str</i> or <i>fn</i>]) | 粒子集访问器函数或属性，用于获取集中的粒子列表。默认情况下，数据结构应为单个粒子对象的数组的数组。 | `d => d` |
| <b>particleLat</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 粒子对象访问器函数、属性或数值常量，用于纬度坐标。 | `lat` |
| <b>particleLng</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 粒子对象访问器函数、属性或数值常量，用于经度坐标。 | `lng` |
| <b>particleAltitude</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 粒子对象访问器函数、属性或数值常量，用于高度（以地球半径单位表示）。 | 0.01 |
| <b>particlesSize</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 粒子集访问器函数、属性或数值常量，用于组中所有粒子的大小。 | `0.5` |
| <b>particlesSizeAttenuation</b>([<i>boolean</i>, <i>str</i> or <i>fn</i>]) | 粒子集访问器函数、属性或布尔常量，用于确定屏幕上每个粒子的大小是否应根据与相机的距离而衰减。 | `true` |
| <b>particlesColor</b>([<i>str</i> or <i>fn</i>]) | 粒子集访问器函数或属性，用于组中所有粒子的颜色。如果定义了`particlesTexture`，则此设置将被忽略。 | `white` |
| <b>particlesTexture</b>([<i>str</i> or <i>fn</i>]) | 粒子集访问器函数或属性，用于应用于组中所有粒子的[纹理](https://threejs.org/docs/#api/en/textures/Texture)。 | - |

### rings 圆环图层

| 方法 | 描述 | 默认值 |
| --- | --- | :--: |
| <b>ringsData</b>([<i>array</i>]) | 圆环地图图层中表示的自传播波纹环列表的 getter/setter。每个数据点显示为一组动画的同心圆，这些圆从球面表面的中心点向外（或向内）传播。 | `[]` |
| <b>ringLat</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 圆环对象访问器函数、属性或数值常量，用于每个圆的中心纬度坐标。 | `lat` |
| <b>ringLng</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 圆环对象访问器函数、属性或数值常量，用于每个圆的中心经度坐标。 | `lng` |
| <b>ringAltitude</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 圆环对象访问器函数、属性或数值常量，用于圆的高度（以地球半径单位表示）。 | 0.0015 |
| <b>ringColor</b>([<i>str</i>, <i>[str, ...]</i> or <i>fn</i>]) | 圆环对象访问器函数或属性，用于每个环的描边颜色。还支持通过传递颜色数组或颜色插值函数来实现径向颜色渐变。 | `() => '#ffffaa'` |
| <b>ringResolution</b>([<i>num</i>]) | 每个圆的几何分辨率的 getter/setter，表示将圆周分成多少个切片段。值越高，圆越平滑。 | 64 |
| <b>ringMaxRadius</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 圆环对象访问器函数、属性或数值常量，用于圆的最大外半径，此时环停止传播并被移除。以角度表示。 | 2 |
| <b>ringPropagationSpeed</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 圆环对象访问器函数、属性或数值常量，用于环的传播速度，以度/秒定义。设置负值将反转方向，使环从`maxRadius`向内传播。 | 1 |
| <b>ringRepeatPeriod</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 圆环对象访问器函数、属性或数值常量，用于连续自动生成同心圆之间的时间间隔（以毫秒为单位）。小于或等于`0`的值将禁用重复并只发出一个环。 | 700 |

### labels 标签图层

| 方法 | 描述 | 默认值 |
| --- | --- | :--: |
| <b>labelsData</b>([<i>array</i>]) | 标签地图图层中表示的标签对象列表的 getter/setter。 | `[]` |
| <b>labelLat</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 标签对象访问器函数、属性或数值常量，用于纬度坐标。 | `lat` |
| <b>labelLng</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 标签对象访问器函数、属性或数值常量，用于经度坐标。 | `lng` |
| <b>labelText</b>([<i>str</i> or <i>fn</i>]) | 标签对象访问器函数或属性，用于标签文本。 | `text` |
| <b>labelColor</b>([<i>str</i> or <i>fn</i>]) | 标签对象访问器函数或属性，用于标签颜色。 | `() => 'lightgrey'` |
| <b>labelAltitude</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 标签对象访问器函数、属性或数值常量，用于标签的高度（以地球半径单位表示）。 | 0.02 |
| <b>labelSize</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 标签对象访问器函数、属性或数值常量，用于标签文本高度（以角度表示）。 | 0.5 |
| <b>labelTypeFace</b>([<i>typeface </i>]) | 文本字体类型 JSON 对象的 getter/setter。支持由 [Facetype.js](http://gero3.github.io/facetype.js/) 生成的任何字体。 | [helvetiker regular](https://github.com/mrdoob/three.js/blob/dev/examples/fonts/helvetiker_regular.typeface.json) |
| <b>labelRotation</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 标签对象访问器函数、属性或数值常量，用于标签的旋转角度（以度为单位）。旋转沿其纬度平行平面的轴顺时针执行。 | 0 |
| <b>labelResolution</b>([<i>num</i>]) | 每个标签的文本几何分辨率的 getter/setter，表示在文本曲线中使用的段数。值越高，标签越平滑。 | 3 |
| <b>labelIncludeDot</b>([<i>boolean</i>, <i>str</i> or <i>fn</i>]) | 标签对象访问器函数、属性或布尔常量，用于确定是否在文本旁边包含一个点标记，指示标签的确切 `lat`、`lng` 坐标。如果启用，文本将从点偏移渲染。 | `true` |
| <b>labelDotRadius</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 标签对象访问器函数、属性或数值常量，用于点标记的半径（以角度表示）。 | 0.1 |
| <b>labelDotOrientation</b>([<i>str</i> or <i>fn</i>]) | 标签对象访问器函数或属性，用于点标记存在时标签的方向。可能的值为 `right`、`top` 和 `bottom`。 | `() => 'bottom'` |
| <b>labelsTransitionDuration</b>([<i>num</i>]) | 用于动画化涉及位置修改（`lat`、`lng`、`altitude`、`rotation`）的标签变化的过渡持续时间（毫秒）的 getter/setter。值为 `0` 将使标签立即移动到最终位置。新标签通过缩放其大小来进行动画处理。 | 1000 |

### HTML元素图层

| 方法 | 描述 | 默认值 |
| --- | --- | :--: |
| <b>htmlElementsData</b>([<i>array</i>]) | HTML元素地图图层中表示的对象列表的 getter/setter。每个HTML元素使用 [ThreeJS CSS2DRenderer](https://threejs.org/docs/#examples/en/renderers/CSS2DRenderer) 进行渲染。 | `[]` |
| <b>htmlLat</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | HTML元素访问器函数、属性或数值常量，用于元素中心位置的纬度坐标。 | `lat` |
| <b>htmlLng</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | HTML元素访问器函数、属性或数值常量，用于元素中心位置的经度坐标。 | `lng` |
| <b>htmlAltitude</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | HTML元素访问器函数、属性或数值常量，用于元素位置的高度坐标（以地球半径单位表示）。 | 0 |
| <b>htmlElement</b>([<i>str</i> or <i>fn</i>]) | 访问器函数或属性，用于检索要使用的DOM元素。应返回 [HTMLElement](https://developer.mozilla.org/en-US/docs/Web/API/HTMLElement) 的实例。 | `null` |
| <b>htmlElementVisibilityModifier</b>([<i>fn(elem, isVisible)</i>]) | 自定义函数，定义元素如何根据它们在地球前面还是后面来显示/隐藏。该函数接收两个参数 `(elem, isVisible)`，即HTML元素和一个指示元素是否应该可见的布尔值。默认情况下，Three对象本身在地球后面时会自动隐藏。 | - |
| <b>htmlTransitionDuration</b>([<i>num</i>]) | 用于动画化HTML元素位置变化的过渡持续时间（毫秒）的 getter/setter。值为 `0` 将使元素立即移动到最终位置。 | 1000 |

### 3D对象图层

| 方法 | 描述 | 默认值 |
| --- | --- | :--: |
| <b>objectsData</b>([<i>array</i>]) | 对象图层中表示的自定义3D对象列表的 getter/setter。每个对象根据 `objectThreeObject` 方法进行渲染。 | `[]` |
| <b>objectLat</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 对象访问器函数、属性或数值常量，用于对象位置的纬度坐标。 | `lat` |
| <b>objectLng</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 对象访问器函数、属性或数值常量，用于对象位置的经度坐标。 | `lng` |
| <b>objectAltitude</b>([<i>num</i>, <i>str</i> or <i>fn</i>]) | 对象访问器函数、属性或数值常量，用于对象位置的高度坐标（以地球半径单位表示）。 | 0.01 |
| <b>objectRotation</b>([<i>{[x], [y], [z]}</i>, <i>str</i> or <i>fn</i>]) | 对象访问器函数、属性或 `{x, y, z}` 对象，用于对象的旋转（以度为单位）。每个维度都是可选的，允许仅在某些轴上旋转。旋转按 **X**->**Y**->**Z** 的顺序应用。 | - |
| <b>objectFacesSurface</b>([<i>boolean</i>, <i>str</i> or <i>fn</i>]) | 对象访问器函数、属性或布尔常量，用于确定对象是否应该旋转以面向（远离）地球表面 (`true`)，或者保持其原始宇宙方向 (`false`)。 | `true` |
| <b>objectThreeObject</b>([<i>Object3d</i>, <i>str</i> or <i>fn</i>]) | 对象访问器函数或属性，用于定义要作为对象地图图层一部分渲染的自定义3D对象。应返回 [ThreeJS Object3d](https://threejs.org/docs/index.html#api/core/Object3D) 的实例。 | 一个黄色球体 |

### 自定义图层

| 方法 | 描述 | 默认值 |
| --- | --- | :--: |
| <b>customLayerData</b>([<i>array</i>]) | 自定义地图图层中表示的项目列表的 getter/setter。每个项目根据 `customThreeObject` 方法进行渲染。 | `[]` |
| <b>customThreeObject</b>([<i>Object3d</i>, <i>str</i> or <i>fn</i>]) | 对象访问器函数或属性，用于生成要作为自定义地图图层一部分渲染的自定义3D对象。应返回 [ThreeJS Object3d](https://threejs.org/docs/index.html#api/core/Object3D) 的实例。 | `null` |
| <b>customThreeObjectUpdate</b>([<i>str</i> or <i>fn</i>]) | 对象访问器函数或属性，用于用新数据更新现有的自定义3D对象。这可用于提高数据更新的性能，因为不需要在每次更新时删除和重新创建对象。回调方法的签名包括要更新的对象及其新数据：`customThreeObjectUpdate((obj, objData) => { ... })`。 | `null` |

### 工具

| 方法 | 描述 |
| --- | --- |
| <b>getGlobeRadius</b>() | 返回地球半径在绝对空间单位中的笛卡尔距离。 ||
| <b>getCoords</b>(<i>lat</i>, <i>lng</i> [,<i>altitude</i>]) | 转换球面坐标的实用方法。给定一对纬度/经度坐标和可选的高度（以地球半径单位表示），返回等效的 `{x, y, z}` 笛卡尔空间坐标。 ||
| <b>toGeoCoords</b>({ <i>x</i>, <i>y</i>, <i>z</i> }) | 将笛卡尔坐标转换为地理域的实用方法。给定一组3D笛卡尔坐标 `{x, y, z}`，返回等效的 `{lat, lng, altitude}` 球面坐标。高度以地球半径单位定义。 ||

### 渲染选项
| 方法 | 描述 | 默认值 |
| --- | --- | :--: |
| <b>rendererSize</b>(<i>Vector2</i>) | 建议注入当前[渲染器大小](https://threejs.org/docs/#api/en/renderers/WebGLRenderer.getSize)，以确保对象比例保持恒定。在使用路径FatLines时特别必要。 | 回退到浏览器窗口的完整大小 (`THREE.Vector2(window.innerWidth, window.innerHeight)`) |
| <b>setPointOfView</b>(camera) | 有些图层需要了解相机的位置和视图方向才能正常工作。每次相机位置更改时（例如，在controls的`change`事件上），建议调用此函数，传递当前相机作为唯一参数，以保持图层以最佳状态运行并与视图同步。 | |
| <b>pauseAnimation</b>() | 暂停所有地球图层的动画。 | |
| <b>resumeAnimation</b>() | 恢复所有地球图层的动画。 | |


[npm-img]: https://img.shields.io/npm/v/three-globe
[npm-url]: https://npmjs.org/package/three-globe
[build-size-img]: https://img.shields.io/bundlephobia/minzip/three-globe
[build-size-url]: https://bundlephobia.com/result?p=three-globe
[npm-downloads-img]: https://img.shields.io/npm/dt/three-globe
[npm-downloads-url]: https://www.npmtrends.com/three-globe
