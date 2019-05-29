# Módulo 3: Índices espectrales y transformaciones.

## Cálcular índices normalizados

```Javascript
// Ejemplo 3.1
// Calcula el NDVI
var do_ndvi = function(image){

    return image.normalizedDifference(['B5', 'B4']).rename('NDVI');

}
```

```Javascript
// Calcula el GNDVI
var do_gndvi = function(image){

    return image.normalizedDifference(['B5', 'B3']).rename('GNDVI')

}
```

```Javascript
// Calcula el NDSI
var do_ndsi = function(image){

    return image.normalizedDifference(['B6', 'B5']).rename('NDSI')

}
```

```Javascript
// Calcula el ndbai
var do_ndbai = function(image){

    return image.normalizedDifference(['B7', 'B5']).rename('NDBaI')

}
```

## Agregar todos los índices a una imagen

```Javascript
var add_variables = function(image) {
    var im = do_ndvi( image )
    im = im.addBands( do_gndvi(image) )
             .addBands( do_ndsi(image)  )
             .addBands( do_gndvi(image) )
             .addBands( do_ndbai(image) )

    im = im.set("system:time_start", image.get('system:time_start'))
    return im
  }
```

## Generamos el stack con reducción por mediana

```Javascript
var stack_clasificacion = ic_2015_2018
                          .map(filtrar_nubes)
                          .map(add_variables).median();

Map.addLayer(stack_clasificacion, {bands: ["NDVI"],  min:0, max: 0.8},"NDVI");
Map.addLayer(stack_clasificacion, {bands: ["GNDVI"], min:-0.34, max:0.75},"GNDVI");
Map.addLayer(stack_clasificacion, {bands: ["NDSI"],  min:-0.81, max:0.25},"NDSI");
Map.addLayer(stack_clasificacion, {bands: ["NDBaI"], min:-0.85, max:0.14},"NDBaI");
```










