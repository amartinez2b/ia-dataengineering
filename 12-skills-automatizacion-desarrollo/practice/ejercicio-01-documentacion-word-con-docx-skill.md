# Ejercicio 01 - Generar un documento Word técnico con la skill docx

## Objetivo

Usar la skill `docx` en Codex para convertir el archivo Markdown [arquitectura.md](/Users/agus/local/lab/bigdataybi/ia-dataengineering/12-skills-automatizacion-desarrollo/practice/arquitectura.md) en un documento Word `.docx`, tomando como referencia de formato el archivo [msword.docx](/Users/agus/local/lab/bigdataybi/ia-dataengineering/12-skills-automatizacion-desarrollo/practice/msword.docx).

El resultado debe ser un archivo Word profesional que conserve el contenido del Markdown y además incorpore una presentación formal basada en la plantilla de ejemplo.

## Duración sugerida

30 a 45 minutos

## Requisito de contexto

Este laboratorio supone que el estudiante ya tiene disponible dentro del repositorio:

- el archivo fuente [arquitectura.md](/Users/agus/local/lab/bigdataybi/ia-dataengineering/12-skills-automatizacion-desarrollo/practice/arquitectura.md)
- el archivo de referencia [msword.docx](/Users/agus/local/lab/bigdataybi/ia-dataengineering/12-skills-automatizacion-desarrollo/practice/msword.docx)
- Codex funcionando correctamente

## Skill que se va a utilizar

- Repositorio de referencia: [anthropics/skills](https://github.com/anthropics/skills)
- Skill objetivo: `docx`

## Importante sobre la instalación

Para Codex, la forma más conveniente en este laboratorio es instalar la skill dentro del repositorio para que quede visible como parte del proyecto.

La ruta recomendada es:

- `.agents/skills/docx/`

No conviene copiar solo `SKILL.md`. La skill `docx` necesita también sus scripts asociados para poder trabajar correctamente.

## Parte A - Crear la carpeta local de skills para Codex

Dentro del repositorio crea esta estructura:

```text
.agents/
└── skills/
    └── docx/
```

Una forma simple de hacerlo es:

```bash
mkdir -p .agents/skills/docx
```

## Parte B - Copiar la skill `docx`

Debes copiar a esa carpeta local el contenido de la skill oficial `docx`.

La carpeta final debería contener al menos:

- `SKILL.md`
- `scripts/`
- `LICENSE.txt`

### Estructura esperada

```text
.agents/
└── skills/
    └── docx/
        ├── SKILL.md
        ├── LICENSE.txt
        └── scripts/
```

No copies únicamente `SKILL.md`, porque la skill necesita sus scripts para crear y manipular correctamente el documento Word.

## Parte C - Verificar que Codex descubra la skill

Abre Codex dentro del repositorio y valida que la skill esté disponible.

Puedes comprobarlo de cualquiera de estas formas:

- usando el selector de skills con `$`
- verificando si aparece `docx`
- invocándola explícitamente en el prompt

Si la skill no aparece, revisa:

- que el directorio se llame exactamente `docx`
- que exista el archivo `SKILL.md`
- que la carpeta esté dentro de `.agents/skills/`
- que Codex haya recargado el workspace o abierto un nuevo thread

## Parte D - Revisar los archivos de entrada

Antes de invocar la skill, revisa los dos archivos que se usarán en el ejercicio:

- contenido fuente: `12-skills-automatizacion-desarrollo/practice/arquitectura.md`
- plantilla de ejemplo: `12-skills-automatizacion-desarrollo/practice/msword.docx`

La idea no es copiar manualmente el contenido a Word, sino pedirle a Codex que:

- lea el contenido del Markdown
- tome como referencia visual y estructural el `.docx` de ejemplo
- genere un nuevo archivo Word bien formateado

## Parte E - Confirmar el objetivo del documento

Antes de pedir el `.docx`, ten claro qué debe hacer el resultado final.

El nuevo documento debe:

- conservar y reorganizar correctamente el contenido de `arquitectura.md`
- apoyarse en `msword.docx` como ejemplo de estilo y formato
- tener presentación profesional
- quedar como un archivo `.docx` listo para entregar

### No olvidar estas reglas al crear el documento

- agregar la portada del documento
- agregar cabecera y pie de página
- incluir páginas numeradas
- usar tablas con bordes negros
- poner en negritas los encabezados de todas las tablas

## Parte F - Preparar el prompt para la skill

En Codex, la forma más clara de usar la skill es invocarla explícitamente.

### Prompt base sugerido

```markdown
$docx

# Rol
Actúa como un arquitecto de datos y redactor técnico senior.

# Objetivo
Convierte el archivo `12-skills-automatizacion-desarrollo/practice/arquitectura.md` en un archivo `.docx`.

# Referencia de formato
Usa como referencia visual y estructural el archivo `12-skills-automatizacion-desarrollo/practice/msword.docx`.

# Alcance
- toma el contenido base desde `arquitectura.md`
- reorganízalo en un documento Word claro y profesional
- conserva el sentido técnico original del texto
- si agregas tablas para resumir información, deben respetar el formato solicitado

# Requisitos
- el documento debe estar bien estructurado
- usa títulos y subtítulos claros
- agrega la portada del documento
- agrega cabecera y pie de página
- incluye páginas numeradas
- todas las tablas deben tener bordes negros
- los encabezados de todas las tablas deben estar en negritas
- redacta en español técnico claro
- el resultado final debe ser un archivo `.docx`

# Formato esperado
1. propone el nombre del archivo
2. indica cómo usarás `arquitectura.md` y `msword.docx`
3. crea el documento Word
```

## Parte G - Enriquecer el prompt

El estudiante debe mejorar el prompt base agregando al menos:

- nombre final esperado del archivo `.docx`
- nivel de formalidad del documento
- si desea conservar o adaptar el estilo de la plantilla
- si quiere que alguna sección del Markdown se convierta en tabla
- cualquier detalle extra de portada, cabecera o pie de página

La idea es que el documento no sea una conversión plana, sino un entregable bien presentado.

## Parte H - Qué debe hacer realmente la skill

La skill debe ser capaz de:

- leer el contenido de `arquitectura.md`
- producir un nuevo `.docx` a partir de ese contenido
- tomar `msword.docx` como ejemplo de presentación
- construir un archivo final con formato profesional
- respetar los requisitos visuales definidos en este ejercicio

## Parte I - Revisión del resultado

Después de generar el documento, revisa:

- si el archivo `.docx` fue creado correctamente
- si el contenido de `arquitectura.md` quedó realmente incorporado
- si la portada fue agregada
- si existen cabecera y pie de página
- si las páginas están numeradas
- si los encabezados están ordenados
- si las tablas tienen bordes negros
- si los encabezados de tabla están en negritas
- si las tablas o listas se leen bien
- si el estilo se acerca al ejemplo `msword.docx`
- si no hay secciones inventadas o vagas

## Parte J - Mejora opcional

Si hay tiempo, pide una segunda versión del documento con alguna de estas mejoras:

- una portada más formal
- una tabla resumen de capas de la arquitectura Medallion
- una tabla comparativa de ventajas y desventajas
- mejor distribución de estilos entre títulos, tablas y secciones
- una versión más alineada visualmente con `msword.docx`

## Entregable

El estudiante debe presentar:

1. evidencia de la carpeta `.agents/skills/docx/`
2. evidencia de que Codex detectó o usó la skill
3. evidencia de que usó `arquitectura.md` como contenido fuente
4. evidencia de que tomó `msword.docx` como referencia de formato
5. el prompt usado para generar el documento
6. el archivo `.docx` final
7. una explicación breve de cómo la skill ayudó en el proceso

## Criterio de éxito

El ejercicio está completo si el estudiante logra:

- instalar correctamente la skill `docx` en Codex
- invocar la skill en Codex
- convertir `arquitectura.md` en un archivo Word
- usar `msword.docx` como referencia de formato
- generar un archivo Word válido
- incluir portada, cabecera, pie de página y numeración
- aplicar correctamente el formato de tablas solicitado
