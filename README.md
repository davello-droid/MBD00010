# MBD00010
# Proyecto --- Predicci贸n de Importaciones para Cencosud

Proyecto grupal -- Anal铆tica del Transporte y Log铆stica\
Mag铆ster en Business Analytics and Data Science -- UDP

Este proyecto tiene como objetivo desarrollar un modelo predictivo para
estimar las importaciones de electrodom茅sticos en Chile, utilizando
datos de comercio exterior, con el fin de apoyar la planificaci贸n
log铆stica de una empresa del sector retail (Cencosud).

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
electrodom茅sticos en Chile, con el prop贸sito de apoyar la planificaci贸n
log铆stica y de abastecimiento de una empresa del sector retail
(Cencosud).

Se analizar谩n las siguientes variables:

-   Valor CIF\
-   Peso total\
-   Cantidad importada

Productos considerados (c贸digos HS):

-   8418 鈫?Refrigeradores\
-   8450 鈫?Lavadoras\
-   8516 鈫?Microondas / hornos el茅ctricos\
-   8528 鈫?Televisores

Horizonte de predicci贸n:

-   6 meses

Modelos a comparar:

-   ARIMA\
-   Regresi贸n lineal\
-   Random Forest\
-   XGBoost\
-   LightGBM

El mejor modelo ser谩 seleccionado mediante validaci贸n cruzada y m茅tricas
de error.

## 3) Instalaci贸n

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

Ubicaci贸n de datos

data/raw/

Fuentes

-   Servicio Nacional de Aduanas (importaciones)
-   Datos entregados en el curso
-   Datos abiertos de comercio exterior
-   Variables macroecon贸micas (opcional)

Columnas principales

-   fecha
-   codigo_arancel
-   valor_cif
-   peso
-   cantidad

Filtrado por c贸digos HS

-   8418
-   8450
-   8516
-   8528

Datos procesados

data/processed/

## 5) Flujo de trabajo

1.  Exploraci贸n de datos\
2.  Limpieza y filtrado por c贸digo HS\
3.  Agregaci贸n mensual\
4.  Construcci贸n de dataset temporal\
5.  Entrenamiento de modelos\
6.  Validaci贸n cruzada\
7.  Predicci贸n a 6 meses\
8.  Interpretaci贸n para el cliente

Etapas

-   Comprensi贸n del problema
-   Comprensi贸n de datos
-   Preparaci贸n
-   Modelado
-   Evaluaci贸n
-   Interpretaci贸n

## 6) Ejecuci贸n

Ejecutar notebooks en orden

01_exploracion_datos.ipynb 02_limpieza_y_filtrado.ipynb
03_construccion_dataset.ipynb 04_modelo_arima.ipynb 05_modelos_ml.ipynb
06_validacion_y_comparacion.ipynb 07_forecast_final.ipynb

Archivos generados en

data/processed/ results/

## 7) Outputs esperados

Dataset limpio mensual\
Dataset final para modelado\
M茅tricas de modelos\
Comparaci贸n de algoritmos\
Predicci贸n a 6 meses\
Gr谩ficos de series de tiempo\
Resultados para informe

Ubicaci贸n

results/

Subcarpetas

results/figures/ results/metrics/ results/predictions/

## 8) Metodolog铆a

Se utiliza un enfoque de anal铆tica de datos y series de tiempo

-   Preparaci贸n de datos
-   Agregaci贸n temporal
-   Modelos estad铆sticos
-   Machine Learning
-   Validaci贸n cruzada
-   Forecasting

Modelos evaluados

-   ARIMA
-   Regresi贸n
-   Random Forest
-   XGBoost
-   LightGBM

El modelo final se selecciona seg煤n menor error.

## 9) Cliente del proyecto

Cliente simulado

Cencosud

Necesidad

Anticipar importaciones futuras para mejorar

-   log铆stica
-   inventario
-   transporte
-   costos
-   abastecimiento

## 10) Autores

Proyecto grupal --- Anal铆tica del Transporte y Log铆stica

-   Felipe Valdivia
-   Roberto Sepulveda
-   Daniel Avello
