# Tidymodels Demo – Predicción de Precios de Viviendas

Este repositorio contiene una **demostración completa del flujo de trabajo en `tidymodels`**, desde el análisis exploratorio de datos hasta el preprocesamiento, modelado y optimización de hiperparámetros para un problema de **regresión**.

El objetivo principal es mostrar **buenas prácticas reproducibles** en proyectos de ciencia de datos con R, separando claramente cada etapa del pipeline.

## Estructura del proyecto

```         

tidymodels-demo/
│
├── data/
│   ├── df_train.csv
│   └── df_test.csv
│
├── src/
│   ├── 1_eda_files/
│   ├── 2_preprocessing_rsample_recipes_files/
│   ├── 3_modeling_parsnip_workflows_files/
│   ├── 4_opt_hp_prediction_tune_finetune_yardstick_files/
│   ├── 1_eda.qmd
│   ├── 1_eda.html
│   ├── 2_preprocessing_rsample_recipes.qmd
│   ├── 2_preprocessing_rsample_recipes.html
│   ├── 3_modeling_parsnip_workflows.qmd
│   ├── 3_modeling_parsnip_workflows.html
│   ├── 4_opt_hp_prediction_tune_finetune_yardstick.qmd
│   └── 4_opt_hp_prediction_tune_finetune_yardstick.html
│
├── README.md
├── .gitignore
├── .Rprofile
├── renv.lock
└── tidymodels-demo.Rproj
```

## Dataset

El proyecto utiliza el dataset **House Price Prediction Treated Dataset**, disponible en Kaggle:

<https://www.kaggle.com/datasets/aravinii/house-price-prediction-treated-dataset>

El dataset ya se encuentra preprocesado (sin valores faltantes) y está dividido originalmente en conjuntos de entrenamiento y prueba.

## Notebooks del proyecto

### 1. Análisis exploratorio de datos (`1_eda.qmd`)

Este notebook se enfoca en:

-   Inspección general del dataset
-   Distribución de la variable objetivo (`price`)
-   Comparación entre conjuntos de entrenamiento y prueba
-   Relaciones clave entre precio, tamaño y ubicación
-   Análisis de variables binarias y categóricas

📌 **Objetivo:** generar intuiciones y justificar decisiones de preprocesamiento y modelado posteriores.

### 2. Preprocesamiento con `rsample` y `recipes` (`2_preprocessing_rsample_recipes.qmd`)

En este notebook se construye un pipeline de preprocesamiento **reproducible y libre de fuga de información**, utilizando el ecosistema `tidymodels`.

Incluye:

-   Unificación del dataset original
-   Nueva partición entrenamiento/prueba con `rsample`
-   Definición de una receta (`recipe`) con:
    -   Feature engineering
    -   Transformaciones logarítmicas
    -   Normalización
    -   Codificación de variables categóricas
    -   Asignación de roles
    -   Limpieza de predictores

📌 **Objetivo:** dejar los datos listos para el modelado, garantizando consistencia entre train y test.


### 3. Modelado con `parsnip` y `workflows` (`3_modeling_parsnip_workflows.qmd`)

Este notebook aborda la etapa de modelado mediante:

-   Definición de modelos de regresión con `parsnip`
-   Integración del preprocesamiento y el modelo en `workflow()`
-   Entrenamiento de distintos enfoques de regresión
-   Comparación de modelos bajo un mismo pipeline

📌 **Objetivo:** desacoplar el modelo del preprocesamiento y facilitar la comparación justa entre algoritmos.


### 4. Optimización de hiperparámetros (`4_opt_hp_prediction_tune_finetune_yardstick.qmd`)

Notebook dedicado a:

-   Definición de grids de hiperparámetros
-   Optimización con `tune`
-   Evaluación con métricas de `yardstick`
-   Selección del mejor modelo según desempeño

📌 **Objetivo:** mostrar un flujo completo de tuning y evaluación dentro del marco de `tidymodels`.


## Reproducibilidad

El proyecto utiliza `renv` para la gestión de dependencias.

Para reproducir el entorno:

``` r
renv::restore()
```

Esto instalará automáticamente las versiones de los paquetes utilizadas en el proyecto.

## Autores

-   **Jessica Andrea Aquino Torrez**
-   **Pedro José Cataño Castilla**

Este repositorio se desarrolla en el marco de la **Maestría en Explotación de Datos y Descubrimiento del Conocimiento** de la **Universidad de Buenos Aires (UBA)**, como parte de la materia **Enfoque Estadístico del Aprendizaje**.

## Enfoque del repositorio

Este repositorio está orientado a:

-   Aprendizaje de `tidymodels`
-   Buenas prácticas en proyectos de machine learning
-   Material de apoyo para cursos, talleres o videotutoriales
-   Referencia reutilizable para futuros proyectos de regresión en R
