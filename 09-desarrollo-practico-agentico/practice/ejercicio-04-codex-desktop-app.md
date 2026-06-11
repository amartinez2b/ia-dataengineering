# Ejercicio 04 - Usar Codex Desktop App sobre el proyecto

## Objetivo

Abrir el proyecto `multihope` en Codex Desktop App y usar esa interfaz para analizar archivos, pedir cambios y comparar la experiencia frente al uso por terminal.

## Duración sugerida

25 a 30 minutos

## Requisitos

Antes de comenzar, el estudiante debería tener:

- Codex ya funcionando en local
- el proyecto `multihope` ya importado a su cuenta personal y clonado localmente
- acceso al escritorio del sistema operativo

## Parte A - Abrir el proyecto con Codex Desktop App

Desde terminal, ubícate en la carpeta local del proyecto y ejecuta:

```bash
codex app .
```

Eso debería abrir Codex Desktop App usando el directorio actual como workspace.

## Parte B - Revisar el proyecto desde la interfaz visual

Una vez abierta la app:

1. confirma que `multihope` sea el workspace activo
2. ubica la conversación o panel principal
3. valida que puedes trabajar sobre el repositorio desde la interfaz

## Parte C - Hacer un análisis del proyecto desde la app

Usa Codex Desktop App sobre el proyecto `multihope`.

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

## Parte D - Pedir una mejora pequeña desde la app

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

## Parte E - Probar funciones útiles de la interfaz

Durante el ejercicio intenta usar al menos algunas de estas capacidades:

- abrir el proyecto desde la app con `codex app`
- trabajar sobre el workspace visible
- revisar archivos relevantes mientras conversas con el agente
- inspeccionar cambios propuestos
- comparar la experiencia visual con la terminal

## Parte F - Comparar la experiencia app vs terminal

Responde brevemente:

- ¿Qué fue más cómodo en la app?
- ¿Qué fue más claro en terminal?
- ¿En qué tipo de tarea usarías cada interfaz?

## Entregable

El estudiante debe entregar:

1. evidencia de que abrió Codex Desktop App sobre `multihope`
2. evidencia de que el proyecto quedó cargado como workspace
3. el prompt usado para el análisis
4. el prompt usado para la mejora pequeña
5. una breve comparación entre trabajar con Codex en terminal y en la app

## Conclusión esperada

El estudiante debería observar que Codex Desktop App ofrece una experiencia más visual y cómoda para recorrer el workspace y conversar con el agente, mientras que la terminal sigue siendo útil para flujos directos, repetibles o muy orientados a comando.
