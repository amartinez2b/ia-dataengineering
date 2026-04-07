# Ejercicio 01 - Generar un documento Word técnico con la skill docx

## Objetivo

Generar un documento de Word con toda la documentación técnica del proyecto desarrollado en los temas 11 y 12, usando la skill `docx` del repositorio público de Anthropic Skills.

El documento debe describir al menos:

- el proyecto base `multihope`
- el flujo `raw -> bronze -> silver -> gold`
- el proceso de `customers` ya existente y su reutilización como patrón
- la implementación para `products`, `sales` y `shops`
- la tabla final `gold/comercial`
- el DAG de Airflow que orquesta el pipeline

## Duración sugerida

40 a 60 minutos

## Requisito de contexto

Este laboratorio supone que el estudiante ya trabajó los temas 11 y 12 y por tanto ya dispone de:

- el proyecto PySpark desarrollado
- el DAG de Airflow diseñado o implementado
- información suficiente para documentar arquitectura, capas y flujo operativo

## Skill que se va a utilizar

- Repositorio de referencia: [anthropics/skills](https://github.com/anthropics/skills)
- Skill objetivo: `docx`

## Importante sobre la instalación

La skill `docx` forma parte del conjunto de skills de documentos. En Claude Code, lo correcto es instalar el plugin:

- `document-skills`

No hace falta instalar manualmente solo la carpeta `docx`.

## Parte A - Instalar las skills de documentos en Claude Code

Abre Claude Code y registra el marketplace oficial:

```text
/plugin marketplace add anthropics/skills
```

Luego instala el plugin de documentos:

```text
/plugin install document-skills@anthropic-agent-skills
```

### Opciones de instalación que aparecerán en pantalla

Cuando ejecutes ese comando, Claude Code mostrará opciones como estas:

- `Install for you (user scope)`
- `Install for all collaborators on this repository (project scope)`
- `Install for you, in this repo only (local scope)`

### Qué significa cada opción

#### `Install for you (user scope)`

Instala el plugin para tu usuario, de forma global en tu entorno.

Eso significa que:

- podrás usarlo en otros repositorios
- no quedará limitado solo al proyecto actual
- es la mejor opción si vas a reutilizar la skill durante el curso

### `Install for all collaborators on this repository (project scope)`

Instala el plugin para el repositorio, de modo que otros colaboradores de ese proyecto también puedan aprovechar esa configuración compartida.

Eso significa que:

- queda pensado para trabajo colaborativo dentro del repo
- tiene sentido cuando un equipo completo necesita la misma capacidad
- no suele ser la mejor primera opción para un laboratorio individual

### `Install for you, in this repo only (local scope)`

Instala el plugin solo para ti y solo dentro del repositorio actual.

Eso significa que:

- sirve si quieres probar la skill sin dejarla disponible en otros proyectos
- es útil para pruebas puntuales
- si cambias a otro repo, tendrás que volver a instalarla allí

### Qué opción tomar en este ejercicio

Para este laboratorio, la opción recomendada es:

- `Install for you (user scope)`

La razón es que esta skill puede seguir siendo útil en otros módulos o en otros repositorios del curso, especialmente cuando haya que generar documentación técnica adicional.

### Qué debería pasar

Después de instalarlo, Claude Code ya podrá usar skills de documentos como:

- `docx`
- `pdf`
- `pptx`
- `xlsx`

## Parte B - Confirmar el objetivo del documento

Antes de pedir el `.docx`, prepara la lista de secciones que debe contener.

Se recomienda que el documento tenga como mínimo estas partes:

1. portada
2. objetivo del proyecto
3. descripción del repositorio
4. arquitectura de capas
5. detalle de tablas `customers`, `products`, `sales` y `shops`
6. flujo de `raw -> bronze -> silver -> gold`
7. diseño de la tabla `gold/comercial`
8. descripción del DAG de Airflow
9. recomendaciones técnicas o próximos pasos

## Parte C - Preparar el prompt para la skill

La forma más clara de usar la skill es pedir explícitamente que Claude use `docx`.

### Prompt base sugerido

```markdown
# Rol
Actúa como un arquitecto de datos y redactor técnico senior.

# Instrucción principal
Usa la skill `docx` para generar un documento Word profesional.

# Objetivo
Crear un archivo `.docx` con la documentación técnica completa del proyecto desarrollado sobre `multihope`.

# Alcance del documento
Incluye:
- resumen del proyecto
- descripción del flujo existente de `customers`
- explicación de cómo se replicó el patrón para `products`, `sales` y `shops`
- detalle de las capas `raw`, `bronze`, `silver` y `gold`
- explicación de la tabla final `comercial`
- descripción técnica del DAG de Airflow
- conclusiones y siguientes pasos

# Requisitos
- el documento debe estar bien estructurado
- usa títulos y subtítulos claros
- agrega tablas si ayudan a resumir componentes o capas
- redacta en español técnico claro
- el resultado final debe ser un archivo `.docx`

# Formato esperado
1. propone el nombre del archivo
2. genera el contenido
3. crea el documento Word
```

## Parte D - Enriquecer el prompt

El estudiante debe mejorar el prompt base agregando al menos:

- nombre exacto del proyecto
- rutas o nombres reales de scripts importantes
- nombre real del DAG
- estructura de tablas y capas
- nivel de detalle esperado

La idea es que el documento no sea genérico, sino fiel al proyecto real.

## Parte E - Contenido mínimo esperado del documento

El documento final debe dejar claro:

- qué problema resuelve el proyecto
- qué hace el flujo existente de `customers`
- cómo se desarrolló la ingesta para `products`, `sales` y `shops`
- cómo se aplicó la limpieza a `silver`
- cómo se construye `gold/comercial`
- cómo el DAG de Airflow orquesta el pipeline

## Parte F - Revisión del resultado

Después de generar el documento, revisa:

- si el archivo `.docx` fue creado correctamente
- si los encabezados están ordenados
- si las tablas o listas se leen bien
- si el texto representa realmente el proyecto
- si no hay secciones inventadas o vagas

## Parte G - Mejora opcional

Si hay tiempo, pide una segunda versión del documento con alguna de estas mejoras:

- una tabla resumen de capas y tablas
- una tabla resumen de tareas del DAG
- una sección de riesgos técnicos
- una sección de próximos pasos

## Entregable

El estudiante debe presentar:

1. evidencia de instalación de `document-skills`
2. el prompt usado para generar el documento
3. el archivo `.docx` final
4. una explicación breve de cómo la skill ayudó en el proceso

## Criterio de éxito

El ejercicio está completo si el estudiante logra:

- instalar correctamente el plugin `document-skills`
- invocar la skill `docx`
- generar un archivo Word válido
- documentar correctamente el proyecto técnico de los temas 11 y 12
