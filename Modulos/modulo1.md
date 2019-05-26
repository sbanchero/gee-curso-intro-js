# Módulo 1: Conceptos básicos de EE.

## Descripción de la herramienta Code Editor.

[Code Editor](https://code.earthengine.google.com) (CE) es uno de los clientes para comunicarnos con la API de Google Earth Engine.

![Interfaz-Code-Editor](https://developers.google.com/earth-engine/images/Playground_diagram_v3_crop.png)

 - __Buscador__: Herramienta de búsqueda de datos disponibles en la plataforma. Además, podemos buscar lugares y posicionar el mapa a partir de un topónimo.
 - __Panel Izquierdo__
    - __Scripts__: Espacio de almacenamiento de nuestro código fuente.
    - __Docs__: Documentación sobre la API de ee.
    - __Assets__: Espacio de almacenamiento de nuestros datos, de __*manera gratuita*__ disponemos de __¡¡250GB!!__
 - __Editor de código fuente:__ 

## Los datos disponibles

![Datos-Disponibles](imgs/catalogo.png)


## ¿Cómo utilizar GEE?

 - Javascript API
    - Interactive Code Editor
    - Node.js*

 - Python API
	- Python module
	- Web Apps with Appengine
	- Jupyter Notebooks*

Ambos son clientes que se conectan a la API de GEE.

## ¿Cómo se corre un scripts en CE?


```Javascript
var start_date = "2018-12-01";
var end_date   = "2019-03-31";
var Landsat8SRT1 = ee.ImageCollection("LANDSAT/LC08/C01/T1_SR")
                     .filterBounds(limite)
                     .filterDate(start_date, end_date);
                     
print("# Escenas", Landsat8SRT1.size())
```

    https://code.earthengine.google.com/39d64cf21b212c5d7137549edcb2f7ac

## Estructuras de datos para gestión de datos espaciales

### ee.Image

```Javascript
var escena = ee.Image('LANDSAT/LC08/C01/T1_SR/LC08_225086_20181230');
// Objeto Image
print(escena)
// Lista con los nombres de las bandas
print(escena.bandNames())
// Objeto Image de un subconjunto de bandas que son renombradas
print(escena.select(["B2", "B3", "B4"],["blue","green","red"]))
```

### ee.Geometry

```Javascript
var un_poligono = ee.Geometry.Polygon(
        [[[-60.024, -36.816],
          [-60.024, -36.888],
          [-59.927, -36.888],
          [-59.927, -36.816]]], null, false);
          
print("Un Polígono:", un_poligono);
print("Área m2:", un_poligono.area(1));
print("Área km2:", un_poligono.area(1).multiply(0.0001).ceil());
```

### ee.Feature

```Javascript
var propiedades = {"Nombre": "Lote 1", "Descripcion": "Cultivos de Invierno"}
var un_feature = ee.Feature(un_poligono, propiedades)
print("Un Feature:", un_feature)
print("Área km2:", un_feature.area(1).multiply(0.0001))
print("Un Feature:", ee.String(un_feature.get("Nombre")))
```

## Trabajar con colecciones

![IC](imgs/image-collection.png)


### ee.ImageCollection

```Javascript
var ic_landsat8_SR = ee.ImageCollection("LANDSAT/LC08/C01/T1_SR");
var periodo_1 = {
  start_date: "2017-03-01",
  end_date:   "2017-06-30",
}
var ic_otoño = ic_landsat8_SR
                  .filterBounds(limite)
                  //.filterDate(periodo_1.start_date, periodo_1.end_date)
                  //.filterMetadata("CLOUD_COVER", "less_than", 10)
                  //.filterMetadata("WRS_PATH", "equals", 225)
                  //.filterMetadata("WRS_ROW", "equals", 86)
                  //.select(["B2","B3","B4","B5","B6"]);
print(ic_otoño);
print(ic_otoño.mosaic())
```

### ee.FeatureCollection

```Javascript
var fc_deptos = ee.FeatureCollection("users/santiagobanchero/curso-gee/departamentos");
print("# Deptos:", fc_deptos.size())
print("Un Feature:", fc_deptos.first())

var partido_azul = fc_deptos.filterMetadata("NAM", "equals", "Azul");
print("Feature Azul:", partido_azul);
print("Superficie Azul:", ee.Feature(partido_azul.first()).area().multiply(0.0001));

```
## Agregar layers al mapa

## Configurar la visualización de rasters
```Javascript
var vis_RGB = {bands: ["B4","B3","B2"], min: 66, max: 1600}

var vis_FalsoColor = {
    bands: ["B5","B4","B3"], 
    min: 150, 
    max: 5300, 
    gamma: 1.4}

Map.addLayer(mosaico, vis_RGB, "RGB");
Map.addLayer(mosaico, vis_FalsoColor, "Falso Color");
Map.setOptions("HYBRID");
```

## Operadores de ee.Image

### Álgebra de bandas


* Operadores: matemáticos, relacionales y booleanos
* Creación de máscaras.
* Operador _where_


## Función _map_: ¿qué hacer en lugar de un bucle for?


## Operadores de reducción.


# Referencias

* [IMAGE PROCESSING ALGORITHMS PART 6: GAMMA CORRECTION](https://www.dfstudios.co.uk/articles/programming/image-programming-algorithms/image-processing-algorithms-part-6-gamma-correction/)







