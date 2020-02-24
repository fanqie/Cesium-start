# TerrainProvider类-地形，让三维表现更立体

很多地方我们会看到`Scene.terrainProvider`,是不是就说`terrainProvider`就是`scene`的属性？并不是！看[源码](https://github.com/CesiumGS/cesium/blob/1.66/Source/Scene/Scene.js#L1123-L1142)：
``` js
/**
 * The terrain provider providing surface geometry for the globe.
 * @memberof Scene.prototype
 *
 * @type {TerrainProvider}
 */
terrainProvider : {
    get : function() {
        if (!defined(this.globe)) {
            return undefined;
        }
        return this.globe.terrainProvider;
    },

    set : function(terrainProvider) {
        if (defined(this.globe)) {
            this.globe.terrainProvider = terrainProvider;
        }
    }
},
```
由源码看到，`terrainProvider`并不是直接归属于`scene`,而是`scene.globe`的,而`Scene.terrainProvider`相当于只是个快捷方式。
``` js
Scene.terrainProvider === scene.globe.terrainProvider
```

`scene`下这样的快捷方式还有很多。

## sampleTerrain