# ML_Core8
Objetivo: Realizar el preprocesamiento de datos y la optimización de modelos de machine learning para el conjunto de datos seleccionado. La meta es elegir la técnica de machine learning más adecuada y optimizar sus hiperparámetros para obtener el mejor rendimiento posible.

#  Sleep Disorder Prediction

Este proyecto tiene como objetivo analizar datos relacionados con el sueño y predecir la presencia de trastornos como **insomnio** o **apnea del sueño** mediante técnicas de machine learning.

---

##  Archivos

- `EDA_panda&Kaggle.ipynb`: Análisis exploratorio de datos.
- `ML_core8.ipynb`: Modelado y evaluación de clasificadores.

---

## Dataset

El dataset contiene 374 registros con variables fisiológicas, de estilo de vida y diagnósticos relacionados al sueño.

| Columna                | Descripción |
|------------------------|-------------|
| `gender`               | Género del individuo. |
| `age`                  | Edad. |
| `occupation`           | Ocupación. |
| `sleep_duration`       | Horas promedio de sueño diario. |
| `quality_of_sleep`     | Puntaje subjetivo de calidad de sueño. |
| `physical_activity_level` | Nivel de actividad física. |
| `stress_level`         | Nivel de estrés reportado. |
| `bmi_category`         | Clasificación del IMC (bajo peso, normal, sobrepeso, etc.). |
| `blood_pressure`       | Presión arterial. |
| `heart_rate`           | Frecuencia cardíaca en reposo. |
| `daily_steps`          | Promedio de pasos diarios. |
| `sleep_disorder`       | Etiqueta a predecir (Insomnia, Sleep Apnea, o ausente). |

---

## Preprocesamiento

- Se imputaron los valores nulos de `sleep_disorder` usando la **moda por categoría de `bmi_category`**.
- Variables categóricas fueron codificadas.
- División de datos en `X_train`, `X_test`, `y_train`, `y_test`.

---

## Modelos Aplicados

Se entrenaron y compararon varios modelos de clasificación:

- **Regresión Logística**
- **Árbol de Decisión**
- **K-Nearest Neighbors (KNN)**
- **Random Forest**

> Se utilizó `GridSearchCV` para optimizar hiperparámetros.

---

##  Resultados

### Accuracy de Modelos

| Modelo                  | Accuracy |
|-------------------------|----------|
| Regresión Logística     | 0.92     |
| Árbol de Decisión       | 0.88     |
| KNN (k=2)               | 0.88     |
| Random Forest (50 trees)| **0.893** |

### Matriz de Confusión

Se compararon KNN y Random Forest visualmente. El modelo **Random Forest** mostró mejor balance entre precisión y recall para detectar **Sleep Apnea**.

---

## Métricas Comparativas

| Métrica                  | KNN Classifier | Random Forest Classifier |
|--------------------------|----------------|---------------------------|
| Accuracy                 | 0.88           | **0.893**                 |
| Precisión (Sleep Apnea)  | **0.92**       | 0.87                      |
| Recall (Sleep Apnea)     | 0.58           | **0.68**                  |
| F1-score (Sleep Apnea)   | 0.71           | **0.76**                  |

---

## Conclusión

- **Random Forest** es el modelo final recomendado por su robustez y capacidad para detectar adecuadamente casos clínicos relevantes como **apnea del sueño**.
- La regresión logística tuvo el mayor accuracy general, pero Random Forest demostró un mejor desempeño en la clase minoritaria.

---

## Próximos pasos

- Evaluar el modelo en nuevos datos o con validación cruzada estratificada.
- Integrar el modelo en una app o API para predicción real.
- Explorar técnicas de balanceo de clases (`SMOTE`, `undersampling`).

---

## Autor(a)

Proyecto desarrollado por Marcela Rubio como parte de una práctica de  Machine Learning (b2b-sonda-ds-mayo-2025)

