# Módulo 4: Clasificación supervisada

## Generación de conjuntos de muestras.

```Javascript
// Muestreo
var muestras = agua.merge(cultivos).merge(bosques).merge(ganaderia);

// Extracciones de valores de las bandas
var fc_muestras_bandas = stack_clasificacion
                .median()
                .sampleRegions(
                        muestras, 
                        ["clase"], 30, null, 1, true);
```


## Definición de un esquema de holdout para clasificación.

```Javascript
// Separamos en train / test
// Agregamos una columna de numeros aleatorios con distribución uniforme.
var fc_muestras_indices = fc_muestras_indices.randomColumn("RND", 17);
// 30% testing
var testset = fc_muestras_indices.filterMetadata("RND", "less_than", 0.3);

// 70% training
var trainset = fc_muestras_indices.filterMetadata("RND", "not_less_than", 0.3);
print("# Test",testset.size())
print("# Train",trainset.size())
```


## Algoritmos básicos para clasificación supervisada: CART, SVM y Random Forest. 

```Javascript
// Ajuste de los modelos
var parametros = {
  numberOfTrees: 10, 
  variablesPerSplit: 0, 
  minLeafPopulation: 50, 
  seed: 15
};

// Bandas utilizadas para clasificar
var bandas = ['NDVI','GNDVI','NDSI', 'NDBaI'];

// 
var rf_fit = ee.Classifier.randomForest( parametros )
                           .train(trainset, 'clase', bandas);
```

## Evaluación de las clasificaciones: Matriz de confusión, Exactitud, Kappa.

```Javascript

```
