# Ejercicio 02 - Usar Claude Code dentro de Visual Studio Code

## Objetivo

Instalar la integración de Claude Code para Visual Studio Code y usarla sobre el mismo proyecto `multihope` del ejercicio 1 para analizar archivos, pedir cambios y trabajar desde el editor.

## Duración sugerida

25 a 30 minutos

## Referencia oficial

- Claude Code in VS Code: [code.claude.com/docs/en/ide-integrations](https://code.claude.com/docs/en/ide-integrations)

## Requisitos

Antes de comenzar, el estudiante debería tener:

- Visual Studio Code instalado
- Claude Code ya funcionando en local
- el proyecto `multihope` ya importado a su cuenta personal y clonado localmente

## Parte A - Abrir el proyecto en Visual Studio Code

Abre Visual Studio Code y luego abre la carpeta local de `multihope`.

## Parte B - Instalar la extensión de Claude Code

Dentro de Visual Studio Code:

1. abre el panel de extensiones
2. busca `Claude Code`
3. instala la extensión oficial
4. si hace falta, reinicia o recarga la ventana de VS Code

## Parte C - Abrir Claude Code dentro de VS Code

Puedes abrir Claude Code desde alguno de estos lugares:

- icono de Claude Code en la barra lateral
- comando desde la paleta de VS Code
- icono disponible en el editor

## Parte D - Hacer un análisis del proyecto desde el editor

Usa Claude Code dentro de VS Code sobre el proyecto `multihope`.

Prompt sugerido:

```markdown
# Rol
Actúa como un ingeniero de datos senior.

# Objetivo
Analiza este proyecto y dime qué archivos o notebooks revisaría primero para entender la lógica principal.

# Formato de salida
1. archivos recomendados
2. razón de cada uno
3. riesgos o dudas iniciales
```

## Parte E - Pedir una mejora pequeña desde Visual Studio Code

Selecciona un archivo o notebook del proyecto y pide una mejora limitada.

Prompt sugerido:

```markdown
# Objetivo
Propón una mejora pequeña de legibilidad o mantenibilidad en este archivo.

# Restricciones
- No cambies el comportamiento esperado.
- Explica primero el cambio.
- Muestra claramente el diff o la propuesta.

# Formato de salida
1. diagnóstico
2. cambio propuesto
3. advertencias
```

## Parte F - Probar funciones útiles de la integración

Durante el ejercicio intenta usar al menos algunas de estas capacidades:

- abrir Claude Code como panel o tab
- usar menciones de archivos
- enviar una selección concreta del código
- revisar un diff propuesto
- aceptar o rechazar una propuesta de edición

## Parte G - Comparar la experiencia VS Code vs terminal

Responde brevemente:

- ¿Qué fue más cómodo en VS Code?
- ¿Qué fue más claro en terminal?
- ¿En qué tipo de tarea usarías cada interfaz?

## Entregable

El estudiante debe entregar:

1. evidencia de que instaló la extensión de Claude Code en VS Code
2. evidencia de que abrió `multihope` en VS Code
3. el prompt usado para el análisis
4. el prompt usado para la mejora pequeña
5. una breve comparación entre trabajar con Claude Code en terminal y en VS Code

## Conclusión esperada

El estudiante debería observar que Claude Code en Visual Studio Code ofrece una experiencia más visual y cómoda para revisar archivos, cambios y diffs, mientras que la terminal sigue siendo útil para ciertos flujos más directos o automatizados.
