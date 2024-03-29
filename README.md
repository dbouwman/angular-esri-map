angular-esri-map
================

A collection of directives to help you use Esri maps and servies in an Angular app

### Demos
There are [a few demos](http://esri.github.io/angular-esri-map/examples) showing how to use this module to bring Esri maps into your own Angular applications.

### Example
Here is a quick example to get you started. Just change the paths to point to the proper libraries and go.

![App](https://raw.github.com/Esri/angular-esri-map/master/angular-esri-map.png)

```html
<!DOCTYPE html>
<html ng-app="esri-map-example">
    <head>
        <meta name="viewport" content="initial-scale=1.0, user-scalable=no">
        <meta charset="utf-8">

        <link rel="stylesheet" type="text/css" href="http://js.arcgis.com/3.11/esri/css/esri.css">
    </head>
    <body ng-controller="MapController">
        <h2>Feature Layers Example</h2>
        <esri-map id="map" center="map.center" zoom="map.zoom" basemap="topo">
            <esri-feature-layer url="http://services.arcgis.com/rOo16HdIMeOBI4Mb/arcgis/rest/services/Portland_Parks/FeatureServer/0"></esri-feature-layer>
            <esri-feature-layer url="http://services.arcgis.com/rOo16HdIMeOBI4Mb/arcgis/rest/services/Heritage_Trees_Portland/FeatureServer/0"></esri-feature-layer>
        </esri-map>
        <p>Lat: {{ map.center.lat | number:3 }}, Lng: {{ map.center.lng | number:3 }}, Zoom: {{map.zoom}}</p>
        <script type="text/javascript" src="http://js.arcgis.com/3.11compact"></script>
        <script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.2.16/angular.js"></script>
        <script src="../dist/angular-esri-map.js"></script>
        <script type="text/javascript">
            angular.module('esri-map-example', ['esri.map'])
                .controller('MapController', function ($scope) {
                    $scope.map = {
                        center: {
                            lng: -122.676207,
                            lat: 45.523452
                        },
                        zoom: 12
                    };
                });
        </script>
    </body>
</html>
```

### Development Instructions

Make sure you have [Node](http://nodejs.org/) and  [Gulp](https://github.com/gulpjs/gulp/blob/master/docs/getting-started.md#getting-started) installed.

1. [Fork and clone this repo](https://help.github.com/articles/fork-a-repo)
2. `cd` into the `angular-esri-map` folder
5. Install the dependencies with `npm install`
5. run `gulp` from the command line. This will start watching the source files and running linting and build commands.
6. Browse to the example pages under the `examples` folder
7. Make your changes and create a [pull request](https://help.github.com/articles/creating-a-pull-request)
