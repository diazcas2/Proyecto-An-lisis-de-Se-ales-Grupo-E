# Análisis y clasificación de voz

## Descripción del proyecto

Este proyecto aborda el **análisis, preprocesado y clasificación de señales de voz** mediante técnicas de procesamiento digital de señales y aprendizaje automático. A partir de audios en bruto, se realiza una limpieza de ruido y silencios, se extraen las características acústicas relevantes y se construyen modelos de clasificación para el análisis de la voz.

El trabajo está desarrollado en **R**, apoyándose en librerías especializadas para el tratamiento de audio y el modelado estadístico.

ENLACE A LOS DATOS: `https://bil.eecs.yorku.ca/datasets/` donde la carpeta usada es `for-norm.tar.gz`.

## Objetivos

* Preprocesar señales de voz para mejorar su calidad analítica.
* Detectar y eliminar ruido y silencios en los audios.
* Extraer características acústicas relevantes (temporales y espectrales).
* Construir y evaluar modelos de clasificación basados en dichas características.
* Analizar el rendimiento de los modelos mediante métricas estándar.

## Estructura del proyecto

```
├── Informe.Rmd            # Informe principal del proyecto (análisis completo)
├── Audios_finales_orig    # Audios originales
├── Audios_finales_conv    # Audios tras la conversión a wav
├── Audios_finales_limp    # Audios tras la limpieza de ruido
└── README.md              # Este archivo
```

## Preprocesado de audio

El preprocesado incluye las siguientes etapas:

1. **Lectura y conversión de audios**

   * Carga de archivos de audio desde directorios definidos.
   * Conversión a un formato y frecuencia de muestreo homogéneos.

2. **Detección de ruido y silencios**

   * Cálculo de métricas temporales como:

     * *Zero Crossing Rate (ZCR)*
     * *Short Time Energy (STE)*
   * Identificación de segmentos no informativos.

3. **Eliminación de ruido y silencios**

   * Filtrado de segmentos irrelevantes.
   * Generación de audios limpios para el análisis posterior.

## Extracción de características

A partir de los audios preprocesados se extraen características acústicas, entre ellas:

* **Period pitch**
* **Coeficientes cepstrales en escala Mel (MFCC)**
* **Centroide espectral**
* Otras medidas espectrales y temporales relevantes

Estas características se utilizan como variables de entrada para los modelos de clasificación.

## Modelado y clasificación

El proyecto emplea técnicas de aprendizaje automático para la clasificación de la voz, haciendo uso de librerías como:

* `caret`
* `randomForest`
* `pROC`
* `dplyr`

Se entrenan y evalúan distintos modelos, analizando su desempeño mediante métricas como:

* Exactitud
* Curvas ROC
* AUC

## Requisitos

Para ejecutar el proyecto se requiere:

* Paquetes de R:

  * `seewave`
  * `tuneR`
  * `caret`
  * `pROC`
  * `dplyr`
  * `randomForest`

Los paquetes pueden instalarse ejecutando:

```r
install.packages(c("seewave", "tuneR", "caret", "pROC", "dplyr", "randomForest"))
```

## Ejecución

1. Colocar los audios originales en la carpeta correspondiente.
2. Ejecutar el archivo `Informe.Rmd` para reproducir todo el flujo de análisis:

   * Preprocesado
   * Extracción de características
   * Entrenamiento y evaluación de modelos
   
3. Revisar los resultados y visualizaciones generadas.

## Resultados

El informe final incluye:

* Visualizaciones de señales y espectros.
* Comparación de características acústicas.
* Evaluación cuantitativa de los modelos de clasificación.

## Autoría

Proyecto desarrollado por **Azahara Martínez, María de los Ángeles Díaz,Álvaro Nieva, Iyán Álvarez, Florencia Pellegrini y Óscar Camacho.** 

## Referencias

Las referencias bibliográficas y técnicas se encuentran detalladas en la sección final del informe (`Informe.Rmd`).
