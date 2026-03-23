# Ejercicio 01 - Conteo de tokens

## Objetivo

Entender que los modelos no leen el texto como una persona, sino como tokens, y observar cómo cambia el conteo cuando agregamos más contexto al prompt.

## Duración sugerida

15 a 20 minutos

## Herramienta

- OpenAI Tokenizer: [platform.openai.com/tokenizer](https://platform.openai.com/tokenizer)

## Instrucciones

### Parte A - Prompt corto

Copia este texto en el tokenizer:

```text
Explícame este código Python.

import pandas as pd

df = pd.read_csv("orders.csv")
df = df[df["status"] == "paid"]
df["total_with_tax"] = df["total"] * 1.19
df["created_at"] = pd.to_datetime(df["created_at"])
daily_sales = df.groupby(df["created_at"].dt.date)["total_with_tax"].sum()
daily_sales.to_csv("daily_sales.csv")
```

Anota:

- cantidad de tokens
- cantidad de caracteres
- impresión general del tamaño del prompt

### Parte B - Prompt con contexto

Ahora prueba este prompt:

```text
Actúa como un ingeniero de datos senior.
Explícame este código Python paso a paso.
Quiero que describas entradas, salidas, riesgos, supuestos y mejoras posibles.
Usa lenguaje claro para una persona que mantiene pipelines de datos.
Entrega la respuesta en formato de lista.

import pandas as pd

df = pd.read_csv("orders.csv")
df = df[df["status"] == "paid"]
df["total_with_tax"] = df["total"] * 1.19
df["created_at"] = pd.to_datetime(df["created_at"])
daily_sales = df.groupby(df["created_at"].dt.date)["total_with_tax"].sum()
daily_sales.to_csv("daily_sales.csv")
```

Anota nuevamente:

- cantidad de tokens
- cuánto aumentó respecto al prompt corto

### Parte C - Prompt con más contexto

Ahora usa esta versión más completa:

```text
Actúa como un ingeniero de datos senior.
Explícame este código Python paso a paso.
Quiero que describas entradas, salidas, riesgos, supuestos y mejoras posibles.
Usa lenguaje claro para una persona que mantiene pipelines de datos.
Entrega la respuesta en formato de lista.
No inventes librerías ni funciones que no estén presentes.
Si algo no se puede saber solo por el código, indícalo.
Resume al final qué debería validarse antes de usarlo en producción.

import pandas as pd

df = pd.read_csv("orders.csv")
df = df[df["status"] == "paid"]
df["total_with_tax"] = df["total"] * 1.19
df["created_at"] = pd.to_datetime(df["created_at"])
daily_sales = df.groupby(df["created_at"].dt.date)["total_with_tax"].sum()
daily_sales.to_csv("daily_sales.csv")
```

## Preguntas de reflexión

- ¿Cómo cambia el número de tokens cuando agregas contexto?
- ¿Qué parte del prompt consume más tokens: instrucciones o código?
- ¿Vale la pena usar más tokens si eso mejora la calidad de la respuesta?
- ¿Qué podría pasar si en un proyecto real pegas demasiado contexto innecesario?

## Conclusión esperada

Los estudiantes deberían observar que:

- más contexto suele significar más tokens
- más tokens pueden mejorar la precisión, pero también aumentan costo y tamaño
- conviene incluir contexto útil, no contexto excesivo

## Entregable

El estudiante debe entregar una tabla simple con tres filas:

- prompt corto
- prompt con contexto
- prompt con más contexto

Y estas columnas:

- descripción
- número de tokens
- observación
