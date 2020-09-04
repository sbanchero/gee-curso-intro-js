# Curso de introducción a GEE

Curso de introducción a Google Earth Engine (GEE), utilizando la interfaz [Code Editor](https://code.earthengine.google.com/).


## Docente

Lic. Santiago, Banchero

INTA/UNLu


## Objetivos del curso

<div style="text-align: justify">El objetivo del curso es que el alumno adquiera los conceptos principales de manejo de la herramienta Code Editor, entienda los principales objetos (Image, Feature y Colecciones) y que pueda escribir scripts para explotar diferentes colecciones de imágenes de las principales plataformas de sensoramiento remoto de libre disponibilidad.</div>

## Conocimientos previos

Las personas que tomen el curso deberían tener __nociones básicas__ de:

 * SIG y Teledetección.
 * Programación. **¡No es excluyente!** Pero la idea es que alguna vez haya tenido contacto con algún lenguaje de programación (R, Python, Matlab u otro). El lenguaje utilizado es Javascript, antes del curso sería importante que miren estos enlaces: [About JavaScript](https://developer.mozilla.org/en-US/docs/Web/JavaScript/About_JavaScript), [Una re-introducción a JavaScript (Tutorial de JS)](https://developer.mozilla.org/es/docs/Web/JavaScript/Una_re-introducci%C3%B3n_a_JavaScript), [Introduction to JavaScript for Earth Engine](https://developers.google.com/earth-engine/tutorial_js_01).
 * 

## Contenidos

 * [__Módulo 1: Conceptos básicos de EE.__](https://github.com/sbanchero/gee-curso-intro-js/blob/master/Modulos/modulo1.md)
    * Descripción de la herramienta Code Editor.
    * Cómo correr scripts en GEE y cómo funciona el cliente.
    * Estructuras de datos para gestión de datos espaciales: Image, Feature, Geometry, ImageCollection y FeatureCollection. Otras estructuras de datos: Dictionary, List, Array, Geometry, Date, Number y String.
    * Algoritmos: Invocar métodos de un objeto, llamar algoritmos definidos en la API y definir nuevas funciones.
    * Agregar datos a un mapa.
    * Buscar imágenes, colecciones de imágenes y colecciones de features.
    * Álgebra de bandas. Operadores: matemáticos, relacionales y booleanos.
    * Función _map_: ¿qué hacer en lugar de un bucle for?
    * Operadores de reducción.
    * Creación de máscaras.

 * [__Módulo 2: Gestión de almacenamiento.__](https://github.com/sbanchero/gee-curso-intro-js/blob/master/Modulos/modulo2.md)
    * Assets: Cómo persistir contenidos. Organización de contenidos.
    * Tipos de contenidos: Image, ImageCollection y Tables.
    * Uso de metadatos para la organización de contenidos.

 * [__Módulo 3: Índices espectrales y transformaciones.__](https://github.com/sbanchero/gee-curso-intro-js/blob/master/Modulos/modulo3.md)
    * Índices normalizados.
    * Definición de expresiones.
    * Transformaciones lineales.
    * Construcción de *features spaces* a partir de índices.

 * [__Módulo 4: Clasificación supervisada__](https://github.com/sbanchero/gee-curso-intro-js/blob/master/Modulos/modulo4.md)
    * Generación de conjuntos de muestras.
    * Definición de un esquema de holdout para clasificación.
    * Algoritmos básicos para clasificación supervisada: CART, SVM y Random Forest. Parametrización.
    * Evaluación de las clasificaciones: Matriz de confusión, Exactitud, Kappa.



## Referencias

  * Get Started with Earth Engine. [ [Ir](https://developers.google.com/earth-engine/getstarted) ] 
  * Managing Assets [ [Ir](https://developers.google.com/earth-engine/asset_manager) ]
  * Guías. [ [Ir](https://developers.google.com/earth-engine/) ]
  * Earth Engine resources for higher education. [ [Ir](https://developers.google.com/earth-engine/edu) ]

## ¿Cómo citar este curso?
[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.4014437.svg)](https://doi.org/10.5281/zenodo.4014437)
Santiago Banchero. (2019, May). sbanchero/gee-curso-intro-js: Version1.1 (Version v1.1). Zenodo. http://doi.org/10.5281/zenodo.4014437







