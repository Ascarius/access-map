Access Map
==========

jQuery plugin on top of Google Maps API for simple access map.

[MarkerOptions]: https://developers.google.com/maps/documentation/javascript/reference?hl=FR#MarkerOptions
[InfoWindowOptions]: https://developers.google.com/maps/documentation/javascript/reference?hl=FR#InfoWindowOptions
[MapOptions]: https://developers.google.com/maps/documentation/javascript/reference?hl=FR#MapOptions



Quick start
-----------

    <div id="map"></div>

    <script>
      jQuery(function ($) {
        $('#map').accessmap({
          places: [{
            lat: 48.858359,
            lng: 2.294465,
            content: "Effeil Tower"
          }],
          map: {
            zoom: 12
          }
        });
      });
    </script>



Default options
---------------

    {
      places: [
        {
          lat: 46.521533,
          lng: 6.625276,
          url: 'http://we-studio.ch'
        }
      ],
      marker: {},
      infoWindow: {},
      map: {
        zoom: 12,
        center: undefined,
        mapTypeId: maps.MapTypeId.ROADMAP,
        disableDefaultUI: true,
        disableDoubleClickZoom: true,
        draggable: false,
        scrollwheel: false
      }
    }



Options
-------

### `places` `Array`

Array of place objects.


#### `lat` `Number`

#### `lng` `Number`

#### `position` `google.maps.LatLng`

If not provided, `lat` and `lng` will be used to create a `google.maps.LatLng` object.

#### `content` `String`

Create an InfoWindow attached to the marker with this content.

Can't be used with `url`.

#### `url` `String`

URL to open on click. Can't be used with `content`.

#### `marker` `Object`

Marker options for this place.

Overrides default marker options.

Every properties of `google.maps.MarkerOptions` : [See reference][MarkerOptions]

#### `infoWindow` `Object`

InfoWindow options for this place.

Overrides default infoWindow options.

Every properties of `google.maps.InfoWindowOptions` : [See reference][InfoWindowOptions]



### `marker` `Object` : Default markers options

[See reference][MarkerOptions]



### `infoWindow` `Object` : Default infoWindows options

[See reference][InfoWindowOptions]



### `map` `Object` : Map options

[See reference][MapOptions]


#### `center` `google.maps.LatLng`

Center of the map

If undefined, position of the first place will be used.

Could be altered after initialization, because map fit to display all markers.