&lt;open-map&gt; element &lt;/open-map&gt;
==========================================

Make Open Street Maps using declarative Polymer web components. To get started read the [&lt;open-map-doc&gt;&lt;/open-map-doc&gt;] or checkout the [&lt;open-map-demo&gt;&lt;/open-map-demo&gt;].


Version
----

0.0.4

Tech
-----------

`<open-map></open-map>` use:
* [Polymer] - awesome framework.

Use guide
--------------
##### Install open-map component using [bower].

```sh
$ bower install open-map

```

##### Configure Polymer and the new component.

```html
<head>
    <script src="../platform/platform.js"></script>
    <link rel="import" href="../open-map/open-map.html">
    <style>
      html, body {
        margin: 0;
        height: 100%;
      }
      leaflet-map {
        height: 100%;
      }
    </style>
  </head>
  <body unresolved>
    <open-map longitude="77.2" latitude="28.4" mapID="examples.map-i875kd35">
      <open-marker icon="{'icon': 'twitter', 'markerColor':'red'}"></open-marker>
    </open-map>
    <script>
        var map = document.querySelector('open-map');
        var me = document.querySelectorAll('open-marker')[0];
        map.addEventListener('open-map-ready', funtion(){
            navigator.geolocation.getCurrentPosition(function(pos){
              me.latitude = pos.coords.latitude;
              me.longitude = pos.coords.longitude;
            });
        });
    </script>
  </body>
```

Personalize the map
-------------------
You can personalize the map using the [MapBoxEditor], introduce your map id in the attribute `mapID`.

License
----
MIT


[&lt;open-map-demo&gt;&lt;/open-map-demo&gt;]:https://ruben96.github.io/open-map/components/open-map/demo.html
[&lt;open-map-doc&gt;&lt;/open-map-doc&gt;]:https://ruben96.github.io/open-map
[Polymer]:http://www.polymer-project.org/
[MapBoxEditor]:https://www.mapbox.com/editor
[bower]:http://bower.io/