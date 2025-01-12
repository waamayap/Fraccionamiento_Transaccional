# Fraccionamiento_Transaccional

## Resumen del Proyecto

Este proyecto tiene como objetivo identificar patrones de fraude mediante la detección de fraccionamiento transaccional. El fraccionamiento transaccional consiste en dividir una transacción en varias de menor monto, realizadas en un mismo período de tiempo, generalmente 24 horas, y relacionadas con el mismo cliente o cuenta. El análisis se enfoca en identificar estas irregularidades y optimizar la detección utilizando un modelo de Machine Learning basado en XGBoost.

Contenido

1. Análisis Exploratorio de Datos (EDA):

Distribución de transacciones con fraude por:

Merchant_ID: Identifica la actividad general y el porcentaje de fraudes por cada comerciante.
Transaction_Type: Compara el porcentaje de fraude entre transacciones de débito y crédito.
Días de la semana y horas del día: Muestra patrones temporales asociados al fraude.
Montos transaccionales (Transaction_Amount): Analiza cómo los montos impactan la probabilidad de fraude.

2. Modelo Analítico:

Modelo Seleccionado: XGBoost por su excelente balance entre métricas como ROC AUC (0.97) y F1 Score (0.83).
Validación Cruzada: Utilizando KFold, el modelo mostró un AUC-ROC promedio de 0.97 con una desviación estándar de 0.0011.

3. Análisis Interpretativo:

Uso de SHAP para interpretar las variables más influyentes en el modelo:
Transaction_Amount: Los valores más altos disminuyen la probabilidad de fraude.
Secuencia_Transacciones: Una mayor frecuencia de transacciones incrementa el riesgo de fraude.

4. Recomendaciones:

Frecuencia de Actualización:
Diaria: Captura de datos en tiempo real para identificar patrones recientes.
Semanal: Reentrenamiento del modelo para adaptarse a nuevos patrones.
Mensual: Ajustes de hiperparámetros para garantizar el máximo rendimiento.

5.  Propuesta de Despliegue:

Arquitectura basada en AWS, utilizando:
Amazon SageMaker para entrenar y desplegar el modelo.
AWS Lambda como intermediario entre el modelo y las solicitudes de usuarios.
Amazon API Gateway para exponer un endpoint REST que permita interactuar con el modelo.

6.  Requisitos del Proyecto
   
Software y Librerías:
Python (Scikit-learn, SHAP, XGBoost, Pandas)
AWS (SageMaker, Lambda, API Gateway)
Datos: Incluyen información transaccional diaria con atributos como Transaction_Amount, Transaction_Type, Merchant_ID y variables temporales.

Conclusión
El proyecto ofrece un enfoque robusto para la detección de fraudes transaccionales utilizando técnicas avanzadas de Machine Learning e interpretabilidad con SHAP. La arquitectura de despliegue propuesta garantiza escalabilidad y accesibilidad para análisis en tiempo real.
