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

Acá agregar mini códigos de ejemplo.....

 * ee.Image
 * ee.Feature
 * ee.Geometry
 * ee.ImageCollection
 * ee.FeatureCollection


## Otras estructuras de datos

  * ee.Dictionary
  * ee.List
  * ee.Array
  * ee.Geometry
  * ee.Date
  * ee.Number
  * ee.String

Algoritmos: Invocar métodos de un objeto, llamar algoritmos definidos en la API y definir nuevas funciones.


## Agregar datos a un mapa.



  * Buscar imágenes, colecciones de imágenes y colecciones de features.
    * Álgebra de bandas. Operadores: matemáticos, relacionales y booleanos.
    * Función _map_: ¿qué hacer en lugar de un bucle for?
    * Operadores de reducción.
    * Creación de máscaras.