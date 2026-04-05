# MBD00010
**Proyecto - Predicción de Importaciones para Cencosud**

Proyecto grupal -- Analítica del Transporte y Logística  
Magíster en Business Analytics and Data Science -- UDP

Este proyecto tiene como objetivo desarrollar un modelo predictivo para
estimar las importaciones de electrodomésticos en Chile, utilizando
datos de comercio exterior, con el fin de apoyar la planificación
logística de una empresa del sector retail (Cencosud).

El trabajo sigue un enfoque reproducible basado en notebooks, datos
abiertos y modelos de series de tiempo y Machine Learning.

---

## 1) Estructura del Proyecto

```text
MBD00010/
│
├── data/                         # Carpeta de datos (enlace a Google Drive en ejecución)
│   ├── raw/aduanas/              # Datos originales (NO incluidos en el repo)
│   └── processed/                # Datos procesados generados por el proyecto
│
├── notebooks/
│   ├── 01_preparacion_datos.ipynb
│   └── 02_proyecto_logistica_cencosud_.ipynb
│
├── results/                      # Resultados del modelo
│   └── graphics/                 # Gráficos generados
│
├── requirements.txt              # Dependencias del proyecto
└── README.md                     # Documentación
```
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

El mejor modelo será seleccionado mediante validación cruzada y métricas
de error.

---
## 3) Instalación
### Google Colab (recomendado)

Este proyecto está preparado para ejecutarse en Google Colab, utilizando Google Drive para almacenar los datos.

---
## 4) Datos
### Ubicación exacta de los datos

Los datos originales no se incluyen en este repositorio debido a su tamaño.

Para ejecutar correctamente el proyecto en Google Colab, la carpeta de datos debe estar ubicada exactamente en:

```text
/content/drive/MyDrive/Mod10/proyecto/data
```

### Estructura exacta requerida

```text
/content/drive/MyDrive/Mod10/proyecto/data/
├── raw/
│   └── aduanas/
│       └── Txt_Originales/              # Archivos originales de Aduanas
└── processed/
    ├── importaciones_hs_filtrado_raw.csv
    └── importaciones_hs_filtrado_estandarizado.csv
```

### Fuentes

- Servicio Nacional de Aduanas  
- Datos entregados en el curso  
- Datos abiertos de comercio exterior  
- Variables macroeconómicas (opcional)

### Variables principales

- fecha  
- codigo_arancel  
- valor_cif  
- peso  
- cantidad  

### Filtrado por códigos HS

- 8418  
- 8450  
- 8516  
- 8528  

---
## 5) Ejecución en Google Colab

### Paso 1: Montar Google Drive

```python
from google.colab import drive
drive.mount("/content/drive")
```

### Paso 2: Clonar el repositorio

```python
!git clone https://github.com/davello-droid/MBD00010.git
%cd /content/MBD00010
```

### Paso 3: Enlazar la carpeta de datos desde Google Drive

```python
import os
import shutil

if os.path.islink("/content/MBD00010/data") or os.path.exists("/content/MBD00010/data"):
    try:
        if os.path.islink("/content/MBD00010/data"):
            os.unlink("/content/MBD00010/data")
        else:
            shutil.rmtree("/content/MBD00010/data")
    except Exception:
        pass

os.symlink(
    "/content/drive/MyDrive/Mod10/proyecto/data",
    "/content/MBD00010/data"
)
```

### Paso 4: Instalar dependencias

```python
!pip install -r requirements.txt
```

### Paso 5: Ejecutar notebooks en orden

```text
notebooks/01_preparacion_datos.ipynb
notebooks/02_proyecto_logistica_cencosud_.ipynb
```

---
## 6) Validación rápida de rutas en Colab

Antes de ejecutar los notebooks, se recomienda validar que la estructura esté disponible:

```python
from pathlib import Path

base = Path("/content/drive/MyDrive/Mod10/proyecto/data")

print("Existe data:", base.exists())
print("Existe raw/aduanas:", (base / "raw" / "aduanas").exists())
print("Existe processed:", (base / "processed").exists())
print("Existe archivo raw filtrado:", (base / "processed" / "importaciones_hs_filtrado_raw.csv").exists())
print("Existe archivo estandarizado:", (base / "processed" / "importaciones_hs_filtrado_estandarizado.csv").exists())
```

Si alguna de estas rutas no existe, el proyecto no funcionará correctamente.

---
## 7) Flujo de trabajo

1. Exploración de datos  
2. Limpieza y filtrado por código HS  
3. Agregación mensual  
4. Construcción de dataset temporal  
5. Entrenamiento de modelos  
6. Validación cruzada  
7. Predicción a 6 meses  
8. Interpretación para el cliente  

---
## 8) Outputs esperados

- Dataset limpio mensual  
- Dataset final para modelado  
- Métricas de modelos  
- Comparación de algoritmos  
- Predicción a 6 meses  
- Gráficos de series de tiempo  
- Resultados para informe  

Los resultados se almacenan en:

```text
results/
```

---

## 9) Metodología

Se utiliza un enfoque de analítica de datos y series de tiempo:

- Preparación de datos  
- Agregación temporal  
- Modelos estadísticos  
- Machine Learning  
- Validación cruzada  
- Forecasting  

Modelos evaluados:

- ARIMA  
- Regresión lineal  
- Random Forest  
- XGBoost  
- LightGBM  

El modelo final se selecciona según el menor error por validación cruzada.

---

## 10) Cliente del proyecto

Cliente simulado: **Cencosud**

Necesidad:

Anticipar importaciones futuras para mejorar:

- logística  
- inventario  
- transporte  
- costos  
- abastecimiento  

---

## 11) Autoría

**MBD0010**

- Felipe Valdivia  
- Daniel Avello  
- Roberto Sepúlveda  
