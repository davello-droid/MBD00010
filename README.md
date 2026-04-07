# MBD00010
**Proyecto - Predicción de Importaciones para Cencosud**

Proyecto grupal -- Analítica del Transporte y Logística  
Magíster en Business Analytics and Data Science -- UDP

## 1. Resumen ejecutivo

El presente proyecto desarrolla una solución analítica orientada a estudiar y proyectar el comportamiento de las importaciones asociadas a categorías de productos electrodomésticos y electrónicos relevantes para una empresa del retail importador como Cencosud. La propuesta se construye a partir de microdatos del Servicio Nacional de Aduanas de Chile y se complementa con variables macroeconómicas del Banco Central de Chile, con el propósito de enriquecer la capacidad explicativa y predictiva del análisis.

Desde una perspectiva de negocio, el proyecto busca aportar una señal útil para la planificación logística, el monitoreo de abastecimiento y la toma de decisiones vinculadas a inventario, capacidad operativa y seguimiento de categorías sensibles. Para ello, se implementa un flujo de trabajo que considera la preparación de datos, la construcción de series temporales mensuales, la integración de variables externas, el análisis exploratorio, la comparación de modelos predictivos y la generación de pronósticos.

El enfoque metodológico combina rigurosidad técnica y aplicabilidad práctica. Se evalúan distintos modelos sobre variables objetivo como valor CIF, peso y cantidad importada, utilizando métricas de error y ajuste para determinar el mejor desempeño por variable. En este contexto, el proyecto no pretende ofrecer una predicción exacta del comportamiento futuro de las compras de la empresa, sino una aproximación analítica defendible y útil como apoyo a la gestión.

## 2. Contexto y justificación

En empresas del retail con dependencia relevante de importaciones, la anticipación de flujos de ingreso de productos representa un insumo estratégico para la gestión logística. Contar con una proyección razonable del comportamiento futuro de las importaciones permite fortalecer decisiones relacionadas con abastecimiento, uso de capacidad, control de inventarios y priorización operativa.

Cencosud constituye un caso de uso realista y defendible para este tipo de análisis, dada su exposición al comercio exterior en múltiples líneas de productos. En ese contexto, este proyecto propone transformar datos públicos y heterogéneos en una herramienta analítica con valor aplicado, orientada a responder una necesidad concreta de negocio mediante técnicas de ciencia de datos y modelamiento predictivo.

## 3. Problema de negocio

¿Cómo evolucionarán en los próximos meses las importaciones asociadas a determinadas categorías de productos electrodomésticos y electrónicos relevantes para una empresa del retail como Cencosud, y qué enfoque de modelamiento ofrece una mejor capacidad predictiva para apoyar decisiones logísticas?

## 4. Objetivo general

Desarrollar un pipeline analítico y predictivo que permita estimar la evolución mensual de importaciones de categorías HS4 seleccionadas, integrando microdatos del Servicio Nacional de Aduanas con variables externas del Banco Central de Chile.

## 5. Objetivos específicos

1. Preparar y estandarizar los datos de importaciones relevantes para el análisis.
2. Identificar y filtrar categorías HS4 de interés para productos electrodomésticos y electrónicos.
3. Construir series temporales mensuales consolidadas y segmentadas por categoría.
4. Incorporar variables macroeconómicas externas para enriquecer el análisis.
5. Desarrollar un análisis exploratorio que permita comprender patrones, variabilidad y posibles anomalías.
6. Comparar distintos modelos predictivos sobre las variables objetivo.
7. Generar pronósticos y visualizaciones útiles para la interpretación ejecutiva de resultados.

## 6. Alcance del proyecto

El proyecto se enfoca en el análisis de importaciones observadas en datos públicos, agregadas a frecuencia mensual, y en su modelamiento predictivo sobre variables seleccionadas. No busca reconstruir órdenes de compra internas ni representar de forma directa la demanda comercial o los procesos internos de abastecimiento de la empresa. En consecuencia, los resultados deben interpretarse como una señal analítica de apoyo a la toma de decisiones, y no como una proyección exacta de compras futuras.

---

## 7) Estructura académica sugerida del proyecto

```text
MBD00010/
│
├── data/
│   ├── aduanas/
│   │   └── aduanas_procesadas.zip       # Datos procesados de Aduanas incluidos en el repo
│   └── bcch/                            # Datos de variables exógenas del Banco Central de Chile
│       ├── bcch_dolar_observado.csv
│       ├── bcch_ipc_mensual.csv
│       └── bcch_precio_cobre.csv
│
│
├── notebooks/
│   ├── 01_preparacion_datos.ipynb
│   └── 02_proyecto_logistica_cencosud_.ipynb
│
├── results/                      # Resultados del modelo
│    ├── graphics/                # Gráficos generados
│    └── tables/                  # Tablas de resultados
├── requirements.txt              # Dependencias del proyecto
└── README.md                     # Documentación
```
---
## 8) Objetivo del Proyecto
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
-   LightGBM\
-   SARIMAX\
-   Exponential Smoothing\

La selección final del mejor modelo por variable se realiza automáticamente a partir de las métricas obtenidas en la ejecución del notebook.

## 9. Resultados esperados

Se espera que el proyecto permita:

- construir una base analítica limpia y trazable;
- identificar patrones relevantes en la evolución mensual de las importaciones;
- comparar el desempeño de distintos enfoques de modelamiento;
- generar un forecast orientativo para variables críticas;
- producir visualizaciones y tablas útiles para interpretación ejecutiva.

En términos metodológicos, se espera además evidenciar que el desempeño predictivo puede variar entre variables y que la incorporación de variables exógenas puede aportar valor en ciertos casos, aunque no necesariamente de forma homogénea.

---
## 10) Instalación
### Google Colab

Este proyecto está preparado para ejecutarse en Google Colab.

---
## 11) Datos
### Datos de Aduanas

Los datos originales no se incluyen en este repositorio debido a su tamaño.

El flujo de preparación es el siguiente:

1. Los archivos originales de Aduanas fueron almacenados externamente.
2. El notebook `01_preparacion_datos.ipynb` descarga esos archivos mediante `gdown`.
3. Los datos se procesan mediante lectura por bloques (chunking).
4. Se generan dos archivos:
   - `importaciones_hs_filtrado_raw.csv`
   - `importaciones_hs_filtrado_estandarizado.csv`
5. Ambos archivos se comprimen en:
   - `aduanas_procesadas.zip`

Para ejecutar el proyecto en el repositorio, el archivo debe estar ubicado en:

```text
/content/MBD00010/data/aduanas/aduanas_procesadas.zip
```

### Variables exógenas (BCCH)

El proyecto incorpora variables macroeconómicas del Banco Central de Chile como variables exógenas del modelo.

Estas variables se encuentran en:

```text
/content/MBD00010/data/bcch/
```

Archivos considerados:
- `bcch_dolar_observado.csv`
- `bcch_ipc_mensual.csv`
- `bcch_precio_cobre.csv`

Estos archivos sí forman parte del repositorio y son cargados directamente por el notebook de modelamiento.

### Estructura exacta requerida

```text
/content/MBD00010/data/
├── aduanas/
│   └── aduanas_procesadas.zip
└── bcch/
    ├── bcch_dolar_observado.csv
    ├── bcch_ipc_mensual.csv
    └── bcch_precio_cobre.csv
```

### Fuentes

- Servicio Nacional de Aduanas
- Datos entregados en el curso
- Datos abiertos de comercio exterior
- Banco Central de Chile

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
## 12) Ejecución en Google Colab

### Paso 1: Abrir el notebook principal

```text
notebooks/02_proyecto_logistica_cencosud.ipynb
```

### Paso 2: Ejecutar todas las celdas

El notebook principal:
- clona el repositorio desde GitHub;
- instala dependencias;
- descomprime `aduanas_procesadas.zip`;
- carga los archivos de Aduanas y BCCH;
- ejecuta el pipeline de análisis y modelamiento.

### Paso 3: Ejecución opcional del notebook de preparación

```text
notebooks/01_preparacion_datos.ipynb
```

Este notebook permite reconstruir el dataset procesado de Aduanas a partir de los archivos originales.

---
## 13) Validación rápida de rutas en Colab

Antes de ejecutar el notebook de modelamiento, se recomienda validar que la estructura esté disponible:

```python
from pathlib import Path

base = Path("/content/MBD00010/data")

print("Existe data:", base.exists())
print("Existe data/aduanas:", (base / "aduanas").exists())
print("Existe aduanas_procesadas.zip:", (base / "aduanas" / "aduanas_procesadas.zip").exists())
print("Existe data/bcch:", (base / "bcch").exists())
print("Existe bcch_dolar_observado.csv:", (base / "bcch" / "bcch_dolar_observado.csv").exists())
print("Existe bcch_ipc_mensual.csv:", (base / "bcch" / "bcch_ipc_mensual.csv").exists())
print("Existe bcch_precio_cobre.csv:", (base / "bcch" / "bcch_precio_cobre.csv").exists())
```

Si alguna de estas rutas no existe, el proyecto no funcionará correctamente.

---
## 14) Flujo de trabajo

1. Exploración de datos
2. Limpieza y filtrado por código HS
3. Agregación mensual
4. Construcción de dataset temporal
5. Integración de variables exógenas BCCH
6. Entrenamiento de modelos
7. Validación cruzada
8. Predicción a 6 meses
9. Interpretación para el cliente

---
## 15) Outputs esperados

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

## 16) Metodología

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
- SARIMAX
- Exponential Smoothing

El modelo final se selecciona según el menor error por validación cruzada.

---

## 17) Cliente del proyecto

Cliente simulado: **Cencosud**

Necesidad:

Anticipar importaciones futuras para mejorar:

- logística
- inventario
- transporte
- costos
- abastecimiento

---

## 18) Autoría

**MBD0010**

- Felipe Valdivia
- Daniel Avello
- Roberto Sepúlveda
