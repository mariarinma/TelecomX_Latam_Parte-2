# TelecomX_Latam_Parte-2

# Telecom X — Predicción de Cancelación de Clientes (Churn)

## Descripción del Proyecto

Este proyecto tiene como objetivo analizar y predecir la cancelación de clientes (churn) en Telecom X utilizando técnicas de análisis de datos y modelos de Machine Learning.

La cancelación de clientes representa un problema crítico para las empresas de telecomunicaciones, ya que adquirir nuevos clientes suele ser más costoso que retener los existentes. Por ello, identificar de forma anticipada a los clientes con mayor probabilidad de cancelar permite implementar estrategias de retención más efectivas.

En este proyecto se realiza:

- Limpieza y preparación de datos
- Análisis exploratorio de datos (EDA)
- Análisis de correlaciones y variables relevantes
- Entrenamiento de modelos de Machine Learning
- Evaluación de modelos predictivos
- Interpretación de factores que influyen en la cancelación

El resultado final es un modelo capaz de identificar clientes con mayor riesgo de cancelar el servicio y generar insights estratégicos para el negocio.

---

# Dataset

El dataset contiene información de clientes de Telecom X, incluyendo:

- Información demográfica
- Tipo de contrato
- Servicios contratados
- Métodos de pago
- Cargos mensuales y totales
- Indicador de cancelación (Churn)

Después del preprocesamiento el dataset final contiene:

- **7043 registros**
- **27 variables**

La variable objetivo del modelo es:

**Churn**
- 0 → Cliente permanece activo  
- 1 → Cliente cancela el servicio

Distribución del dataset:

- Clientes activos: **73.46%**
- Clientes que cancelan: **26.54%**

---

# Estructura del Proyecto
- TelecomX_latam_parte2.ipynb
- README.md
- TelecomX_clean.csv

El archivo principal es el notebook donde se desarrolla todo el análisis y el modelado.

---

# Proceso del Proyecto

## 1. Preparación de Datos

Se realizaron los siguientes pasos:

- Eliminación de columnas irrelevantes (customerID)
- Conversión de variables categóricas mediante **One-Hot Encoding**
- Conversión de variables booleanas a formato numérico
- Creación de nuevas variables:
  - **Cuentas_Diarias**
  - **Cantidad_Servicios**
- Análisis de balance de clases

---

## 2. Análisis Exploratorio de Datos (EDA)

Se analizaron patrones de cancelación utilizando:

- Matriz de correlación
- Boxplots
- Scatter plots
- Distribución de churn

Principales hallazgos:

- Los clientes con **menor antigüedad** tienen mayor probabilidad de cancelar.
- Los **cargos mensuales elevados** están asociados con mayor churn.
- Los clientes con **contratos de mayor duración** presentan menor cancelación.
- El método de pago **Electronic Check** muestra mayor riesgo de churn.

---

# Modelos de Machine Learning

Se entrenaron dos modelos de clasificación:

### Regresión Logística
Modelo lineal sensible a la escala de los datos, por lo que se aplicó normalización con StandardScaler.

Resultados:

Accuracy: **0.79**

Precision (Churn): **0.63**

Recall (Churn): **0.52**

F1-score: **0.57**

---

### Random Forest
Modelo basado en árboles que no requiere normalización.

Resultados:

Accuracy: **0.78**

Precision (Churn): **0.61**

Recall (Churn): **0.48**

F1-score: **0.54**

---

# Variables Más Importantes

Según el modelo Random Forest, las variables con mayor impacto en la predicción de cancelación son:

- account.Charges.Total
- customer.tenure
- account.Charges.Monthly
- Cuentas_Diarias
- internet.InternetService_Fiber optic
- account.PaymentMethod_Electronic check
- account.Contract_Two year
- Cantidad_Servicios

Estas variables indican que la cancelación está fuertemente relacionada con:

- Antigüedad del cliente
- Costos del servicio
- Tipo de contrato
- Método de pago
- Servicios contratados

---

# Estrategias de Retención Propuestas

Basándose en los resultados del análisis y del modelo predictivo, se proponen las siguientes estrategias:

### Retención temprana
Los clientes con menor antigüedad presentan mayor riesgo de cancelación. Programas de onboarding y seguimiento en los primeros meses pueden reducir churn.

### Optimización de precios
Clientes con cargos mensuales altos presentan mayor probabilidad de cancelar. Ajustar paquetes o beneficios podría mejorar la retención.

### Promoción de contratos de largo plazo
Los contratos de uno o dos años reducen significativamente la cancelación.

### Incentivos para pagos automáticos
Clientes que usan Electronic Check muestran mayor churn. Promover pagos automáticos podría mejorar la fidelización.

### Bundles de servicios
Clientes que utilizan más servicios tienen menor probabilidad de cancelar.

---

# Conclusión

El análisis demuestra que la cancelación de clientes está influenciada principalmente por factores relacionados con:

- Antigüedad del cliente
- Costos del servicio
- Tipo de contrato
- Método de pago
- Nivel de uso de servicios

El modelo de **Regresión Logística mostró el mejor desempeño para detectar clientes con riesgo de churn**, aunque ambos modelos ofrecen resultados útiles para construir sistemas de predicción de cancelación.

Este tipo de análisis permite a Telecom X anticipar la cancelación de clientes y aplicar estrategias de retención basadas en datos.

---

# Tecnologías Utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-Learn

---

# Autor

Proyecto desarrollado por Maria Jose Rincon Manrique como parte del desafío de **Data Science LATAM — Telecom X2**.
