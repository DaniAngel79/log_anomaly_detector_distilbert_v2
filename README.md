# log_anomaly_detector_distilbert_v2: Clasificador de Logs con DistilBERT
## 🛡️ Detección de Anomalías en Logs de Seguridad

**¡ABRIR Y EJECUTAR PROYECTO EN GOOGLE COLAB!**

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/DaniAngel79/log_anomaly_detector_distilbert_v2/blob/main/Log_Anomaly_Training.ipynb)

### Descripción del Proyecto

Este proyecto se centra en la **identificación de patrones anómalos** (potencialmente maliciosos) dentro de grandes volúmenes de logs de sistemas de seguridad.

Implementé un clasificador avanzado utilizando el modelo de lenguaje pre-entrenado **DistilBERT**, el cual ajusté mediante **Fine-Tuning** para una tarea de clasificación binaria de características extraídas de los logs. Mi objetivo principal fue crear una herramienta capaz de asistir a los analistas SOC (Security Operations Center) en la detección temprana de amenazas.

---

## 🚀 Flujo de Trabajo y Ejecución

El proceso completo, que abarca desde la ingesta y preprocesamiento de los datos hasta la fase de entrenamiento e inferencia, se detalla en el cuaderno:

* **Cuaderno principal:** `Log_Anomaly_Training.ipynb`

Para ejecutar el proyecto:

1.  Haga clic en el botón **"Open In Colab"** de arriba.
2.  Una vez en el entorno de Colab, ejecute todas las celdas en orden (Runtime -> Run all).

---

## 📈 Evaluación del Rendimiento

El modelo fue evaluado rigurosamente en un conjunto de prueba, demostrando una alta efectividad.

| Métrica | Valor |
| :--- | :--- |
| **F1-Score Final** | **92.70%** |
| **Precisión (Precision)** | 94.16% |
| **Exhaustividad (Recall)** | 91.29% |

### 🚨 Análisis Crítico de la Matriz de Confusión

La matriz de confusión es crucial para entender las debilidades del modelo en un contexto de ciberseguridad.

| Métrica | Valor | Implicación en Seguridad |
| :--- | :--- | :--- |
| **Falsos Negativos (FN)** | **80** | **Amenazas Reales NO detectadas (Principal preocupación).** Una FN representa una potencial brecha o intrusión que el sistema ignoró. Este es el área clave para el próximo ciclo de mejora. |
| **Falsos Positivos (FP)** | **52** | Alarmas Falsas. Mantuve esta métrica muy baja para evitar la fatiga por alertas en el equipo de seguridad. |

**Recomendación:** Para mejorar la tasa de detección de amenazas (reducir los FN), mi análisis indica que la estrategia más inmediata es realizar un ajuste en el umbral de decisión del clasificador.
