# MBD00010
# Proyecto --- Prediccióm de Importaciones para Cencosud

Proyecto grupal -- Analítica del Transporte y Logística\
Magíster en Business Analytics and Data Science -- UDP

Este proyecto tiene como objetivo desarrollar un modelo predictivo para
estimar las importaciones de electrodomésticos en Chile, utilizando
datos de comercio exterior, con el fin de apoyar la planificación
logística de una empresa del sector retail (Cencosud).

El trabajo sigue un enfoque reproducible basado en notebooks, datos
abiertos y modelos de series de tiempo y Machine Learning.


## 1) Estructura del Proyecto

Proyecto_Logistica_Cencosud/

data/ raw/ processed/

notebooks/ 01_exploracion_datos.ipynb 02_limpieza_y_filtrado.ipynb
03_construccion_dataset.ipynb 04_modelo_arima.ipynb 05_modelos_ml.ipynb
06_validacion_y_comparacion.ipynb 07_forecast_final.ipynb

results/ figures/ metrics/ predictions/

report/ informe.pdf figuras/

requirements.txt README.md

## 2) Objetivo del Proyecto

El objetivo del proyecto es construir un modelo predictivo que permita
estimar el comportamiento futuro de las importaciones de
electrodomésticos en Chile, con el propósito de apoyar la planificación
logística y de abastecimiento de una empresa del sector retail
(Cencosud).

Se analizarán las siguientes variables:

-   Valor CIF\
-   Peso total\
-   Cantidad importada

Productos considerados (c贸digos HS):

-   8418 Refrigeradores\
-   8450 Lavadoras\
-   8516 Microondas / hornos eléctricos\
-   8528 Televisores

Horizonte de predicción:

-   6 meses

Modelos a comparar:

-   ARIMA\
-   Regresión lineal\
-   Random Forest\
-   XGBoost\
-   LightGBM

El mejor modelo sería seleccionado mediante validación cruzada y métricas
de error.

## 3) Instalación

Crear entorno virtual

python -m venv .venv

Activar entorno

Windows ..venv`\Scripts`{=tex}`\activate`{=tex}

Linux / Mac source .venv/bin/activate

Instalar dependencias

pip install -r requirements.txt

Actualizar pip (opcional)

python -m pip install -U pip

## 4) Datos utilizados

Ubicación de datos

data/raw/

Fuentes

-   Servicio Nacional de Aduanas (importaciones)
-   Datos entregados en el curso
-   Datos abiertos de comercio exterior
-   Variables macroeconómicas (opcional)

Columnas principales

-   fecha
-   codigo_arancel
-   valor_cif
-   peso
-   cantidad

Filtrado por códigos HS

-   8418
-   8450
-   8516
-   8528

Datos procesados

data/processed/

## 5) Flujo de trabajo

1.  Exploración de datos\
2.  Limpieza y filtrado por código HS\
3.  Agregación mensual\
4.  Construcción de dataset temporal\
5.  Entrenamiento de modelos\
6.  Validación cruzada\
7.  Predicción a 6 meses\
8.  Interpretación para el cliente

Etapas

-   Comprensión del problema
-   Comprensión de datos
-   Preparación
-   Modelado
-   Evaluación
-   Interpretación

## 6) Ejecución

Ejecutar notebooks en orden

01_exploracion_datos.ipynb 02_limpieza_y_filtrado.ipynb
03_construccion_dataset.ipynb 04_modelo_arima.ipynb 05_modelos_ml.ipynb
06_validacion_y_comparacion.ipynb 07_forecast_final.ipynb

Archivos generados en

data/processed/ results/

## 7) Outputs esperados

Dataset limpio mensual\
Dataset final para modelado\
Métricas de modelos\
Comparación de algoritmos\
Predicción a 6 meses\
Gráficos de series de tiempo\
Resultados para informe

Ubicación

results/

Subcarpetas

results/figures/ results/metrics/ results/predictions/

## 8) Metodología

Se utiliza un enfoque de analítica de datos y series de tiempo

-   Preparación de datos
-   Agregación temporal
-   Modelos estadísticos
-   Machine Learning
-   Validación cruzada
-   Forecasting

Modelos evaluados

-   ARIMA
-   Regresi贸n
-   Random Forest
-   XGBoost
-   LightGBM

El modelo final se selecciona según menor error.

## 9) Cliente del proyecto

Cliente simulado

Cencosud

Necesidad

Anticipar importaciones futuras para mejorar

-   logística
-   inventario
-   transporte
-   costos
-   abastecimiento

## 10) Autores

Proyecto grupal --- Analítica del Transporte y Logística

-   Felipe Valdivia
-   Roberto Sepulveda
-   Daniel Avello
