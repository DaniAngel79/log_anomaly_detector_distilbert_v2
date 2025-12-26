# log_anomaly_detector_distilbert_v2
"Detección de anomalías en logs de seguridad utilizando DistilBERT y clasificación de características."
# 🛡️ Detección de Anomalías en Logs de Seguridad (DistilBERT)

Este proyecto implementa un clasificador avanzado de logs para identificar patrones anómalos (posible actividad maliciosa) en logs de sistemas de seguridad. Utiliza un modelo de lenguaje pre-entrenado **DistilBERT** ajustado para la clasificación binaria de características de log.

## 🚀 Cómo Usar el Proyecto

El flujo de trabajo completo (desde la preparación de datos hasta la inferencia final) se encuentra en el cuaderno: **Log_Anomaly_Training.ipynb**.

1. Abre el cuaderno en Google Colab (haciendo clic en el archivo).
2. Ejecuta todas las celdas en orden.

## 📊 Resultados de Rendimiento del Modelo

El modelo logró una alta efectividad en el conjunto de prueba (evaluación final):

* **F1-Score Final:** 92.70%
* **Precisión (Precision):** 94.16%
* **Exhaustividad (Recall):** 91.29%

## 🚨 Análisis de Errores (Matriz de Confusión)



La matriz de confusión revela la distribución de errores del modelo:

| Métrica | Valor | Interpretación |
| :--- | :--- | :--- |
| **Falsos Negativos (FN)** | **80** | **Amenazas Perdidas (principal área de mejora).** |
| **Falsos Positivos (FP)** | **52** | Alarmas Falsas (frecuencia muy baja). |

El modelo es muy preciso, pero se recomienda aplicar estrategias como el ajuste del umbral de decisión para reducir los 80 Falsos Negativos en un entorno de seguridad.
