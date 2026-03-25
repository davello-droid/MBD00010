# MBD00010
**Proyecto --- Prediccióm de Importaciones para Cencosud**

Proyecto grupal -- Analítica del Transporte y Logística\
Magíster en Business Analytics and Data Science -- UDP

Este proyecto tiene como objetivo desarrollar un modelo predictivo para
estimar las importaciones de electrodomésticos en Chile, utilizando
datos de comercio exterior, con el fin de apoyar la planificación
logística de una empresa del sector retail (Cencosud).

El trabajo sigue un enfoque reproducible basado en notebooks, datos
abiertos y modelos de series de tiempo y Machine Learning.


---
## 1) Estructura del Proyecto
Proyecto_Logistica_Cencosud/
|-- data/                          # Carpeta de datos
|-- data/raw/                      # Carpeta de datos originales
|-- data/processed/                # Carpeta de datos procesados
|-- notebooks/             	       # Contiene notebook del proyecto
|-- main.py                        # Script principal para ejecutar todo
|-- 01_preparacion_datos.ipynb     # notebook prepara datos
|-- 02_modelos.ipynb               # notebook define modelo
|-- 03_forecast_y_resultados.ipynb # notebook pronostico final
|-- results/                       # Carpeta de resultados
|-- results/figures                # Carpeta de resultados de figuras
|-- results/metrics                # Carpeta de resultados de metricas
|-- report/                        # Carpeta de reportes
|-- requirements.txt               # Dependencias del proyecto
|-- README.md                      # Este archivo

---
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

Productos considerados (códigos HS):
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

## 3) Instalación (Windows / PowerShell)

```powershell
# 1) Crear entorno virtual windows
python -m venv .venv
.\.venv\Scripts\Activate.ps1

# 2) Instalar dependencias
python -m pip install -U pip
python -m pip install -r requirements.txt
```
> Si PowerShell bloquea la activación del venv, ejecutar comando y volver a realizar ese paso:
```powershell
Set-ExecutionPolicy -Scope Process -ExecutionPolicy Bypass
```

## 4) Datasets (carpeta `data/`)
```text
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
```
---
## 5) Flujo de trabajo

1. Exploración de datos  
2. Limpieza y filtrado por código HS  
3. Agregación mensual  
4. Construcción de dataset temporal  
5. Entrenamiento de modelos  
6. Validación cruzada  
7. Predicción a 6 meses  
8. Interpretación para el cliente

## 6) Ejecución

> Ejecutar notebooks en orden.

```powershell
01_preparacion_datos.ipynb
02_modelos.ipynb
03_forecast_y_resultados.ipynb
```
Archivos generados en
data/processed/
---

## 7) Outputs esperados

- Dataset limpio mensual  
- Dataset final para modelado  
- Métricas de modelos  
- Comparación de algoritmos  
- Predicción a 6 meses  
- Gráficos de series de tiempo  
- Resultados para informe 

---
## 8) Metodología

Se utiliza un enfoque de analítica de datos y series de tiempo

- Preparación de datos
- Agregación temporal
- Modelos estadísticos
- Machine Learning
- Validación cruzada
- Forecasting

Modelos evaluados

- ARIMA
- Regresión
- Random Forest
- XGBoost
- LightGBM

El modelo final se selecciona según menor error por validación cruzada.
---

## 9) Cliente del proyecto

Cliente simulado: Cencosud

Necesidad:
Anticipar importaciones futuras para mejorar

- logística
- inventario
- transporte
- costos
- abastecimiento
---
## 10) Autoría
**Grupo 2 – MBD0009**
- Felipe Valdivia
- Daniel Avello
- Roberto Sepúlveda
---
