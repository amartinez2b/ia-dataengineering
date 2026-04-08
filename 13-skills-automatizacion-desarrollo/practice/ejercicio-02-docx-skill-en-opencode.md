# Ejercicio 02 - Generar un documento Word técnico con la skill docx en OpenCode

## Objetivo

Repetir el ejercicio 01, pero esta vez usando **OpenCode** y una instalación local de la skill `docx`, para generar un documento Word con la documentación técnica del proyecto desarrollado en los temas 11 y 12.

## Duración sugerida

40 a 60 minutos

## Base del ejercicio

El contenido técnico del documento debe cubrir, igual que en el ejercicio 01:

- el proyecto `multihope`
- el flujo `raw -> bronze -> silver -> gold`
- el proceso existente de `customers`
- la implementación de `products`, `sales` y `shops`
- la tabla final `gold/comercial`
- el DAG de Airflow del tema 12

## Referencias oficiales

- Skill oficial: [anthropics/skills - docx](https://github.com/anthropics/skills/tree/main/skills/docx)
- Skills en OpenCode: [OpenCode Skills](https://opencode.ai/docs/skills)

## Idea clave

A diferencia de Claude Code, en OpenCode la skill se descubre desde rutas del proyecto o del usuario. La forma más simple para este laboratorio es instalarla localmente dentro del repositorio.

## Parte A - Crear la carpeta local de skills para OpenCode

Dentro del repositorio del proyecto crea esta estructura:

```text
.opencode/
└── skills/
    └── docx/
```

Una forma simple de hacerlo es:

```bash
mkdir -p .opencode/skills/docx
```

## Parte B - Copiar la skill `docx`

Debes copiar a esa carpeta local el contenido de la skill `docx`.

Lo importante es no copiar solo `SKILL.md`. Para que la skill quede realmente útil, también debes incluir sus scripts asociados.

La carpeta final debería contener al menos:

- `SKILL.md`
- `scripts/`
- `LICENSE.txt`

### Estructura esperada

```text
.opencode/skills/docx/
├── SKILL.md
├── LICENSE.txt
└── scripts/
```

## Parte C - Por qué esta instalación funciona en OpenCode

La documentación oficial de OpenCode indica que las skills se descubren automáticamente desde rutas como:

- `.opencode/skills/<name>/SKILL.md`
- `.claude/skills/<name>/SKILL.md`
- `.agents/skills/<name>/SKILL.md`

Para este curso, la opción recomendada es:

- `.opencode/skills/docx/`

porque deja la skill visible dentro del proyecto y claramente asociada al laboratorio.

## Parte D - Verificar que OpenCode pueda descubrir la skill

Abre OpenCode dentro del repositorio y valida que la skill esté disponible.

La documentación oficial explica que OpenCode muestra las skills disponibles a través de su herramienta nativa `skill`, cargándolas bajo demanda.

Si la skill no aparece o no se usa correctamente, revisa:

- que el archivo se llame exactamente `SKILL.md`
- que el directorio se llame `docx`
- que el frontmatter del archivo siga siendo válido
- que la carpeta esté dentro de `.opencode/skills/`

## Parte E - Preparar el prompt

Ahora pide a OpenCode que use la skill `docx` para generar un documento Word.

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

## Parte F - Enriquecer el prompt

El estudiante debe mejorar el prompt con información real del proyecto, por ejemplo:

- nombre exacto del DAG
- rutas o nombres de scripts
- rutas de notebooks relevantes
- capas y tablas reales
- decisiones técnicas importantes del pipeline

## Parte G - Revisar el documento generado

Después de que OpenCode genere el documento, valida:

- si el archivo `.docx` fue creado correctamente
- si la estructura es clara
- si el contenido representa fielmente el proyecto
- si no hay secciones inventadas
- si el lenguaje técnico es consistente

## Parte H - Comparación con el ejercicio 01

Responde brevemente:

1. ¿Qué cambió al usar la misma skill en OpenCode en lugar de Claude Code?
2. ¿Qué ventajas tuvo instalar la skill localmente dentro del proyecto?
3. ¿Qué diferencias notaste en el flujo de uso?

## Entregable

El estudiante debe presentar:

1. evidencia de la carpeta `.opencode/skills/docx/`
2. evidencia de que OpenCode detectó o usó la skill
3. el prompt usado
4. el archivo `.docx` final
5. una breve comparación con el ejercicio 01

## Criterio de éxito

El ejercicio está completo si el estudiante logra:

- instalar correctamente la skill `docx` en OpenCode
- hacer que OpenCode la descubra desde `.opencode/skills/`
- generar un archivo Word válido
- documentar técnicamente el proyecto de los temas 11 y 12
