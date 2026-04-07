# Ejercicio 01 - Pipeline PySpark con agentes de IA sobre multihope

## Objetivo

Usar agentes de IA para extender el repositorio `multihope` con un flujo de datos completo:

- ingesta de `raw` a `bronze` para `products`, `sales` y `shops`
- limpieza de `bronze` a `silver` para `products`, `sales` y `shops`
- consolidación de una tabla final `comercial` en `gold`

## Duración sugerida

60 a 75 minutos

## Repositorio base

- Original: [amartinez2b/multihope](https://github.com/amartinez2b/multihope)

## Herramientas permitidas

Todo el laboratorio debe hacerse con **agentes de IA**. Puedes usar uno o varios de estos:

- Claude Code
- Codex
- Gemini CLI
- OpenCode

## Parte A - Copiar el repositorio a tu cuenta personal

En GitHub:

1. entra al repositorio original
2. copia o importa el repositorio a tu cuenta personal
3. valida que la URL final quede bajo tu usuario, por ejemplo:

```text
https://github.com/TU-USUARIO/multihope.git
```

En este laboratorio no debes trabajar directamente sobre el repositorio original.

## Parte B - Crear la rama `dev`

En tu repositorio personal de GitHub:

1. crea una rama llamada `dev`
2. confirma que la rama exista en remoto antes de empezar a desarrollar

## Parte C - Clonar el proyecto localmente

```bash
git clone -b dev https://github.com/TU-USUARIO/multihope.git
cd multihope
```

Si prefieres clonar primero y cambiar de rama después:

```bash
git clone https://github.com/TU-USUARIO/multihope.git
cd multihope
git checkout dev
```

## Parte D - Análisis inicial con un agente

Abre el proyecto con tu agente y realiza un análisis inicial del repositorio.

### Objetivo del análisis

Identificar:

- estructura del proyecto
- notebooks existentes
- scripts existentes
- datasets o rutas de entrada
- carpetas donde conviene crear código nuevo
- cuál es la cuarta tabla del dominio comercial que ya existe o que debe inferirse desde el proyecto

### Prompt base sugerido

```markdown
# Rol
Actúa como un ingeniero de datos senior.

# Contexto
Estoy trabajando en un proyecto existente llamado `multihope`.

# Objetivo
Analiza el repositorio y explícame:
- cuál es la estructura principal del proyecto
- qué carpetas, notebooks y scripts son relevantes para un pipeline PySpark
- dónde conviene implementar una capa `bronze`, `silver` y `gold`
- qué tablas de negocio aparecen en el proyecto
- cuál podría ser la cuarta tabla que complemente `products`, `sales` y `shops` para construir una tabla final `comercial`

# Restricciones
- no inventes archivos si no están justificados por la estructura del repositorio
- explica tus supuestos
- propone una organización simple y coherente

# Formato de salida
Entrega:
1. resumen del repositorio
2. propuesta de carpetas o archivos
3. lista de tablas involucradas
4. plan de implementación
```

## Parte E - Desarrollar la capa `raw -> bronze`

Con ayuda del agente, implementa la ingesta de estas tablas:

- `products`
- `sales`
- `shops`

### Qué debe resolver esta etapa

- leer desde la fuente `raw`
- guardar la información en `bronze`
- mantener trazabilidad mínima
- dejar nombres y estructura consistentes

### Entregables mínimos de esta etapa

- script o scripts Python/PySpark para la ingesta
- notebooks de apoyo si hacen falta para exploración o validación
- explicación breve de dónde se guarda la salida `bronze`

### Prompt base sugerido

```markdown
# Rol
Actúa como un ingeniero de datos especializado en PySpark.

# Objetivo
Ayúdame a implementar la ingesta de `products`, `sales` y `shops` desde `raw` hacia `bronze` dentro de este repositorio.

# Requisitos
- usa la estructura real del proyecto
- proponme archivos concretos
- genera código claro y mantenible
- separa la lógica por tabla si eso mejora la claridad
- incluye comentarios mínimos útiles

# Formato de salida
- estructura propuesta
- código PySpark
- pasos para ejecutar
```

## Parte F - Desarrollar la capa `bronze -> silver`

Ahora crea la limpieza para:

- `products`
- `sales`
- `shops`

Debes generar:

- script Python/PySpark con la lógica principal
- notebooks para apoyar la validación o exploración de calidad

### Qué debe resolver esta etapa

- tipado de columnas
- tratamiento de nulos
- eliminación de duplicados si aplica
- normalización básica de textos o formatos
- validaciones mínimas de calidad

### Prompt base sugerido

```markdown
# Rol
Actúa como un ingeniero de datos senior experto en limpieza de datos con PySpark.

# Contexto
Ya existe una capa `bronze` para `products`, `sales` y `shops`.

# Objetivo
Genera la lógica para pasar estas tablas a `silver`, aplicando limpieza, estandarización y validaciones básicas.

# Requisitos
- usa PySpark
- genera un script principal reutilizable
- propone notebooks de validación para cada tabla o para el conjunto
- explica las reglas de limpieza aplicadas

# Formato de salida
1. reglas de limpieza
2. scripts propuestos
3. notebooks propuestos
4. criterios de validación
```

## Parte G - Construir la capa `gold`

En esta etapa debes combinar **cuatro tablas** para producir una estructura final llamada:

`comercial`

Como mínimo deben estar:

- `products`
- `sales`
- `shops`

La cuarta tabla debe ser identificada por el estudiante durante el análisis inicial del repositorio o definida con justificación técnica clara si el proyecto requiere crearla.

### Qué debe resolver esta etapa

- joins consistentes
- selección de columnas relevantes de negocio
- estructura final apta para análisis comercial
- almacenamiento en `gold`

### Prompt base sugerido

```markdown
# Rol
Actúa como un arquitecto de datos con experiencia en modelado analítico.

# Contexto
Ya existen tablas `silver` para `products`, `sales` y `shops`. Debo construir una tabla final `comercial` en `gold` combinando cuatro tablas del dominio comercial.

# Objetivo
Propón y genera la lógica PySpark para construir la tabla `comercial`.

# Requisitos
- justifica la cuarta tabla que se va a usar
- explica las llaves de join
- define las columnas finales orientadas a análisis comercial
- mantén el resultado consistente con la estructura real del proyecto

# Formato de salida
1. modelo lógico propuesto
2. joins y llaves
3. script PySpark
4. validaciones finales
```

## Parte H - Validación con agentes

Pide al agente que revise críticamente tu implementación.

Debes solicitarle al menos:

- detección de errores potenciales
- revisión de nombres de rutas y tablas
- riesgos de calidad de datos
- puntos débiles en joins o tipado
- mejoras posibles en la organización del código

### Prompt sugerido

```markdown
# Rol
Actúa como revisor técnico de un pipeline PySpark.

# Objetivo
Revisa mi implementación completa de `raw -> bronze -> silver -> gold` y detecta:
- errores potenciales
- supuestos no validados
- riesgos de calidad de datos
- oportunidades de mejora

# Restricciones
- prioriza problemas reales
- no des sugerencias genéricas
- cita archivos concretos del proyecto
```

## Parte I - Evidencia esperada

El estudiante debe dejar evidencia de:

- copia del repositorio en su cuenta personal
- rama `dev`
- clon local
- archivos nuevos o modificados para `bronze`
- script y notebooks para `silver`
- lógica de consolidación `gold/comercial`
- interacción con agentes de IA para análisis, generación y revisión

## Entregable

Debe presentar:

1. URL del repositorio personal
2. nombre de la rama `dev`
3. lista de archivos creados o modificados
4. explicación breve del flujo `raw -> bronze -> silver -> gold`
5. justificación de la cuarta tabla usada para `comercial`
6. evidencia de uso de agentes de IA
7. resultado final esperado de la tabla `comercial`

## Criterio de éxito

El ejercicio está completo si el estudiante logra:

- trabajar completamente sobre su copia del repositorio
- desarrollar en una rama `dev`
- usar agentes de IA durante todo el flujo
- implementar las tres capas del pipeline con coherencia
- producir una tabla final `comercial` en `gold`
