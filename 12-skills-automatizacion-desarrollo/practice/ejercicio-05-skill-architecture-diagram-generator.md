# Ejercicio 05 - Instalar la skill `architecture-diagram-generator` y generar un diagrama HTML

## Objetivo

Instalar la skill `architecture-diagram-generator` y usarla para generar un diagrama de arquitectura en un archivo `.html` que represente el ciclo de vida de los datos desde Oracle, pasando por procesamiento con Spark, hasta el consumo analítico en Power BI.

El resultado debe mostrar de forma clara:

- el sistema fuente en Oracle
- la ingesta hacia una zona `raw`
- las capas `bronze`, `silver` y `gold`
- el procesamiento con Spark
- el consumo final desde Power BI

## Duración sugerida

30 a 45 minutos

## Referencias

- Skill: [Cocoon-AI/architecture-diagram-generator](https://github.com/Cocoon-AI/architecture-diagram-generator/tree/main)
- Archivo de instalación incluido en el repositorio: `architecture-diagram.zip`

## Idea clave

No todas las skills generan texto o código aplicativo.

Algunas especializan al agente para producir entregables visuales. En este caso, la skill crea un diagrama técnico autocontenido en HTML con SVG embebido, útil para documentar arquitecturas de datos sin depender de herramientas externas de diagramación.

## Parte A - Instalar la skill en Claude Code

Para este laboratorio, la forma más simple es instalar la skill localmente dentro del proyecto.

Primero crea la carpeta de skills:

```bash
mkdir -p .claude/skills
```

Luego descarga `architecture-diagram.zip` desde el repositorio y extráelo dentro de `.claude/skills/`.

Ejemplo:

```bash
unzip RUTA/architecture-diagram.zip -d .claude/skills/
```

Si prefieres hacerlo manualmente, también puedes copiar la carpeta `architecture-diagram/` dentro de `.claude/skills/`.

## Parte B - Validar la estructura esperada

Después de extraer la skill, la estructura mínima debería verse así:

```text
.claude/
└── skills/
    └── architecture-diagram/
        ├── SKILL.md
        └── resources/
            └── template.html
```

No copies solo `SKILL.md`. La plantilla HTML en `resources/template.html` forma parte del funcionamiento de la skill.

Es normal que la carpeta local quede como `architecture-diagram`, aunque el repositorio público se llame `architecture-diagram-generator`.

## Parte C - Definir la arquitectura a diagramar

Antes de pedir el HTML, prepara una descripción estructurada del flujo.

La arquitectura de referencia para este ejercicio debe incluir como mínimo:

- un sistema fuente Oracle con tablas operacionales
- una ingesta con Spark usando JDBC o extracción incremental
- una zona `raw` o landing para dejar la copia inicial
- transformaciones Spark para construir `bronze`, `silver` y `gold`
- controles básicos de calidad o estandarización en `silver`
- una capa de consumo analítico desde `gold`
- Power BI como herramienta final de consulta y visualización

Si vienes trabajando el proyecto del tema 12, puedes agregar también:

- Airflow como capa de orquestación
- monitoreo o alertas de ejecución
- nombres reales de tablas o datasets del proyecto

## Parte D - Pedir al agente una descripción técnica primero

Antes de generar el diagrama, pide una versión textual bien organizada de la arquitectura.

### Prompt base sugerido

```markdown
# Rol
Actúa como un arquitecto de datos senior.

# Objetivo
Ayúdame a describir una arquitectura de datos para diagramarla después.

# Requisitos
- no generes HTML todavía
- describe componentes, capas y conexiones
- usa el ciclo de vida `source -> raw -> bronze -> silver -> gold -> consumo`
- considera Oracle como fuente
- considera Spark para ingesta y procesamiento
- considera Power BI para consumo
- si hace falta, agrega una capa ligera de orquestación y monitoreo

# Formato de salida
1. lista de componentes
2. conexiones entre componentes
3. observaciones de arquitectura
```

## Parte E - Generar el diagrama HTML con la skill

Cuando la descripción esté clara, pide al agente que use la skill instalada para generar el diagrama.

### Prompt base sugerido

```markdown
# Rol
Actúa como un arquitecto de datos experto en documentación técnica visual.

# Instrucción principal
Usa la skill `architecture-diagram` para generar un diagrama de arquitectura en un único archivo `.html`.

# Título del diagrama
Ciclo de vida de datos: Oracle -> Spark -> Power BI

# Arquitectura a representar
- Oracle es el sistema fuente transaccional
- Spark realiza la ingesta desde Oracle por JDBC con cargas batch o incrementales
- los datos llegan primero a una zona `raw`
- Spark transforma `raw` a `bronze` con estandarización inicial
- Spark transforma `bronze` a `silver` con limpieza, validaciones y modelo más consistente
- Spark construye una capa `gold` con datasets listos para analítica
- Power BI consume la capa `gold` para dashboards y reportes
- muestra el flujo de datos entre capas con flechas claras
- agrupa visualmente las zonas de source, ingestion, processing y consumption

# Requisitos del resultado
- el entregable final debe ser un archivo `.html`
- usa etiquetas claras en cada componente
- refleja explícitamente las capas `raw`, `bronze`, `silver` y `gold`
- evita componentes decorativos innecesarios
- incluye un aspecto profesional y técnico
- no dependas de imágenes externas

# Formato esperado
1. ruta sugerida del archivo
2. crea el archivo HTML final
3. breve explicación de la estructura representada
```

## Parte F - Revisar el resultado en el navegador

Después de generar el archivo, abre el `.html` y valida:

- que el archivo renderiza correctamente en el navegador
- que las flechas muestran el flujo de izquierda a derecha o de arriba abajo de forma clara
- que Oracle, Spark, `raw`, `bronze`, `silver`, `gold` y Power BI aparecen identificados
- que el resultado no parece un diagrama genérico ajeno al caso de datos
- que el HTML puede compartirse como entregable técnico

## Parte G - Iteración recomendada

Si el primer resultado queda muy simple o ambiguo, pide una segunda versión con mejoras como estas:

- separar visualmente fuente, procesamiento y consumo
- agregar Airflow como orquestador
- anotar si la ingesta es batch o incremental
- incluir un dataset analítico final en `gold`
- resaltar controles de calidad antes de Power BI

## Entregable

El estudiante debe presentar:

1. evidencia de instalación de la skill dentro de `.claude/skills/`
2. la descripción textual de la arquitectura
3. el prompt final usado para generar el diagrama
4. el archivo `.html` resultante
5. una explicación breve de cómo el diagrama representa el ciclo de vida de los datos

## Criterio de éxito

El ejercicio está completo si el estudiante logra:

- instalar correctamente la skill `architecture-diagram-generator`
- hacer que Claude Code pueda usarla desde el proyecto
- describir con claridad la arquitectura Oracle -> Spark -> Power BI
- generar un diagrama técnico válido en HTML
- representar visualmente el ciclo de vida de los datos de forma coherente
