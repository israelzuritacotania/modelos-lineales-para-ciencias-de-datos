# MODELOS-LINEALES-PARA-CIENCIAS-DE-DATOS
Modulo 10 de la Maestría en Inteligencia Artificial, Machine Learnign y Ciencia de Datos UPEA


# Price Estimation – Caso Automóviles TAREA 2

Este proyecto automatiza la estimación de precios de automóviles usando machine learning, reemplazando la valuación manual de expertos. El objetivo es reducir costos y mejorar la precisión de las valuaciones.

## Objetivos
1. Entrenar al menos dos tipos de algoritmos diferentes (Random Forest y Ridge Regression), cada uno con tres variaciones de parámetros.
2. Seleccionar el mejor modelo usando una métrica interpretable para negocio (MAE).
3. Registrar el mejor modelo en MLflow y habilitar un endpoint en Databricks para inferencias.
4. Analizar el error por brackets de precio real, explicando riesgos/beneficios de sobre/subestimación.

---

## Flujo de trabajo

### 1. Preparación de datos
- Se utiliza el dataset de automóviles de UCI.
- Se eliminan valores nulos y se seleccionan variables numéricas relevantes.
- Variables predictoras: `highway-mpg`, `city-mpg`, `horsepower`, `engine-size`.
- Variable objetivo: `price`.

### 2. Entrenamiento de modelos
- **Random Forest Regression:** Se entrenan tres modelos variando `n_estimators`, `max_depth` y `max_features`.
- **Ridge Regression:** Se entrenan tres modelos variando el parámetro `alpha`.
- Cada modelo se evalúa usando MAE (Mean Absolute Error).

### 3. Comparación y selección del mejor modelo
- Se construye una tabla de resultados con parámetros y métricas.
- El modelo con menor MAE en el conjunto de test es seleccionado como el mejor.

### 4. Registro y visualización de resultados
- El mejor modelo y sus artefactos (datasets, métricas, gráficas) se registran en MLflow.
- Se generan y guardan gráficas de calidad de predicción, residuos e importancia de variables.
- Las gráficas se muestran automáticamente en el notebook.

### 5. Análisis de error por brackets de precio
- Se grafica el MAE por intervalos de precio real para identificar riesgos de sobre/infraestimación.

### 6. Puntos extra
- Se incluyen análisis adicionales como importancia de variables y gráfico de parallel coordinates para comparar experimentos.

---

## Resultados
- **Mejor modelo:** Random Forest con parámetros óptimos (ver tabla de resultados en el notebook).
- **Métrica principal:** MAE, por su interpretabilidad en unidades monetarias.
- **Variables más importantes:** Identificadas mediante el gráfico de importancia de variables.
- **Registro en MLflow:** Todos los experimentos y artefactos quedan versionados y disponibles para despliegue.
- **Visualizaciones:** Gráficas de calidad de predicción, residuos y análisis de error por brackets permiten una interpretación clara del desempeño y riesgos del modelo.

---

## Ejecución
1. Instala las dependencias con `%pip install ucimlrepo xgboost mlflow scikit-learn pandas matplotlib seaborn`.
2. Ejecuta las celdas en orden para preparar los datos, entrenar los modelos, comparar resultados y registrar el mejor modelo.
3. Revisa las gráficas generadas automáticamente para interpretar los resultados.
4. Consulta MLflow para acceder a los modelos registrados y sus métricas.

---

## Interpretación
- El modelo seleccionado minimiza el error absoluto medio en la predicción de precios.
- El análisis por brackets de precio permite identificar segmentos donde el modelo es más preciso y donde existen riesgos de sobre/infraestimación.
- Las visualizaciones y el registro en MLflow aseguran trazabilidad y reproducibilidad del flujo.

---
