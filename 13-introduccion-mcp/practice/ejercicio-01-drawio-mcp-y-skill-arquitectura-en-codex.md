# Ejercicio 01 - Instalar draw.io MCP y la skill `architecture-diagram-generator` en Codex

## Objetivo

Instalar en Codex:

- el MCP oficial de draw.io
- la skill `architecture-diagram-generator`

Luego usar ambas capacidades para:

1. leer el documento [arquitectura.md](/Users/agus/local/lab/bigdataybi/ia-dataengineering/13-introduccion-mcp/practice/arquitectura.md)
2. diseñar una arquitectura de datos basada en ese documento usando la skill
3. generar un diagrama técnico en HTML con la skill
4. crear en draw.io el diagrama de esa misma arquitectura diseñada usando el MCP

## Documento base del ejercicio

El insumo principal de este laboratorio es el archivo:

- `13-introduccion-mcp/practice/arquitectura.md`

Ese documento describe una arquitectura tipo Medallion y debe ser la base para todo el ejercicio.

La idea no es inventar una arquitectura distinta, sino:

1. leer y entender el contenido de `arquitectura.md`
2. usar la skill `architecture-diagram-generator` para diseñar el diagrama de esa arquitectura
3. usar el MCP `drawio` para crear el diagrama visual de la arquitectura ya diseñada

## Duración sugerida

40 a 60 minutos

## Referencias oficiales

- Skill: [Cocoon-AI/architecture-diagram-generator](https://github.com/Cocoon-AI/architecture-diagram-generator/tree/main)
- MCP: [jgraph/drawio-mcp](https://github.com/jgraph/drawio-mcp)

## Parte A - Instalar la skill en Codex

En Codex, la forma más simple para este laboratorio es dejar la skill dentro del repositorio.

La ruta recomendada es:

- `.agents/skills/architecture-diagram/`

Puedes lograrlo de cualquiera de estas formas:

- copiando la carpeta `architecture-diagram/` del repositorio de la skill
- extrayendo `architecture-diagram.zip` dentro de `.agents/skills/`

### Estructura mínima esperada

```text
.agents/
└── skills/
    └── architecture-diagram/
        ├── SKILL.md
        └── resources/
            └── template.html
```

## Parte B - Verificar que Codex detecte la skill

Abre Codex dentro del repositorio y valida que la skill aparezca.

Puedes comprobarlo así:

- usando el selector de skills con `$`
- verificando si aparece `architecture-diagram`
- invocándola explícitamente en el prompt

Si no aparece, revisa:

- que el directorio se llame `architecture-diagram`
- que exista `SKILL.md`
- que la skill esté dentro de `.agents/skills/`
- que Codex haya recargado el workspace o abierto un nuevo thread

## Parte C - Instalar el MCP de draw.io en Codex

Usa el comando:

```bash
codex mcp add drawio -- npx -y @drawio/mcp
```

### Qué hace este comando

- registra un servidor MCP llamado `drawio`
- usa `npx` para ejecutar el paquete oficial `@drawio/mcp`
- deja la integración lista para que Codex use herramientas como `open_drawio_xml`

## Parte D - Verificar el MCP en Codex

Puedes validar la configuración con:

```bash
codex mcp list
codex mcp get drawio
```

Luego haz una prueba mínima en Codex:

````markdown
Usa la herramienta `open_drawio_xml` para abrir este XML de draw.io:

```xml
<mxfile host="app.diagrams.net">
  <diagram name="Page-1">
    <mxGraphModel dx="800" dy="600" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="827" pageHeight="1169" math="0" shadow="0">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <mxCell id="2" value="Prueba Draw.io MCP" style="rounded=1;whiteSpace=wrap;html=1;" vertex="1" parent="1">
          <mxGeometry x="160" y="120" width="180" height="60" as="geometry"/>
        </mxCell>
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```
````

Si esta prueba funciona, el MCP ya está listo.

## Parte E - Revisar el documento de arquitectura

Antes de usar la skill, abre y revisa:

- `13-introduccion-mcp/practice/arquitectura.md`

Debes identificar al menos:

- objetivo de la arquitectura
- capas principales `bronze`, `silver` y `gold`
- propósito de cada capa
- ventajas, desventajas y recomendaciones

## Parte F - Diseñar la arquitectura con la skill

Ahora usa la skill para diseñar el diagrama de la arquitectura descrita en `arquitectura.md` y producir el entregable HTML.

### Prompt base sugerido

```markdown
$architecture-diagram

Lee el archivo `13-introduccion-mcp/practice/arquitectura.md` y, basándote en ese contenido, diseña un diagrama técnico de la arquitectura descrita allí.

Quiero que:

- uses el documento como fuente principal de contexto
- representes claramente las capas `bronze`, `silver` y `gold`
- reflejes el ciclo de vida de los datos y el propósito de cada capa
- generes un archivo `.html` autocontenido con un diagrama técnico profesional
- no inventes componentes ajenos al documento salvo que los marques explícitamente como apoyo visual
```

## Parte G - Diagramar la misma arquitectura en draw.io con MCP

Después de tener clara la arquitectura y de haber generado el HTML con la skill, pide a Codex que represente esa misma arquitectura diseñada en draw.io usando XML nativo de draw.io.

### Prompt base sugerido

```markdown
# Rol
Actúa como un arquitecto de datos.

# Objetivo
Usa la herramienta `open_drawio_xml` del MCP `drawio` para crear un diagrama editable de la arquitectura descrita en `13-introduccion-mcp/practice/arquitectura.md`.

# Contexto
Primero toma como base el contenido de `13-introduccion-mcp/practice/arquitectura.md` y el diseño de arquitectura que ya generaste con la skill `architecture-diagram`.

# Arquitectura a representar
- debe reflejar la arquitectura Medallion descrita en el documento
- debe mostrar claramente las capas `bronze`, `silver` y `gold`
- debe representar el flujo progresivo de los datos entre capas
- debe enfatizar el propósito de calidad, validación y consumo analítico

# Requisitos
- genera XML compatible con draw.io o mxGraph
- usa la herramienta `open_drawio_xml`
- produce un diagrama editable y, si es posible, un archivo `.drawio`
- abre el resultado con draw.io para revisión
- no inventes relaciones que contradigan el documento base
```

## Parte H - Revisar ambos resultados

Debes validar dos entregables:

- el archivo `.html` generado con la skill
- el diagrama abierto mediante draw.io MCP

Revisa:

- si ambos entregables están realmente basados en `arquitectura.md`
- si la arquitectura es coherente con el documento fuente
- si las capas `bronze`, `silver` y `gold` aparecen correctamente
- si el diagrama de draw.io refleja la misma lógica del HTML generado por la skill
- si el resultado es claro para otra persona del equipo

## Entregable

El estudiante debe presentar:

1. evidencia de la carpeta `.agents/skills/architecture-diagram/`
2. evidencia de instalación del MCP `drawio` en Codex
3. evidencia de la prueba mínima del MCP
4. evidencia de uso del archivo `13-introduccion-mcp/practice/arquitectura.md`
5. el prompt usado para la skill
6. el archivo `.html` resultante
7. el prompt usado para draw.io MCP
8. el diagrama generado en draw.io o el archivo `.drawio`

## Criterio de éxito

El ejercicio está completo si el estudiante logra:

- instalar la skill `architecture-diagram-generator` en Codex
- instalar el MCP `drawio` en Codex
- validar el uso de `open_drawio_xml`
- generar un diagrama técnico en HTML basado en `arquitectura.md`
- diagramar la misma arquitectura diseñada en draw.io o generar su archivo `.drawio`
