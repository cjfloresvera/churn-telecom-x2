# 🚀 Desafío Telecom X: Predicción de Cancelación de Clientes (Churn)

## 🎯 Objetivo del Proyecto

El objetivo principal de este proyecto es construir un modelo predictivo capaz de identificar a los clientes con mayor probabilidad de cancelar sus servicios (churn). A través del análisis de datos, se busca entender los factores que impulsan esta decisión para poder proponer estrategias de retención efectivas y personalizadas.

## 💾 Descripción de los Datos

El conjunto de datos utilizado corresponde a información de clientes de una compañía de telecomunicaciones e incluye las siguientes variables:

* **Identificadores**: `customerID`
* **Información del Cliente**: `gender`, `SeniorCitizen`, `Partner`, `Dependents`
* **Servicios Contratados**: `PhoneService`, `MultipleLines`, `InternetService`, `OnlineSecurity`, `OnlineBackup`, `DeviceProtection`, `TechSupport`, `StreamingTV`, `StreamingMovies`
* **Información de la Cuenta**: `tenure` (antigüedad en meses), `Contract`, `PaperlessBilling`, `PaymentMethod`, `MonthlyCharges`, `TotalCharges`
* **Variable Objetivo**: `Churn` (indica si el cliente canceló el servicio)

## ⚙️ Metodología

El proyecto se desarrolló en varias etapas, siguiendo un pipeline de Machine Learning estándar:

1.  **Limpieza y Preprocesamiento de Datos**:
    * Eliminación de columnas irrelevantes (`customerID`, `Cuentas_Diarias`).
    * Codificación de variables categóricas a formato numérico (One-Hot Encoding).
    * Análisis y manejo del desbalance de clases utilizando la técnica **SMOTE**.
    * Estandarización de variables numéricas con `StandardScaler`.

2.  **Análisis Exploratorio y de Correlación**:
    * Se calculó la proporción de clientes que cancelaron para confirmar el desbalance de clases.
    * Se visualizó la matriz de correlación para identificar las relaciones entre las variables y la variable objetivo `Churn`. Las variables `tenure` y `MonthlyCharges` mostraron ser las más relevantes.

3.  **Modelado y Evaluación**:
    * El conjunto de datos se dividió en conjuntos de entrenamiento y prueba (80/20).
    * Se entrenaron dos modelos de clasificación:
        * **Regresión Logística**: Un modelo lineal que requiere datos estandarizados.
        * **Random Forest**: Un modelo de ensemble basado en árboles, no sensible a la escala de los datos.
    * El rendimiento de los modelos se evaluó utilizando métricas clave como **Exactitud**, **Precisión**, **Recall** y **F1-Score**, además de la **Matriz de Confusión**.

## 🚀 Hallazgos Clave

* **Modelo de Mejor Desempeño**: El modelo **Random Forest** superó a la Regresión Logística en todas las métricas, demostrando ser más robusto y eficaz para la predicción de `churn`.

* **Factores de Mayor Influencia**:
    * **Antigüedad (`tenure`)**: Es el factor más protector contra la cancelación. Los clientes con más tiempo en la empresa son menos propensos a irse.
    * **Tipo de Contrato (`Contract_Month-to-month`)**: Es el mayor predictor de riesgo. La falta de compromiso a largo plazo facilita la cancelación.
    * **Cargos Mensuales (`MonthlyCharges`)**: Los clientes con cargos mensuales más altos son más propensos a cancelar, lo que sugiere una sensibilidad al precio.
    * **Servicio de Internet (`InternetService_Fiber optic`)**: Los clientes con fibra óptica tienen una mayor probabilidad de cancelar, lo que podría estar relacionado con problemas de calidad del servicio.

## 🎯 Estrategias de Retención Propuestas

Basándose en los resultados del análisis, se recomiendan las siguientes estrategias para reducir la tasa de cancelación:

* **Programas de Fidelización**: Implementar ofertas y beneficios para incentivar a los clientes con contratos mensuales a migrar a planes de mayor duración.
* **Monitoreo de Nuevos Clientes**: Realizar un seguimiento proactivo durante los primeros meses para asegurar la satisfacción y resolver cualquier problema rápidamente, ya que este es el período de mayor riesgo.
* **Revisión de Precios**: Analizar los planes de precios y considerar la posibilidad de ofrecer descuentos o paquetes especiales a clientes con cargos mensuales elevados.
* **Mejora de la Calidad del Servicio**: Investigar y abordar las posibles causas de insatisfacción entre los usuarios de fibra óptica.

---
