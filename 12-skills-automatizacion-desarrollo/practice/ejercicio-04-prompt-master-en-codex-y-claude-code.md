# Ejercicio 04 - Instalar y usar la skill `prompt-master` en Claude Code y Codex

## Objetivo

Instalar la skill `prompt-master` y usarla para transformar prompts débiles en prompts más precisos y reutilizables, tanto en Claude Code como en Codex.

La idea del ejercicio no es construir una skill nueva, sino aprender a incorporar una skill pública ya existente y aprovecharla para mejorar la calidad de las instrucciones que damos a nuestros agentes.

## Duración sugerida

30 a 45 minutos

## Repositorio de referencia

- Skill: [nidhinjs/prompt-master](https://github.com/nidhinjs/prompt-master)

## Qué hace esta skill

`prompt-master` está pensada para mejorar prompts.

Su foco no es ejecutar directamente una tarea técnica, sino ayudarte a redactar un mejor prompt para otra herramienta de IA, por ejemplo:

- Claude Code
- Codex
- ChatGPT
- Midjourney
- Cursor

En el contexto de este curso, sirve para convertir instrucciones vagas en prompts más útiles para trabajar sobre el proyecto del tema 12.

## Idea clave

Un agente produce mejores resultados cuando recibe mejores instrucciones.

Esta skill es útil porque permite:

- identificar qué información falta en un prompt
- hacer preguntas de aclaración mínimas
- producir un prompt más específico
- adaptar el prompt al agente o herramienta objetivo

## Parte A - Preparar un prompt débil de partida

Antes de instalar la skill, define un prompt inicial demasiado general.

Puedes usar uno como este:

```text
Necesito ayuda con el pipeline del tema 12.
```

O uno un poco más orientado a documentación:

```text
Quiero documentar mejor el proyecto del tema 12.
```

La meta del ejercicio será transformar ese tipo de pedido vago en un prompt más claro, útil y accionable.

## Parte B - Instalar `prompt-master` en Claude Code

El repositorio de `prompt-master` recomienda como alternativa para Claude Code clonar la skill directamente en el directorio de skills del usuario.

Para este laboratorio, usa esa ruta:

```bash
mkdir -p ~/.claude/skills
git clone https://github.com/nidhinjs/prompt-master.git ~/.claude/skills/prompt-master
```

### Qué validar

La carpeta final debería contener al menos:

- `SKILL.md`
- `references/`
- `LICENSE`

No conviene copiar solo `SKILL.md`, porque la skill consulta plantillas dentro de `references/`.

## Parte C - Usar `prompt-master` en Claude Code

Una forma clara de invocarla es usar su nombre explícitamente.

### Prompt sugerido para Claude Code

```markdown
/prompt-master

Convierte este prompt débil en un prompt sólido para Claude Code:

"Quiero documentar mejor el proyecto del tema 12."

Quiero que el prompt final:
- pida usar la skill `docx`
- genere un documento Word profesional
- describa el flujo `raw -> bronze -> silver -> gold`
- explique el DAG de Airflow del proyecto
- responda en español técnico claro

Si falta contexto, hazme máximo 3 preguntas antes de generar el prompt final.
```

### Qué hacer después

Cuando Claude Code te entregue el prompt mejorado:

1. cópialo
2. pégalo en una nueva interacción
3. ejecútalo para observar si el resultado es mejor que con el prompt original

## Parte D - Instalar `prompt-master` en Codex

En Codex, la forma más conveniente para este laboratorio es instalar la skill dentro del repositorio, de modo que quede visible como parte del proyecto.

La ruta recomendada es:

- `.agents/skills/prompt-master/`

### Estructura esperada

```text
.agents/
└── skills/
    └── prompt-master/
        ├── SKILL.md
        ├── LICENSE
        └── references/
```

Puedes lograrlo copiando el contenido del repositorio `prompt-master` dentro de esa carpeta.

Lo importante es incluir al menos:

- `SKILL.md`
- `references/`
- `LICENSE`

No copies únicamente `SKILL.md`, porque la skill necesita sus referencias para enrutar correctamente plantillas y recomendaciones.

## Parte E - Verificar que Codex descubra la skill

Abre Codex dentro del repositorio y valida que la skill aparezca.

Puedes comprobarlo de cualquiera de estas formas:

- usando el selector de skills con `$`
- verificando si aparece `prompt-master`
- invocándola explícitamente en el prompt

Si no aparece, revisa:

- que el nombre de la carpeta sea `prompt-master`
- que exista el archivo `SKILL.md`
- que la skill esté dentro de `.agents/skills/`
- que Codex haya recargado el workspace o abierto un nuevo thread

## Parte F - Usar `prompt-master` en Codex

En Codex, la forma más clara de probarla es invocarla explícitamente.

### Prompt sugerido para Codex

```markdown
$prompt-master

Convierte este prompt débil en un prompt sólido para Codex:

"Revisa el DAG del tema 12 y dime cómo mejorarlo."

Quiero que el prompt final le pida a Codex:
- inspeccionar primero el repositorio
- no modificar archivos
- devolver hallazgos priorizados
- citar rutas relevantes del proyecto
- responder en español

Si falta contexto, hazme máximo 3 preguntas antes de generar el prompt final.
```

### Qué hacer después

Cuando Codex te entregue el prompt mejorado:

1. cópialo
2. úsalo en una nueva conversación o thread
3. compara la calidad del resultado frente al prompt original

## Parte G - Comparación entre Claude Code y Codex

Al terminar, responde brevemente:

1. ¿Qué diferencias notaste al instalar una misma skill en Claude Code y en Codex?
2. ¿Qué tan útil fue `prompt-master` para mejorar instrucciones vagas?
3. ¿En qué tareas del curso usarías esta skill otra vez?

## Entregable

El estudiante debe presentar:

1. evidencia de instalación de `prompt-master` en Claude Code
2. evidencia de instalación de `prompt-master` en Codex
3. el prompt débil original
4. el prompt mejorado generado por la skill en cada herramienta
5. una comparación breve de resultados

## Criterio de éxito

El ejercicio está completo si el estudiante logra:

- instalar correctamente `prompt-master` en Claude Code
- instalar correctamente `prompt-master` en Codex
- invocar la skill en ambos entornos
- generar prompts mejorados a partir de una instrucción vaga
- comparar el valor práctico de la skill en el trabajo con agentes
