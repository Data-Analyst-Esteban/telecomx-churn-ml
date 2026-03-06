# TelecomX — Predicción de Cancelación de Clientes (Churn) — Parte 2

![Python](https://img.shields.io/badge/Python-3.12-blue?logo=python)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-1.x-F7931E?logo=scikit-learn)
![Status](https://img.shields.io/badge/Status-Completado-brightgreen)
![Curso](https://img.shields.io/badge/Alura-LATAM-orange)

## Descripción

Este proyecto es la continuación del análisis exploratorio de churn de TelecomX (Parte 1). En esta etapa se desarrollan modelos de Machine Learning para **predecir qué clientes tienen mayor probabilidad de cancelar sus servicios**, permitiendo a la empresa anticiparse al problema y aplicar estrategias de retención más efectivas.

---

## Objetivos

- Preparar los datos para el modelado (encoding, normalización, balanceo de clases)
- Realizar análisis de correlación y selección de variables
- Entrenar y comparar dos modelos de clasificación
- Evaluar el rendimiento con métricas estándar
- Interpretar la importancia de las variables
- Generar conclusiones y recomendaciones estratégicas

---

## Estructura del Proyecto

```
telecomx-churn-ml/
│
├── TelecomX_ML.ipynb             # Notebook principal con todo el análisis y modelado
├── TelecomX_tratado.csv          # Dataset limpio generado desde la Parte 1
│
├── proporcion_churn.png          # Gráfico: proporción de churn en el dataset
├── correlacion_churn.png         # Gráfico: correlación de variables con churn
├── analisis_dirigido.png         # Gráfico: boxplots de variables clave vs churn
├── matrices_confusion.png        # Gráfico: matrices de confusión de ambos modelos
├── comparacion_modelos.png       # Gráfico: comparación de métricas por modelo
├── importancia_rf.png            # Gráfico: importancia de variables en Random Forest
├── coeficientes_rl.png           # Gráfico: coeficientes de Regresión Logística
│
└── README.md
```

---

## Tecnologías Utilizadas

| Librería | Uso |
|---|---|
| `pandas` | Manipulación y análisis de datos |
| `numpy` | Operaciones numéricas |
| `matplotlib` / `seaborn` | Visualización de datos |
| `scikit-learn` | Modelos de ML, métricas y preprocesamiento |
| `imbalanced-learn` | Balanceo de clases con SMOTE |

---

## Modelos Entrenados

| Modelo | Normalización | Justificación |
|---|---|---|
| Regresión Logística | Sí (StandardScaler) | Modelo lineal sensible a la escala de los datos |
| Random Forest | No | Modelo basado en árboles, no requiere normalización |

---

## Instalación y Uso

**1. Clona el repositorio:**
```bash
git clone https://github.com/Data-Analyst-Esteban/telecomx-churn-ml.git
cd telecomx-churn-ml
```

**2. Instala las dependencias:**
```bash
pip install pandas numpy matplotlib seaborn scikit-learn imbalanced-learn requests
```

**3. Abre el notebook:**
```bash
jupyter notebook TelecomX_ML.ipynb
```
O ábrelo directamente en **VS Code** o **Google Colab**.

---

## Principales Resultados

- El **Random Forest** obtuvo el mejor rendimiento general en todas las métricas.
- El **Recall** es la métrica más relevante en este problema, ya que identificar correctamente a los clientes que cancelarán es prioritario para el negocio.
- Las variables más importantes para la predicción fueron: **Meses de Contrato**, **Cargo Total**, **Cargo Mensual** y **Tipo de Contrato mes a mes**.

---

## Factores Clave que Influyen en la Cancelación

- Clientes con pocos meses de contrato tienen significativamente mayor riesgo de churn
- Los contratos mes a mes están fuertemente asociados a la cancelación
- El servicio de Fibra Óptica presenta mayor tasa de insatisfacción
- El método de pago por cheque electrónico es un indicador de menor compromiso

---

## Recomendaciones Estratégicas

1. **Intervención proactiva en los primeros 12 meses** — periodo crítico de retención
2. **Incentivar contratos anuales** — reducen drásticamente la tasa de churn
3. **Auditoría del servicio de Fibra Óptica** — mejorar calidad y soporte técnico
4. **Migración a pago automático** — reducir el uso de cheque electrónico
5. **Implementar el modelo en producción** — scoring mensual de riesgo por cliente

---

## Repositorio Parte 1

El análisis exploratorio de datos (EDA) que precede a este proyecto se encuentra en:  
[Challenge-telecomx-churn](https://github.com/Data-Analyst-Esteban/Challenge-telecomx-churn)

---

## Autor

**Esteban** — [Data-Analyst-Esteban](https://github.com/Data-Analyst-Esteban)

Proyecto desarrollado como parte del Challenge Data Science Parte 2 — **Alura LATAM**
