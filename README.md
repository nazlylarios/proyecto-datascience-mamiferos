# Patrones de la comunidad de mamíferos en una reserva de la Selva Maya

Proyecto final de la materia **Ciencia de Datos** (Maestría en Ciencias Biológicas, UNAM).

**Objetivo:** explorar patrones en las comunidades de mamíferos medianos y grandes registrados con cámaras trampa y evaluar su relación con variables ambientales mediante análisis multivariado y aprendizaje automático.

📄 **Ver el reporte completo:** [index.html](index.html) (o la versión publicada en GitHub Pages).

## Flujo de análisis

1. **Matriz de comunidad**: frecuencias relativas de detección por especie en 24 estaciones de cámara; se filtraron especies raras (debajo del primer cuartil) y se aplicó la transformación de Hellinger.
2. **Variables ambientales**: área basal de árboles frutales (log), cobertura de sotobosque, distancia a carretera y cobertura promedio de bosque maduro (100–1000 m), estandarizadas.
3. **PCA**: los tres primeros componentes explican ~94 % de la variación ambiental (PC1 46 %: bosque maduro y sotobosque; PC2 26 %: árboles frutales; PC3 22 %: distancia a carretera).
4. **Clustering jerárquico** (Ward) sobre la matriz de comunidad → 3 grupos de estaciones.
5. **Aprendizaje supervisado**: Random Forest y SVM para predecir el grupo a partir de las variables ambientales.

## Resultados principales

| Modelo | Exactitud (test) |
|---|---|
| Random Forest | 0.75 |
| SVM (RBF) | 0.50 |

La cobertura de bosque maduro fue la variable más importante en el Random Forest, seguida de la distancia a carretera y la cobertura de sotobosque, lo que sugiere que la cantidad y calidad del hábitat ayudan a explicar los patrones de la comunidad.

## Herramientas

Python · pandas · NumPy · scikit-learn · SciPy · matplotlib · seaborn · Jupyter

## Cómo reproducir

```bash
pip install -r requirements.txt
jupyter notebook proyecto.ipynb
```

> Los datos de registros de cámaras trampa no se incluyen en el repositorio.

## Autora

Nazly Ochoa — Maestría en Ciencias Biológicas, IIES-UNAM, Morelia.
