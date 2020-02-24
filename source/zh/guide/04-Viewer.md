# Viewer类-一切API的入口

之前我们已经创建了一个简单的示例Helloworld。其中我们使用的第一个cesium的API为：

``` js
var viewer = new Cesium.Viewer("cesiumContainer");
```

实质上，我们通常使用的`new Cesium.Viewer(divId, this.option)`实质上最终还是创建的`CesiumWidget`对象。可见[源码](https://github.com/CesiumGS/cesium/blob/1.66/Source/Widgets/Viewer/Viewer.js#L368)。

``` js
var viewer = new Cesium.CesiumWidget("cesiumContainer");
```

这样创建出来是不带任何组件工具简单场景。见[示例](https://sogrey.github.io/Cesium-start-Example/examples/CesiumWidget.html)

`Viewer`相当于一个包装类，它不仅包装了我们的场景还为我们包装了很多有用的工具。

## CesiumWidget

