# Ejercicio 04 - Usar variables dentro de un prompt

## Objetivo

Entender cómo usar variables dentro de un prompt para volverlo más reusable, más claro y más fácil de adaptar a distintos casos.

## Duración sugerida

15 a 20 minutos

## Idea principal

En muchos casos conviene escribir prompts como si fueran una plantilla. En lugar de repetir el mismo texto varias veces, puedes definir variables al inicio y luego referenciarlas dentro del prompt.

Esto ayuda a:

- reutilizar prompts
- reducir errores de edición
- cambiar valores sin reescribir toda la instrucción
- dejar más claro qué partes del prompt son dinámicas

## Ejemplo base

```markdown
FILENAME="archivo.xlsx"

Lee el archivo {{FILENAME}} y genera un resumen.
Luego mueve el archivo {{FILENAME}} a la carpeta DESKTOP del computador.
```

## Importante

Un LLM no siempre interpreta estas variables como lo haría un motor de plantillas real. Por eso, en la práctica este patrón funciona mejor cuando:

- el estudiante deja muy claro el valor de cada variable
- el prompt explica que debe reemplazar mentalmente cada variable por su valor
- el uso de variables mejora legibilidad y consistencia

## Versión mejorada del ejemplo

```markdown
# Variables
FILENAME="archivo.xlsx"
TARGET_FOLDER="DESKTOP"

# Instrucción
Usa los valores definidos en la sección `Variables`.

1. Lee el archivo {{FILENAME}} y genera un resumen ejecutivo.
2. Después indica cómo mover el archivo {{FILENAME}} a la carpeta {{TARGET_FOLDER}} del computador.

# Restricciones
- Si no puedes ejecutar la acción, explica el procedimiento exacto.
- No inventes contenido del archivo si no fue compartido.
- Si falta información, dilo explícitamente.
```

## Actividad

Toma este patrón y crea 3 prompts distintos usando variables.

### Caso 1 - Archivo de datos

Define variables como:

- `FILENAME`
- `FILE_TYPE`
- `OUTPUT_FORMAT`

Y crea un prompt para pedir análisis del archivo.

### Caso 2 - Script de código

Define variables como:

- `SCRIPT_NAME`
- `LANGUAGE`
- `TASK`

Y crea un prompt para pedir explicación o mejora de un script.

### Caso 3 - Error técnico

Define variables como:

- `ERROR_TYPE`
- `ENVIRONMENT`
- `EXPECTED_OUTPUT`

Y crea un prompt para pedir diagnóstico.

## Recomendaciones

Al usar variables en prompts:

- define las variables al inicio
- usa nombres claros y fáciles de entender
- mantén consistencia en la notación, por ejemplo `{{VARIABLE}}`
- no abuses: si hay demasiadas variables, el prompt se vuelve difícil de leer

## Preguntas para responder

- ¿Qué ventajas tiene escribir prompts como plantillas?
- ¿En qué casos podría ser confuso?
- ¿Cuándo conviene reemplazar variables manualmente antes de enviar el prompt?

## Entregable

El estudiante debe entregar:

1. un ejemplo de prompt base con variables
2. tres prompts nuevos creados por él
3. una reflexión breve sobre cuándo usaría esta técnica

## Conclusión esperada

El estudiante debería concluir que las variables dentro de un prompt ayudan a organizar y reutilizar instrucciones, pero que el prompt debe dejar muy claro cómo interpretar o sustituir esos valores para evitar ambigüedad.
