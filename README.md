# Prueba Técnica — Predicción de Churn

## Descripción General

Este repositorio contiene la solución desarrollada para una prueba técnica enfocada en análisis de churn utilizando datos de comportamiento de usuarios calculados sobre ventanas móviles (rolling windows) de 30 días.

El objetivo del ejercicio fue evaluar capacidades relacionadas con:

- Exploratory Data Analysis (EDA)
- Detección y tratamiento de outliers
- Modelado de Machine Learning
- LLM + Prompt Engineering
- Diseño conceptual de un sistema Agente / RAG

El dataset contiene métricas de comportamiento de usuarios como actividad, compras y gasto en los últimos 30 días, junto con una variable objetivo de churn.


# Estructura del repositorio
|---|
├── Dataset_Pruebas.csv
├── Parte 1 _ EDA.ipynb
├── Parte 2_Modelo.ipynb
├── Parte 3_ LLM + Prompting.ipynb
├── Parte 4_ Diseño de Agente_ RAG.ipynb
└── README.md

# Descripción del Dataset

El dataset contiene aproximadamente 2.020 registros de usuarios con las siguientes variables:

| Variable | Descripción |
|---|---|
| user_id | Identificador único del usuario |
| age | Edad del usuario |
| country | País del usuario |
| events_last_30d | Número de eventos en los últimos 30 días |
| purchases_last_30d | Número de compras en los últimos 30 días |
| total_spend_last_30d | Gasto total en los últimos 30 días |
| churned | Variable objetivo (1 = churn, 0 = activo) |

Las variables fueron calculadas utilizando ventanas móviles de 30 días actualizadas diariamente.

# Parte 1 — Exploratory Data Analysis (EDA)

Notebook:
- `Parte 1 _ EDA.ipynb`

Principales actividades:
- Exploración del dataset
- Análisis de distribuciones
- Análisis de correlaciones
- Detección de duplicados
- Identificación e interpretación de outliers
- Implicaciones del rolling window
- Riesgos de calidad de datos

Se identificaron tres categorías principales de outliers:

1. Outliers de dominio (edades inválidas)
2. Outliers estadísticos extremos (posibles bots o errores de logging)
3. Valores económicos negativos (posibles devoluciones o chargebacks)

# Parte 2 — Modelo de Machine Learning

Notebook:
- `Parte 2_Modelo.ipynb`

Modelos implementados:
- Logistic Regression
- Random Forest

Métricas evaluadas:
- F1 Score
- ROC AUC
- Classification Report

Análisis adicional:
- Importancia de variables
- Limitaciones del modelo
- Riesgos de data leakage
- Propuesta de mejora en producción

Conclusión principal:
Las variables disponibles mostraron capacidad predictiva limitada para churn, con métricas cercanas a un clasificador aleatorio (ROC AUC ≈ 0.5), lo que sugiere la necesidad de incorporar variables históricas y de comportamiento más robustas.

# Parte 3 — LLM + Prompt Engineering

Notebook:
- `Parte 3_ LLM + Prompting.ipynb`

Esta sección evalúa el uso de Large Language Models (LLMs) para generar resúmenes automáticos a partir de resultados analíticos y de Machine Learning.

Incluye:
- Diseño de dos prompts distintos
- Comparación entre prompting técnico y orientado a negocio
- Outputs generados
- Evaluación de resultados
- Estrategias para evitar alucinaciones

Enfoques principales:
- Grounding
- Contexto estructurado
- Restricción de información
- Validación manual de outputs

# Parte 4 — Diseño Conceptual de Agente / RAG

Notebook:
- `Parte 4_ Diseño de Agente_ RAG.ipynb`

Esta sección presenta una arquitectura conceptual basada en Retrieval Augmented Generation (RAG) para responder preguntas como:

> “¿Qué tipo de usuarios tienen mayor probabilidad de churn?”

Incluye:
- Arquitectura conceptual
- Pipeline de recuperación de información
- Estrategia de vectorización
- Embeddings propuestos
- Validación de respuestas
- Riesgos de alucinación y mitigación

# Tecnologías Utilizadas

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Jupyter Notebook

Herramientas conceptuales discutidas:
- LLMs
- RAG
- Vector Databases
- Embeddings
- LangChain / LlamaIndex

# Principales Hallazgos

- Desbalance severo de clases (~9.5% churn)
- Correlaciones débiles entre variables y churn
- Presencia de problemas de calidad de datos y outliers
- Riesgo potencial de data leakage temporal debido al esquema rolling window
- Variables insuficientes para una predicción robusta de churn

# Uso de Inteligencia Artificial

Se utilizaron herramientas de Inteligencia Artificial para:
- brainstorming,
- estructuración de explicaciones,
- prompt engineering,
- y revisión de conclusiones analíticas.

Todos los outputs generados fueron validados manualmente contra:
- resultados en Python,
- métricas del modelo,
- y hallazgos obtenidos durante el análisis exploratorio.

# Autor

Prueba técnica desarrollada por: D'Sharlie sANCHEZ rOZO
