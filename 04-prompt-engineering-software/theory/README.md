# Teoría - Módulo 04

## 1. ¿Qué es prompt engineering?

Prompt engineering es la práctica de diseñar instrucciones efectivas para que un modelo de lenguaje responda de forma más útil, precisa y consistente.

En desarrollo de software, esto significa aprender a pedir:

- explicaciones técnicas
- generación de código
- refactorizaciones
- debugging
- documentación
- pruebas

## 2. ¿Por qué importa tanto en software?

En tareas técnicas, un prompt débil puede producir:

- código incompleto
- suposiciones incorrectas
- librerías inventadas
- respuestas demasiado genéricas

En cambio, un prompt bien diseñado suele mejorar:

- precisión
- claridad
- formato de salida
- facilidad de validación

## 3. Componentes de un buen prompt

### Objetivo

Explica qué quieres lograr.

Ejemplo:

- "Genera un script PySpark para leer datos CSV y escribirlos en Parquet"

### Contexto

Da información relevante sobre el proyecto, dominio o restricciones.

Ejemplo:

- "Estoy trabajando en un pipeline batch diario de ventas"

### Rol

Puede ayudar pedir que el modelo responda desde una perspectiva concreta.

Ejemplo:

- "Actúa como un ingeniero de datos senior"

### Restricciones

Define límites o reglas.

Ejemplo:

- "No uses pandas"
- "Usa PySpark"
- "Incluye validación de columnas"

### Formato de salida

Indica cómo quieres recibir la respuesta.

Ejemplo:

- "Entrega el código completo y luego una explicación breve"
- "Responde en formato de tabla"

## 4. Estructura recomendada para prompts técnicos

Una estructura simple y muy útil es:

1. rol
2. objetivo
3. contexto
4. restricciones
5. formato esperado

Ejemplo:

```text
Actúa como un ingeniero de datos senior.
Necesito un script PySpark para leer un CSV de órdenes y calcular ventas diarias.
El pipeline corre una vez al día y debe ser simple y legible.
No uses pandas. Incluye validación de columnas.
Entrega primero el código y luego una explicación breve.
```

## 5. La importancia de usar Markdown al escribir prompts

En contexto técnico, escribir prompts en **Markdown** ayuda mucho más de lo que parece. No es solo una cuestión estética: Markdown permite separar ideas, reducir ambigüedad y volver el prompt más fácil de leer tanto para el humano como para el modelo.

### ¿Por qué conviene usar Markdown?

Porque permite estructurar mejor:

- títulos y secciones
- listas de requisitos
- bloques de código
- tablas
- notas y restricciones

### Beneficios prácticos

#### 1. Mejora la claridad

Un prompt con secciones es más legible que un párrafo largo y mezclado.

#### 2. Reduce ambigüedad

Si separas claramente:

- contexto
- objetivo
- restricciones
- formato esperado

el modelo tiende a responder de forma más ordenada.

#### 3. Hace más fácil iterar

Cuando un prompt está en Markdown, es mucho más fácil editar una sola parte sin reescribir todo.

#### 4. Ayuda a incluir código correctamente

Los bloques de código con triple backtick permiten:

- pegar código fuente
- mostrar errores
- compartir JSON
- compartir SQL o PySpark

sin mezclarlo con instrucciones.

### Ejemplo de prompt pobre vs prompt en Markdown

Prompt pobre:

```text
Actua como ingeniero de datos senior necesito un script pyspark para leer csv de ordenes filtrar pagadas calcular impuestos y escribir parquet no uses pandas y dame una explicacion breve
```

Prompt mejor estructurado con Markdown:

```markdown
# Rol
Actúa como un ingeniero de datos senior.

# Objetivo
Genera un script PySpark para leer un CSV de órdenes, filtrar órdenes pagadas, calcular impuestos y escribir el resultado en Parquet.

# Restricciones
- No uses pandas.
- Incluye validación básica de columnas.
- Usa nombres claros.

# Formato de salida
1. Entrega primero el código completo.
2. Luego agrega una explicación breve.
```

### Recomendación para el curso

Siempre que sea posible, conviene escribir prompts técnicos en Markdown usando:

- encabezados
- listas
- numeración
- bloques de código

Eso vuelve más consistente el trabajo con:

- ChatGPT
- Claude
- Gemini
- DeepSeek
- agentes de código

### Cómo introducir pedazos de código en el prompt usando Markdown

Cuando quieras que la IA:

- explique código
- corrija errores
- refactorice un script
- analice un comando

lo mejor es pegar el fragmento dentro de un bloque de código Markdown con su lenguaje.

### ¿Por qué es importante?

Porque así el modelo distingue mejor entre:

- tus instrucciones
- el código fuente
- la salida esperada

Eso reduce confusión y mejora la precisión.

### Ejemplo con Python

````markdown
# Objetivo
Explícame qué hace este script y detecta riesgos.

# Código
```python
import pandas as pd

df = pd.read_csv("orders.csv")
df = df[df["status"] == "paid"]
df["total_with_tax"] = df["total"] * 1.19
```

# Formato de salida
- Explicación paso a paso
- Riesgos detectados
- Mejoras sugeridas
````

### Ejemplo con shell

````markdown
# Objetivo
Explícame qué hace este comando y qué riesgos tiene.

# Comando
```bash
git checkout -b feature/nueva-rama
git add .
git commit -m "Agrega cambios"
git push origin feature/nueva-rama
```

# Formato de salida
1. Explica cada línea.
2. Indica riesgos o errores comunes.
3. Da una recomendación práctica.
````

### Recomendación práctica

Cuando el prompt incluya código:

- usa bloques con triple backtick
- indica el lenguaje: `python`, `bash`, `sql`, `json`, `yaml`, etc.
- separa claramente el bloque de código de las instrucciones
- si hay error, pega también el mensaje exacto en otro bloque aparte

## 6. Qué hace malo a un prompt

Ejemplos de problemas comunes:

- pedir algo demasiado ambiguo
- no dar contexto
- no indicar restricciones
- no pedir formato
- no decir para qué entorno o lenguaje se necesita

Prompt débil:

```text
Hazme un pipeline.
```

Prompt mejorado:

```text
Actúa como un ingeniero de datos senior.
Genera un script PySpark para leer un CSV de órdenes, filtrar órdenes pagadas, calcular ventas diarias y escribir el resultado en Parquet.
Incluye validación básica de columnas y usa nombres claros.
Entrega el código completo y después una lista breve de supuestos.
```

## 7. Técnicas útiles para iterar prompts

### Pedir paso a paso

Si la tarea es compleja, conviene dividirla.

Ejemplo:

- primero pedir análisis
- luego pedir diseño
- luego pedir código

### Pedir validación de supuestos

Ejemplo:

- "Antes de generar código, enumera los supuestos que estás haciendo"

### Pedir evidencia o límites

Ejemplo:

- "Si algo no se puede inferir, dilo explícitamente"

### Pedir mejora incremental

Ejemplo:

- "Toma tu respuesta anterior y mejora validaciones, legibilidad y manejo de errores"

## 8. La importancia de dar ejemplos en el prompt

Una de las técnicas más útiles en prompt engineering es **mostrar ejemplos de la salida esperada**. Cuando el modelo ve un ejemplo claro, le resulta mucho más fácil entender:

- el formato
- la estructura
- el nivel de detalle
- el tipo de campos esperados

Esto es especialmente importante cuando esperas:

- JSON
- SQL
- tablas
- documentación estructurada
- respuestas en listas o esquemas fijos

### ¿Por qué funciona tan bien?

Porque reduces ambigüedad. En lugar de decir solo "quiero un JSON", le enseñas al modelo cómo debería verse ese JSON.

### Ejemplo débil

```text
Analiza este error y responde en JSON.
```

Problemas:

- no queda claro qué claves debe tener el JSON
- el modelo puede usar nombres arbitrarios
- la estructura puede cambiar entre respuestas

### Ejemplo mejorado con salida esperada

````markdown
# Rol
Actúa como un ingeniero de datos senior.

# Objetivo
Analiza el siguiente error de ejecución y responde en formato JSON.

# Formato esperado
Usa exactamente esta estructura:

```json
{
  "error_type": "string",
  "possible_causes": ["string"],
  "recommended_fix": "string",
  "confidence": "high | medium | low"
}
```

# Restricciones
- No agregues claves adicionales.
- Si no sabes algo con certeza, indícalo en el valor correspondiente.
````

### Beneficios de dar ejemplos

- aumenta consistencia entre respuestas
- reduce variación innecesaria
- hace más fácil procesar la salida por código
- ayuda cuando luego quieres validar automáticamente la respuesta

### Recomendación práctica

Si esperas salida estructurada:

- da un ejemplo mínimo
- usa nombres de campos explícitos
- indica si puede haber listas, nulos o valores opcionales
- aclara si no deben agregarse claves extras

### Casos donde conviene muchísimo dar ejemplo

- JSON para APIs
- SQL esperado
- formato de documentación
- test cases
- objetos de configuración
- reportes en tabla

## 9. Prompts para generación de código confiable

Cuando pedimos código, es útil especificar:

- lenguaje
- librerías permitidas
- entrada y salida
- criterios de calidad
- manejo de errores
- pruebas o validaciones

## 10. Prompt engineering para Python y PySpark

### Para Python

Conviene indicar:

- versión esperada
- estilo
- funciones o script completo
- manejo de errores

### Para PySpark

Conviene indicar:

- que use `SparkSession`
- formato de entrada
- transformaciones esperadas
- formato de salida
- si debe escribir en Parquet o Delta

## 11. Ideas clave para llevarse

- un prompt es una especificación, no un deseo ambiguo
- contexto y restricciones mejoran mucho la respuesta
- Markdown ayuda a estructurar mejor el prompt
- dar ejemplos mejora mucho la consistencia del resultado
- pedir formato hace más fácil revisar la salida
- iterar prompts es parte normal del trabajo
- un mejor prompt reduce errores, pero no reemplaza la validación técnica
