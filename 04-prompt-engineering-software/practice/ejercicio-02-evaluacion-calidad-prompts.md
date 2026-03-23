# Ejercicio 02 - Medir la calidad de un prompt

## Objetivo

Comparar dos versiones de un prompt y medir de forma más objetiva cuál funciona mejor usando una herramienta de evaluación de prompts.

## Duración sugerida

25 a 30 minutos

## Herramienta sugerida

- Promptfoo: [promptfoo.dev](https://www.promptfoo.dev/)

Promptfoo permite:

- comparar prompts lado a lado
- correr varios casos de prueba
- evaluar respuestas con reglas
- visualizar resultados en una interfaz web local

## Escenario

Quieres pedir a un LLM que explique código Python orientado a ingeniería de datos.

Vas a comparar:

- un prompt débil
- un prompt mejor estructurado en Markdown

## Paso 1 - Crear dos prompts

### Prompt A - Débil

```text
Explícame este código.
```

### Prompt B - Mejorado

```markdown
# Rol
Actúa como un ingeniero de datos senior.

# Objetivo
Explica el siguiente código Python paso a paso.

# Restricciones
- Describe entradas, salidas y supuestos.
- Detecta riesgos técnicos.
- No inventes librerías ni componentes que no aparezcan en el código.

# Formato de salida
1. Resumen general.
2. Explicación paso a paso.
3. Riesgos detectados.
4. Mejoras sugeridas.
```

## Paso 2 - Definir un caso de prueba

Usa este código como entrada:

```python
import pandas as pd

df = pd.read_csv("orders.csv")
df = df[df["status"] == "paid"]
df["total_with_tax"] = df["total"] * 1.19
df["created_at"] = pd.to_datetime(df["created_at"])
daily_sales = df.groupby(df["created_at"].dt.date)["total_with_tax"].sum()
daily_sales.to_csv("daily_sales.csv")
```

## Paso 3 - Evaluar con Promptfoo

Si tienes Node.js instalado, puedes usar:

```bash
npx -y promptfoo@latest init
```

La opción `-y` acepta automáticamente la instalación temporal del paquete y evita el prompt interactivo de `npm`.

Si prefieres hacerlo paso a paso, cuando aparezca:

```text
Ok to proceed? (y)
```

debes responder:

```text
y
```

Luego configura una comparación simple entre ambos prompts y al menos un caso de prueba.

Después ejecuta:

```bash
npx -y promptfoo@latest eval
```

Y para abrir la vista visual:

```bash
npx -y promptfoo@latest view
```

## Qué observar

Compara si el prompt mejorado:

- produce una respuesta más ordenada
- cubre mejor entradas, salidas y riesgos
- reduce suposiciones innecesarias
- sigue mejor el formato esperado

## Si no quieres configurar Promptfoo completo

También puedes usarlo de manera conceptual:

- ejecutar ambos prompts en el mismo modelo
- comparar manualmente las respuestas
- evaluar con una rúbrica simple

## Rúbrica sugerida

Califica cada respuesta del 1 al 5 en:

- claridad
- precisión
- cobertura de riesgos
- estructura
- utilidad técnica

## Entregable

El estudiante debe entregar:

1. Prompt A
2. Prompt B
3. la respuesta obtenida para cada uno
4. una tabla comparativa con la rúbrica
5. una conclusión sobre cuál prompt funcionó mejor y por qué

## Conclusión esperada

El estudiante debería concluir que un buen prompt no solo "suena mejor": también puede medirse por consistencia, claridad, cobertura y utilidad técnica.
