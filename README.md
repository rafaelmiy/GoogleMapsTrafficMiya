# MMM-GoogleMapsTraffic

![Alt text](/img/mmm-googlemapstraffic.png "A preview of the MMM-GoogleMapsTraffic module.")

A module for the [MagicMirror²](https://github.com/MichMich/MagicMirror/) that displays a map, centered at provided coordinates, with Google Maps Traffic information.

## Installation

1. Navigate into your MagicMirror's `~/MagicMirror/modules` folder and execute `git clone https://github.com/vicmora/MMM-GoogleMapsTraffic.git`. A new folder will appear navigate into it.
2. Execute `npm install` in `~/MagicMirror/modules/MMM-GoogleMapsTraffic` to install the node dependencies.

## Using the module

To use this module, add it to the modules array in the `config/config.js` file:
```js
var config = {
    modules: [
        {
            module: 'MMM-GoogleMapsTraffic',
            position: 'top_left',
            config: {
                key: 'YOUR_KEY',
                lat: 37.8262306,
                lng: -122.2920096,
                height: '300px',
                width: '300px'
            }
        }
    ]
}
```

## Configuration options

| Option               | Description
|--------------------- |-----------
| `key`                | *Required* Google api key. See below for help.
| `lat`                | *Required* Latitude used to center the map. See below for help. <br><br>**Type:** `float`
| `lng`                | *Required* Longitude used to center the map. See below for help. <br><br>**Type:** `float`
| `height`             | Height of the map. <br><br>**Type:** `string` (pixels) <br> **Default value:** `300px`
| `width`              | Width of the map. <br><br>**Type:** `string` (pixels) <br> **Default value:** `300px`
| `zoom`               | Zoom value to display from lat/lng. <br><br>**Type:** `integer` <br> **Default value:** `10`
| `mapTypeId`          | The map type to display (roadmap, satellite, hybrid, terrain).  <br><br>**Type:** `string` <br> **Default value:** `roadmap`
| `styledMapType`      | Style of the map. See below for help.<br><br>**Type:** `string`<br> **Possible value:** `standard`, `dark`, `night`, `black` or *custom*<br> **Default value:** `standard`
| `disableDefaultUI`   | Disable default UI buttons (Zoom and Street View). <br><br>**Type:** `boolean` <br> **Default value:** `true`
| `updateInterval`     | How often the module should load the map.<br><br>**Type:** `int` in millisecond<br> **Default value:** `900000 (15 mins)`

## Google API Key

Obtain an api at [Google Developer's page](https://developers.google.com/maps/documentation/javascript/).

## Coordinates

The easiest way to obtain latitude and longitude coordinates is via [Google Maps](https://maps.google.com). Type an address, location, or center the map where you'd like it centered. The coordinates will appear in the address bar as seen below.

![Alt text](/img/coordinates.png "Google Maps coordinates.")

## Map style

The easiest way to create your own styled map is via [Google Maps APIs Styling Wizard](https://mapstyle.withgoogle.com/). Create a new file in `~/MagicMirror/modules/MMM-GoogleMapsTraffic/mapStyle` , using the style name as the filename. Copy JSON data generated by wizard into this file.

## Dependencies

Installed via `npm install`:
- fs
- [path](https://www.npmjs.com/package/path)
