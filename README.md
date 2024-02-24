# Internet-Mapping-Class
Repository for mapping assignments

<html lang="en">

<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="initial-scale=1,maximum-scale=1,user-scalable=no" />
<title>ArcGIS Maps SDK for JavaScript Tutorials: Display a map</title>
  </style>
</head>
<body>
<div id="viewDiv"></div>
</body>
</html>

</head>

<body>
  <div id="viewDiv"></div>
  
  <link rel="stylesheet" //href="https://js.arcgis.com/4.28/esri/themes/light/main.css" />
//  <script src="https://js.arcgis.com/4.28/"></script>
  
   <style>
    html,
    body,
    #viewDiv {
      padding: 1%;
      margin: 0;
      height: 100%;
      width: 90%;
    }
  </style>
  <script>
    require([
      "esri/widgets/Sketch",
      "esri/Map",
      "esri/layers/GraphicsLayer",
      "esri/views/MapView",
      "esri/widgets/Home"
    ], (Sketch, Map, GraphicsLayer, MapView, Home) => {
      const graphicsLayer = new GraphicsLayer();

      const map = new Map({
        basemap: "topo-vector",
        layers: [graphicsLayer]
      });

      const view = new MapView({
        container: "viewDiv",
        map: map,
        zoom: 6,
        center: [-70, 45]
      });

      view.when(() => {
        const sketch = new Sketch({
          layer: graphicsLayer,
          view: view,
          // graphic will be selected as soon as it is created
          creationMode: "update"
        });

        view.ui.add(sketch, "top-right");
        view.ui.add(home, "top-left")
      });
    });
  </script>
</body>
</html>
