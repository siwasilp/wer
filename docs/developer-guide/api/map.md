# Map

The `Map` object represents the Mini Tokyo 3D map on your page. You create a `Map` by specifying a `container` and other options. Then Mini Tokyo 3D initializes the map on the page and returns your `Map` object.

Extends [Evented](https://docs.mapbox.com/mapbox-gl-js/api/events/#evented).

```js
new Map(options: Object)
```

## Parameters

### **`options`** ([`Object`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object))

Name | Description
:-- | :--
**`options.accessToken`**<br>[`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String) | Access token for [Mapbox](https://www.mapbox.com). If you don't specify this token, an error will occur when loading the map, so make sure to get an access token specific to your web site.
**`options.bearing`**<br>[`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)<br>default: `0` | The initial bearing (rotation) of the map, measured in degrees counter-clockwise from north. If not specified, it will default to `0`.
**`options.center`**<br>[`LngLatLike`](https://docs.mapbox.com/mapbox-gl-js/api/geography/#lnglatlike)<br>default: `[139.7670, 35.6814]` | The initial geographical centerpoint of the map. If not specified, it will default to around Tokyo station (`[139.7670, 35.6814]`). Note: Mini Tokyo 3D uses longitude, latitude coordinate order to match GeoJSON.
**`options.clockControl`**<br>[`boolean`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)<br>default: `true` | If `true`, the date and time display will be added to the map.
**`options.configControl`**<br>[`boolean`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)<br>default: `true` | If `true`, the configuration buttons will be added to the map.
**`options.container`**<br>[`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String) | The `id` of the HTML element in which Mini Tokyo 3D will render the map. The specified element must have no children.
**`options.dataUrl`**<br>[`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String) | Mini Tokyo 3D data URL. If not specified, `'https://minitokyo3d.com/data'` will be used.
**`options.ecoFrameRate`**<br>[`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)<br>default: `1` | Frame rate for train and airplane animations (frames per second) when Eco Mode is on. Specify on a scale of 1 to 60. Lower values result in less smoother animations and lower CPU resource usage, thus reducing battery consumption on mobile devices. If not specified, it will default to `1`.
**`options.ecoMode`**<br>[`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)<br>default: `'normal'` | The initial eco mode. `'normal'` and `'eco'` are supported.
**`options.fullscreenControl`**<br>[`boolean`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)<br>default: `true` | If `true`, the fullscreen button will be added to the map.
**`options.lang`**<br>[`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String) | [IETF language tag](https://en.wikipedia.org/wiki/IETF_language_tag) for the language. If not specified, the browser's default language is used. Currently `'ja'`, `'en'`, `'ko'`, `'zh-Hans'`, `'zh-Hant'`, `'th'`, `'ne'`, `'pt-BR'` and `'fr'` are supported. If an unsupported language is specified, then `'en'` is used.
**`options.modeControl`**<br>[`boolean`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)<br>default: `true` | If `true`, the mode switch buttons will be added to the map.
**`options.navigationControl`**<br>[`boolean`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)<br>default: `true` | If `true`, the navigation buttons will be added to the map.
**`options.pitch`**<br>[`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)<br>default: `60` | The initial pitch (tilt) of the map, measured in degrees away from the plane of the screen (0-85). If not specified, it will default to `60`.
**`options.plugins`**<br>[`Array`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Array)`<`[`PluginInterface`](./plugin.md)`>` | An array of plugins to add. Each plugin must implement [PluginInterface](./plugin.md).
**`options.searchControl`**<br>[`boolean`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean)<br>default: `true` | If `true`, the search button will be added to the map.
**`options.secrets`**<br>[`Secrets`](./secrets.md) | An object to store the access tokens used to retrieve data.
**`options.selection`**<br>[`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String) | ID of the train or flight to be tracked. The train ID is a string in the form of `'odpt.Train:<operator ID>.<railway ID>.<train number>'`. The fright ID is a string in the form of `'odpt.FlightInformationArrival:<operator ID>.<airport ID>.<flight number>'` or `'odpt.FlightInformationDeparture:<operator ID>.<airport ID>.<flight number>'`. The `'odpt.*:'` part can be omitted. For details, see the [Public Transportation Open Data Center: API Specification](https://developer.odpt.org/en/documents).
**`options.trackingMode`**<br>[`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)<br>default: `'position'` | The initial tracking mode. `'position'`, `'back'`, `'topback'`, `'front'`, `'topfront'`, `'helicopter'`, `'drone'` and `'bird'` are supported.
**`options.zoom`**<br>[`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)<br>default: `14` | The initial zoom level of the map. If not specified, it will default to `14`.

## Instance Members

### **`addLayer(layer)`**

Adds a layer to the map.

#### Parameters

**`layer`** ([`Object`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object) | [`CustomLayerInterface`](https://docs.mapbox.com/mapbox-gl-js/api/properties/#customlayerinterface) | [`GeoJsonLayerInterface`](./geojson-layer.md) | [`ThreeLayerInterface`](./three-layer.md) | [`Tile3DLayerInterface`](./tile-3d-layer.md)) The layer to add, conforming to either the Mapbox Style Specification's [layer definition](https://docs.mapbox.com/mapbox-gl-js/style-spec/#layers), the [CustomLayerInterface](https://docs.mapbox.com/mapbox-gl-js/api/properties/#customlayerinterface) specification, the [GeoJsonLayerInterface](./geojson-layer.md) specification, the [ThreeLayerInterface](./three-layer.md) specification or the [Tile3DLayerInterface](./tile-3d-layer.md) specification.

#### Returns

[`Map`](./map.md): Returns itself to allow for method chaining.

---

### **`easeTo(options)`**

Changes any combination of `center`, `zoom`, `bearing`, `pitch`, and `padding` with an animated transition between old and new values. The map will retain its current values for any details not specified in `options`.

Note: The transition will happen instantly if the user has enabled the `reduced motion` accessibility feature enabled in their operating system, unless `options` includes `essential: true`.

#### Parameters

**`options`** ([`Object`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)) Options describing the destination and animation of the transition. Accepts [CameraOptions](https://docs.mapbox.com/mapbox-gl-js/api/properties/#cameraoptions) and [AnimationOptions](https://docs.mapbox.com/mapbox-gl-js/api/properties/#animationoptions).

#### Returns

[`Map`](./map.md): Returns itself to allow for method chaining.

---

### **`flyTo(options)`**

Changes any combination of `center`, `zoom`, `bearing`, and `pitch`, animating the transition along a curve that evokes flight. The animation seamlessly incorporates zooming and panning to help the user maintain their bearings even after traversing a great distance.

If a user has the `reduced motion` accessibility feature enabled in their operating system, the animation will be skipped and this will behave equivalently to `jumpTo`, unless `options` includes `essential: true`.

#### Parameters

**`options`** ([`Object`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)) Options describing the destination and animation of the transition. Accepts [CameraOptions](https://docs.mapbox.com/mapbox-gl-js/api/properties/#cameraoptions), [AnimationOptions](https://docs.mapbox.com/mapbox-gl-js/api/properties/#animationoptions), and the following additional options.

Name | Description
:-- | :--
**`options.curve`**<br>[`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)<br>default: `1.42` | The zooming "curve" that will occur along the flight path. A high value maximizes zooming for an exaggerated animation, while a low value minimizes zooming for an effect closer to [Map#easeTo](./map.md#easeto-options). 1.42 is the average value selected by participants in the user study discussed in [van Wijk (2003)](https://www.win.tue.nl/~vanwijk/zoompan.pdf). A value of `Math.pow(6, 0.25)` would be equivalent to the root mean squared average velocity. A value of 1 would produce a circular motion. If `options.minZoom` is specified, this option will be ignored.
**`options.maxDuration`**<br>[`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number) | The animation's maximum duration, measured in milliseconds. If duration exceeds maximum duration, it resets to 0.
**`options.minZoom`**<br>[`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number) | The zero-based zoom level at the peak of the flight path. If this option is specified, `options.curve` will be ignored.
**`options.screenSpeed`**<br>[`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number) | The average speed of the animation measured in screenfuls per second, assuming a linear timing curve. If `options.speed` is specified, this option is ignored.
**`options.speed`**<br>[`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)<br>default: `1.2` | The average speed of the animation defined in relation to `options.curve`. A speed of 1.2 means that the map appears to move along the flight path by 1.2 times `options.curve` screenfuls every second. A *screenful* is the map's visible span. It does not correspond to a fixed physical distance, but varies by zoom level.

#### Returns

[`Map`](./map.md): Returns itself to allow for method chaining.

---

### **`getBearing()`**

Returns the map's current bearing. The bearing is the compass direction that is "up"; for example, a bearing of 90° orients the map so that east is up.

#### Returns

[`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number): The map's current bearing.

---

### **`getCenter()`**

Returns the map's geographical centerpoint.

#### Returns

[`LngLat`](https://docs.mapbox.com/mapbox-gl-js/api/geography/#lnglat): The map's geographical centerpoint.

---

### **`getClockMode()`**

Returns the current clock mode.

#### Returns

[`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String): A string representing the current clock mode. Either `'realtime'` or `'playback'`.

---

### **`getEcoMode()`**

Returns the current eco mode.

#### Returns

[`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String): A string representing the current eco mode. Either `'normal'` or `'eco'`.

---

### **`getMapboxMap()`**

Returns the Mapbox's [`Map`](https://docs.mapbox.com/mapbox-gl-js/api/map/) object used in the map.

#### Returns

[`Map`](https://docs.mapbox.com/mapbox-gl-js/api/map/): The Mapbox's Map.

---

### **`getModelPosition(lnglat, altitude)`**

Projects a `LngLat` to a `MercatorCoordinate`, and returns the translated mercator coordinates with Tokyo Station as the origin.

#### Parameters

**`lnglat`** ([`LngLatLike`](https://docs.mapbox.com/mapbox-gl-js/api/geography/#lnglatlike)) The location to project.

**`altitude`** ([`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)) The altitude in meters of the position.

#### Returns

{x: [`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number), y: [`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number), z: [`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)}: The translated mercator coordinates with Tokyo Station as the origin.

---

### **`getModelScale()`**

Returns the scale to transform into `MercatorCoordinate` from coordinates in real world units using meters. This provides the distance of 1 meter in `MercatorCoordinate` units at Tokyo Station.

#### Returns

[`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number): The scale to transform into `MercatorCoordinate` from coordinates in real world units using meters.

---

### **`getPitch()`**

Returns the map's current pitch (tilt).

#### Returns

[`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number): The map's current pitch, measured in degrees away from the plane of the screen.

---

### **`getSelection()`**

Returns the ID of the train or flight being tracked.

#### Returns

[`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String): The ID of the train or flight being tracked. The train ID is a string in the form of `'<operator ID>.<line ID>.<train number>'`. The flight ID is a string in the form of `'<operator ID>.<airport ID>.<flight number>'`.

---

### **`getTrackingMode()`**

Returns the current tracking mode. See [here](../../user-guide/configuration.md#tracking-mode-settings) for details of the tracking modes.

#### Returns

[`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String): A string representing the current tracking mode. Either `'position'`, `'back'`, `'topback'`, `'front'`, `'topfront'`, `'helicopter'`, `'drone'` or `'bird'`.

::: warning
The tracking mode `'heading'` is deprecated and falls back to `'topback'`.
:::

---

### **`getViewMode()`**

Returns the current view mode.

#### Returns

[`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String): A string representing the current view mode. Either `'ground'` or `'underground'`.

---

### **`getZoom()`**

Returns the map's current zoom level.

#### Returns

[`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number): The map's current zoom level.

---

### **`hasDarkBackground()`**

Checks if the background color of the map is dark.

#### Returns

[`boolean`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Boolean): `true` if the background color of the map is dark, `false` otherwise.

---

### **`jumpTo(options)`**

Changes any combination of `center`, `zoom`, `bearing`, and `pitch`, without an animated transition. The map will retain its current values for any details not specified in `options`.

#### Parameters

**`options`** ([`CameraOptions`](https://docs.mapbox.com/mapbox-gl-js/api/properties/#cameraoptions)) Options object.

#### Returns

[`Map`](./map.md): Returns itself to allow for method chaining.

---

### **`off(type, listener)`**

Removes an event listener previously added with [`Map#on`](./map.md#on-type-listener).

#### Parameters

**`type`** ([`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)) The event type previously used to install the listener.

**`listener`** ([`Function`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)) The function previously installed as a listener.

#### Returns

[`Map`](./map.md): Returns itself to allow for method chaining.

---

### **`on(type, listener)`**

Adds a listener for events of a specified type.

#### Parameters

**`type`** ([`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)) The event type to listen for.

**`listener`** ([`Function`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)) The function to be called when the event is fired.

#### Returns

[`Map`](./map.md): Returns itself to allow for method chaining.

---

### **`once(type, listener)`**

Adds a listener that will be called only once to a specified event type.

#### Parameters

**`type`** ([`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)) The event type to add a listener for.

**`listener`** ([`Function`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Statements/function)) The function to be called when the event is fired.

#### Returns

[`Map`](./map.md): Returns itself to allow for method chaining.

---

### **`removeLayer(id)`**

Removes the layer with the given ID from the map.

If no such layer exists, an `error` event is fired.

#### Parameters

**`id`** ([`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)) ID of the layer to remove.

#### Returns

[`Map`](./map.md): Returns itself to allow for method chaining.

---

### **`setBearing(bearing)`**

Sets the map's bearing (rotation). The bearing is the compass direction that is "up"; for example, a bearing of 90° orients the map so that east is up.

Equivalent to `jumpTo({bearing: bearing})`.

#### Parameters

**`bearing`** ([`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)) The desired bearing.

#### Returns

[`Map`](./map.md): Returns itself to allow for method chaining.

---

### **`setCenter(center)`**

Sets the map's geographical centerpoint. Equivalent to `jumpTo({center: center})`.

#### Parameters

**`center`** ([`LngLatLike`](https://docs.mapbox.com/mapbox-gl-js/api/geography/#lnglatlike)) The centerpoint to set.

#### Returns

[`Map`](./map.md): Returns itself to allow for method chaining.

---

### **`setClockMode(mode)`**

Sets the clock mode. In the real-time clock mode (`'realtime'`), trains and airplanes are displayed on the map according to the actual operation at the current time. In the playback clock mode (`'playback'`), you can specify the time and the speed of time passing.

#### Parameters

**`mode`** ([`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)) A string representing the clock mode. Either `'realtime'` or `'playback'`.

#### Returns

[`Map`](./map.md): Returns itself to allow for method chaining.

---

### **`setEcoMode(mode)`**

Sets the eco mode. In the normal mode (`'normal'`), the frame rate for train and airplane animations will be set to 60. In the eco mode (`'eco'`), the frame rate will be set to the [`Map`](./map.md) constructor option `ecoFrameRate`.

#### Parameters

**`mode`** ([`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)) A string representing the eco mode. Either `'normal'` or `'eco'`.

#### Returns

[`Map`](./map.md): Returns itself to allow for method chaining.

---

### **`setLayerVisibility(layerId, visibility)`**

Sets the visibility of the layer. Specify `'visible'` to make it visible, or `'none'` to make it invisible.

#### Parameters

**`layerId`** ([`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)) The ID of the layer to set the visibility in.

**`visibility`** ([`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)) Whether this layer is displayed. Either `'visible'` or `'none'`.

#### Returns

[`Map`](./map.md): Returns itself to allow for method chaining.

---

### **`setPitch(pitch)`**

Sets the map's pitch (tilt). Equivalent to `jumpTo({pitch: pitch})`.

#### Parameters

**`pitch`** ([`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)) The pitch to set, measured in degrees away from the plane of the screen (0-85).

#### Returns

[`Map`](./map.md): Returns itself to allow for method chaining.

---

### **`setSelection(id)`**

Sets the ID of the train or flight you want to track. The train ID is a string in the form of `'odpt.Train:<operator ID>.<railway ID>.<train number>'`. The fright ID is a string in the form of `'odpt.FlightInformationArrival:<operator ID>.<airport ID>.<flight number>'` or `'odpt.FlightInformationDeparture:<operator ID>.<airport ID>.<flight number>'`. The `'odpt.*:'` part can be omitted. For details, see the [Public Transportation Open Data Center: API Specification](https://developer.odpt.org/en/documents).

#### Parameters

**`id`** ([`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)) ID of the train or flight to be tracked.

#### Returns

[`Map`](./map.md): Returns itself to allow for method chaining.

---

### **`setTrackingMode(mode)`**

Sets the tracking mode. See [here](../../user-guide/configuration.md#tracking-mode-settings) for details of the tracking modes.

#### Parameters

**`mode`** ([`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)) A string representing the tracking mode. Either `'position'`, `'back'`, `'topback'`, `'front'`, `'topfront'`, `'helicopter'`, `'drone'` or `'bird'`.

::: warning
The tracking mode `'heading'` is deprecated and falls back to `'topback'`.
:::

#### Returns

[`Map`](./map.md): Returns itself to allow for method chaining.

---

### **`setViewMode(mode)`**

Sets the view mode. In the ground view mode (`ground'`), ground railways, stations, trains and airplanes will be displayed brightly, and underground railways, stations and trains will be translucent. In the underground view mode (`'underground'`), the map will turn dark and ground railways, stations, trains and airplanes will be translucent, while underground railways, stations and trains will appear brighter.

#### Parameters

**`mode`** ([`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)) A string representing the view mode. Either `'ground'` or `'underground'`.

#### Returns

[`Map`](./map.md): Returns itself to allow for method chaining.

---

### **`setZoom(zoom)`**

Sets the map's zoom level. Equivalent to `jumpTo({zoom: zoom})`.

#### Parameters

**`zoom`** ([`number`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Number)) The zoom level to set (0-22).

#### Returns

[`Map`](./map.md): Returns itself to allow for method chaining.

## Events

### **`boxzoomcancel`**

Fired when the user cancels a "box zoom" interaction, or when the bounding box does not meet the minimum size threshold. See [BoxZoomHandler](https://docs.mapbox.com/mapbox-gl-js/api/handlers/#boxzoomhandler).

**Type** [`MapBoxZoomEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapboxzoomevent)

---

### **`boxzoomend`**

Fired when a "box zoom" interaction ends. See [BoxZoomHandler](https://docs.mapbox.com/mapbox-gl-js/api/handlers/#boxzoomhandler).

**Type** [`MapBoxZoomEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapboxzoomevent)

---

### **`boxzoomstart`**

Fired when a "box zoom" interaction starts. See [BoxZoomHandler](https://docs.mapbox.com/mapbox-gl-js/api/handlers/#boxzoomhandler).

**Type** [`MapBoxZoomEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapboxzoomevent)

---

### **`click`**

Fired when a pointing device (usually a mouse) is pressed and released at the same point on the map.

**Type** [`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent)

---

### **`clockmode`**

Fired when the clock mode is changed.

**Type** [`Object`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)

#### Properties

**`mode`** ([`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)): A string representing the clock mode. Either `'realtime'` or `'playback'`.

---

### **`contextmenu`**

Fired when the right button of the mouse is clicked or the context menu key is pressed within the map.

**Type** [`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent)

---

### **`dblclick`**

Fired when a pointing device (usually a mouse) is pressed and released twice at the same point on the map in rapid succession.

**Type** [`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent)

---

### **`deselection`**

Fired when a train or airplane tracking is canceled.

**Type** [`Object`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)

#### Properties

**`deselection`** ([`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)): The ID of the train or flight whose tracking is canceled. The train ID is a string in the form of `'<operator ID>.<line ID>.<train number>'`. The flight ID is a string in the form of `'<operator ID>.<airport ID>.<flight number>'`.

---

### **`drag`**

Fired repeatedly during a "drag to pan" interaction. See [DragPanHandler](https://docs.mapbox.com/mapbox-gl-js/api/handlers/#dragpanhandler).

**Type** ([`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent) | [`MapTouchEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#maptouchevent))

---

### **`dragend`**

Fired when a "drag to pan" interaction ends. See [DragPanHandler](https://docs.mapbox.com/mapbox-gl-js/api/handlers/#dragpanhandler).

**Type** ([`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent) | [`MapTouchEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#maptouchevent))

---

### **`dragstart`**

Fired when a "drag to pan" interaction starts. See [DragPanHandler](https://docs.mapbox.com/mapbox-gl-js/api/handlers/#dragpanhandler).

**Type** ([`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent) | [`MapTouchEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#maptouchevent))

---

### **`ecomode`**

Fired when the eco mode is changed.

**Type** [`Object`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)

#### Properties

**`mode`** ([`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)): A string representing the eco mode. Either `'normal'` or `'eco'`.

---

### **`error`**

Fired when an error occurs. This is Mini Tokyo 3D's primary error reporting mechanism. We use an event instead of `throw` to better accommodate asynchronous operations. If no listeners are bound to the `error` event, the error will be printed to the console.

**Type** [`Object`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)

#### Properties

**`message`** ([`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)): Error message.

---

### **`load`**

Fired immediately after all necessary resources have been downloaded and the first visually complete rendering of the map has occurred.

**Type** [`Object`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)

---

### **`mousedown`**

Fired when a pointing device (usually a mouse) is pressed within the map.

**Type** [`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent)

---

### **`mousemove`**

Fired when a pointing device (usually a mouse) is moved while the cursor is inside the map. As you move the cursor across the map, the event will fire every time the cursor changes position within the map.

**Type** [`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent)

---

### **`mouseover`**

Fired when a pointing device (usually a mouse) is moved within the map. As you move the cursor across a web page containing a map, the event will fire each time it enters the map or any child elements.

**Type** [`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent)

---

### **`mouseup`**

Fired when a pointing device (usually a mouse) is released within the map.

**Type** [`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent)

---

### **`move`**

Fired repeatedly during an animated transition from one view to another, as the result of either user interaction or methods such as [Map#flyTo](./map.md#flyto-options).

**Type** ([`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent) | [`MapTouchEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#maptouchevent))

---

### **`moveend`**

Fired just after the map completes a transition from one view to another, as the result of either user interaction or methods such as [Map#jumpTo](./map.md#jumpto-options).

**Type** ([`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent) | [`MapTouchEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#maptouchevent))

---

### **`movestart`**

Fired just before the map begins a transition from one view to another, as the result of either user interaction or methods such as [Map#jumpTo](./map.md#jumpto-options).

**Type** ([`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent) | [`MapTouchEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#maptouchevent))

---

### **`pitch`**

Fired repeatedly during the map's pitch (tilt) animation between one state and another as the result of either user interaction or methods such as [Map#flyTo](./map.md#flyto-options).

**Type** [`MapDataEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapdataevent)

---

### **`pitchend`**

Fired immediately after the map's pitch (tilt) finishes changing as the result of either user interaction or methods such as [Map#flyTo](./map.md#flyto-options).

**Type** [`MapDataEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapdataevent)

---

### **`pitchstart`**

Fired whenever the map's pitch (tilt) begins a change as the result of either user interaction or methods such as [Map#flyTo](./map.md#flyto-options).

**Type** [`MapDataEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapdataevent)

---

### **`resize`**

Fired immediately after the map has been resized.

---

### **`rotate`**

Fired repeatedly during a "drag to rotate" interaction. See [DragRotateHandler](https://docs.mapbox.com/mapbox-gl-js/api/handlers/#dragrotatehandler).

**Type** ([`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent) | [`MapTouchEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#maptouchevent))

---

### **`rotateend`**

Fired when a "drag to rotate" interaction ends. See [DragRotateHandler](https://docs.mapbox.com/mapbox-gl-js/api/handlers/#dragrotatehandler).

**Type** ([`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent) | [`MapTouchEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#maptouchevent))

---

### **`rotatestart`**

Fired when a "drag to rotate" interaction starts. See [DragRotateHandler](https://docs.mapbox.com/mapbox-gl-js/api/handlers/#dragrotatehandler).

**Type** ([`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent) | [`MapTouchEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#maptouchevent))

---

### **`selection`**

Fired when a train or airplane tracking is initiated.

**Type** [`Object`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)

#### Properties

**`selection`** ([`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)): The ID of the train or flight whose tracking is initiated. The train ID is a string in the form of `'<operator ID>.<line ID>.<train number>'`. The flight ID is a string in the form of `'<operator ID>.<airport ID>.<flight number>'`.

---

### **`touchcancel`**

Fired when a [`touchcancel`](https://developer.mozilla.org/docs/Web/Events/touchcancel) event occurs within the map.

**Type** [`MapTouchEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#maptouchevent)

---

### **`touchend`**

Fired when a [`touchend`](https://developer.mozilla.org/docs/Web/Events/touchend) event occurs within the map.

**Type** [`MapTouchEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#maptouchevent)

---

### **`touchmove`**

Fired when a [`touchmove`](https://developer.mozilla.org/docs/Web/Events/touchmove) event occurs within the map.

**Type** [`MapTouchEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#maptouchevent)

---

### **`touchstart`**

Fired when a [`touchstart`](https://developer.mozilla.org/docs/Web/Events/touchstart) event occurs within the map.

**Type** [`MapTouchEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#maptouchevent)

---

### **`trackingmode`**

Fired when the tracking mode is changed.

**Type** [`Object`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)

#### Properties

**`mode`** ([`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)): A string representing the tracking mode. Either `'position'`, `'back'`, `'topback'`, `'front'`, `'topfront'`, `'helicopter'`, `'drone'` or `'bird'`.

::: warning
The tracking mode `'heading'` is deprecated and falls back to `'topback'`.
:::

---

### **`viewmode`**

Fired when the view mode is changed.

**Type** [`Object`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/Object)

#### Properties

**`mode`** ([`string`](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects/String)): A string representing the view mode. Either `'ground'` or `'underground'`.

---

### **`wheel`**

Fired when a [`wheel`](https://developer.mozilla.org/docs/Web/Events/wheel) event occurs within the map.

**Type** [`MapWheelEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapwheelevent)

---

### **`zoom`**

Fired repeatedly during an animated transition from one zoom level to another, as the result of either user interaction or methods such as [Map#flyTo](./map.md#flyto-options).

**Type** ([`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent) | [`MapTouchEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#maptouchevent))

---

### **`zoomend`**

Fired just after the map completes a transition from one zoom level to another, as the result of either user interaction or methods such as [Map#flyTo](./map.md#flyto-options).

**Type** ([`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent) | [`MapTouchEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#maptouchevent))

---

### **`zoomstart`**

Fired just before the map begins a transition from one zoom level to another, as the result of either user interaction or methods such as [Map#flyTo](./map.md#flyto-options).

**Type** ([`MapMouseEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#mapmouseevent) | [`MapTouchEvent`](https://docs.mapbox.com/mapbox-gl-js/api/events/#maptouchevent))
