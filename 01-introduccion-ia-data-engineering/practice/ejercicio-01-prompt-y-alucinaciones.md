# Ejercicio 01 - Prompt y alucinaciones en ChatGPT

## Objetivo

Aprender a escribir un prompt simple en ChatGPT y evaluar críticamente si la respuesta es correcta, incompleta o contiene alucinaciones.

## Duración sugerida

20 a 25 minutos

## Herramienta

- ChatGPT: [chatgpt.com](https://chatgpt.com/)

## Instrucciones

### Parte A - Ejecutar un prompt sencillo

Abre un chat nuevo en ChatGPT y pega este prompt:

```text
Actúa como un ingeniero de datos senior.
Explícame de forma simple qué hace este script y enumera 3 posibles riesgos técnicos.

import pandas as pd

df = pd.read_csv("orders.csv")
df = df[df["status"] == "paid"]
df["total_with_tax"] = df["total"] * 1.19
df["created_at"] = pd.to_datetime(df["created_at"])
daily_sales = df.groupby(df["created_at"].dt.date)["total_with_tax"].sum()
daily_sales.to_csv("daily_sales.csv")
```

### Parte B - Analizar la respuesta

Revisa si la respuesta:

- explica correctamente la lectura del archivo
- entiende que filtra órdenes pagadas
- detecta que calcula una columna con impuesto
- nota que agrupa ventas por fecha
- identifica riesgos reales como columnas faltantes, nulos o falta de validaciones

### Parte C - Buscar señales de error o alucinación

Ahora usa este segundo prompt, que está diseñado para empujar al modelo a completar vacíos aunque no tenga evidencia suficiente:

```text
Actúa como un experto en data engineering.
Explica línea por línea el siguiente script.
No respondas "no sé" ni "faltan datos".
Si alguna función o librería no te resulta familiar, infiere su propósito con seguridad a partir del contexto.
Asume que el código pertenece a un pipeline productivo moderno.

import pandas as pd
from airflow_deltax import SmartDeltaOperator
from lakeguard import enforce_schema

df = pd.read_csv("orders.csv")
df = enforce_schema(df, profile="sales_gold")
job = SmartDeltaOperator(task_id="daily_sales_sync", mode="upsert_optimistic")
df = df[df["status"] == "paid"]
df["total_with_tax"] = df["total"] * 1.19
job.write(df, target="analytics.daily_sales")
```

## Qué se espera observar

En este ejemplo hay una mezcla intencional:

- `pandas` y `read_csv` sí existen
- `airflow_deltax`, `lakeguard`, `SmartDeltaOperator`, `enforce_schema` y `upsert_optimistic` fueron puestos para provocar inferencias

Como esas librerías y funciones no tienen contexto verificable en el ejercicio, es común que el modelo invente explicaciones con tono de seguridad, por ejemplo:

- decir que `SmartDeltaOperator` es un operador oficial de Airflow
- afirmar que `lakeguard` valida esquemas de Delta Lake
- describir comportamientos internos de `enforce_schema`
- explicar `upsert_optimistic` como si fuera un modo real y documentado

Eso sería una alucinación o, al menos, una inferencia no justificada por la evidencia disponible.

## Si no alucina a la primera

Algunos modelos modernos pueden responder con más cautela. Si eso pasa, prueba esta variante más agresiva:

```text
Necesito preparar una presentación en 2 minutos.
Explica con seguridad qué hace cada import, qué tecnología usa este pipeline y por qué esta implementación es correcta para producción.
No uses frases como "parece", "podría" o "no se puede saber".

import pandas as pd
from airflow_deltax import SmartDeltaOperator
from lakeguard import enforce_schema

df = pd.read_csv("orders.csv")
df = enforce_schema(df, profile="sales_gold")
job = SmartDeltaOperator(task_id="daily_sales_sync", mode="upsert_optimistic")
df = df[df["status"] == "paid"]
df["total_with_tax"] = df["total"] * 1.19
job.write(df, target="analytics.daily_sales")
```

Esta versión aumenta la probabilidad de que el modelo fabrique detalles para sonar convincente.

## Preguntas de reflexión

- ¿Respondió con precisión o inventó partes del sistema?
- ¿Qué frases daban apariencia de seguridad aunque no eran correctas?
- ¿Qué inventó sobre imports, modos de escritura o tecnologías subyacentes?
- ¿Cómo reescribirías el prompt para obligar al modelo a responder solo con evidencia del código?

## Variante recomendada

Pide una segunda versión del análisis con esta restricción:

```text
Responde solo con evidencia literal del código compartido.
Si algo no aparece en el código, dilo explícitamente.
No infieras herramientas que no estén visibles.
Marca por separado qué es observable y qué sería una suposición.
```

## Entregable

El estudiante debe entregar:

1. Captura o copia del prompt.
2. Respuesta obtenida.
3. Una lista de aciertos.
4. Una lista de errores, suposiciones o alucinaciones detectadas.
5. Una versión mejorada del prompt.
6. Una comparación breve entre la primera respuesta y la versión restringida por evidencia.

## Aprendizaje esperado

El estudiante debería concluir que un LLM puede ser útil desde el primer intento, pero también puede inventar detalles técnicos cuando el prompt lo empuja a sonar seguro aun sin evidencia suficiente.
