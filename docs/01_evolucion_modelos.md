
# 1. Evolución de los Modelos de Lenguaje

## Conceptos Fundamentales

- **Modelo de Lenguaje (LM):** Es un modelo estadístico o computacional diseñado para asignar probabilidades a secuencias de palabras o tokens. Su objetivo principal es predecir el siguiente token dentro de un texto basándose en el contexto previo.

- **Modelo de Lenguaje Grande (LLM):** Es la evolución de los LMs impulsada por la arquitectura *Transformer* y el escalamiento masivo en cantidad de parámetros y datos de entrenamiento. Un LLM no solo predice la siguiente palabra, sino que emerge con capacidades de comprensión contextual, traducción, resumen y generación de código.

## Modelos con Razonamiento Explícito (Inference-Time Compute)

A diferencia de los LLMs tradicionales que generan respuestas mediante una única pasada probabilística (token por token de forma directa), los **modelos con razonamiento explícito** (como OpenAI o1/o3, DeepSeek-R1) dedican tiempo de cómputo adicional durante la fase de inferencia para generar una "cadena de pensamiento" antes de dar la respuesta final.

### Origen de la Capacidad de Razonamiento
Esta capacidad **no aparece únicamente por aumentar el número de parámetros**, sino que proviene de:

1. **Técnicas de Entrenamiento Avanzadas:** 
   - Aprendizaje por Refuerzo con Retroalimentación Humana o Basada en Reglas (RLHF/RLAIF).
   - Generación y filtrado de trazas de razonamiento sintéticas mediante entrenamiento enfocado en la resolución sistemática de problemas matemáticos, lógicos y de programación.
2. **Cómputo en Tiempo de Inferencia (Inference-Time Compute):**
   - El modelo utiliza tokens adicionales invisibles o de proceso (*thinking tokens*) para evaluar múltiples hipótesis, corregir errores intermedios y planificar pasos lógicos antes de emitir la salida final al usuario.
