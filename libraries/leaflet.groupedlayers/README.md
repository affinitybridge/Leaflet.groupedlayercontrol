Leaflet.groupedlayercontrol
===========================

forked from https://github.com/ismyrnow/leaflet-groupedlayercontrol

Leaflet layer control with support for grouping overlays together. The layer groups also may be made collapsible.

![preview](preview.png)

[Demo](http://ismyrnow.github.io/Leaflet.groupedlayercontrol/example/basic.html)

## Usage

### Initialization

Add groupings to your overlay layers object, and swap out the default layer
control with the new one.

```javascript
var groupedOverlays = {
  "Landmarks": {
    "Motorways": motorways,
    "Cities": cities
  },
  "Points of Interest": {
    "Restaurants": restaurants
  }
};

var layerControl = L.control.groupedLayers(baseLayers, groupedOverlays, {'groupedlayers' : {'collapsible': true, 'collapsed' : true, 'expandFirst' : true}});
map.addControl(layerControl);
```

The [example](example/basic.html) shows some basic CSS styling of the new control elements.

### Adding a layer

Adding a layer individually works similarly to the default layer control, but requires that
you also specify the group name, along with the layer and layer name.

```javascript
layerControl.addOverlay(cities, "Cities", "Landmarks").
```

## Note

This plugin only affects how the layers are dislpayed in the layer control,
and not how they are rendered or layered on the map.

Grouping base layers is not currently supported.

## License

Leaflet.groupedlayercontrol is free software, and may be redistributed under
the MIT-LICENSE.
