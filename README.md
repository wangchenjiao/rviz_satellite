## rviz_satellite

Plugin for rviz for displaying satellite maps loaded from the internet.

![Alt text](.screenshot.png?raw=true "Fucking Awesome Dude")

### Usage

In order to use rviz_satellite, add this package to your catkin workspace. Then add an instance of `AerialMapDisplay` to your rviz config.

The `Topic` field must point to a latched publisher of `sensor_msgs/NavSatFix`. Note that rviz_satellite will not repeatedly reload the same GPS coordinates twice (unless you modify something in the GUI options).

You must provide an `Object URI` (or URL) from which the satellite images are loaded. rviz_satellite presently only supports the [OpenStreetMap](http://wiki.openstreetmap.org/wiki/Slippy_map_tilenames) convention for tile names.

The URI should have the form:

``http://otile1.mqcdn.com/tiles/1.0.0/sat/{z}/{x}/{y}.jpg``

This is the default URI, which will load data from MapQuest. The tiles are free, and go up to zoom level 18. For higher zoom levels, consider using [MapBox](https://www.mapbox.com).

### Options

- `Alpha` is simply the display transparency.
- `Draw Under` will cause the map to be displayed below all other geometry.
- `Zoom` is the zoom level of the map. Recommended values are 16-19, as anything smaller is _very_ low resolution. 19 is the current max.
- `Blocks` number of adjacent blocks to load. rviz_satellite will load the central block, and this many blocks around the center. 6 is the current max.

### Questions, Bugs

Contact the author (gareth-cross on github), or open an issue.
