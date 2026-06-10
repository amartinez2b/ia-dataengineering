# Teoría - Módulo 08

## 1. ¿Qué es contexto persistente para un agente?

Cuando trabajamos con un agente, una parte del problema no es solo qué modelo usa, sino **qué sabe del proyecto**.

El contexto persistente es el conjunto de archivos e instrucciones que ayudan al agente a entender:

- qué hace el proyecto
- cómo está organizado
- qué decisiones ya se tomaron
- qué restricciones existen
- cómo debe comportarse dentro del repositorio

## 2. ¿Por qué hace falta?

Si un agente entra a un proyecto sin contexto:

- puede interpretar mal el objetivo
- puede sugerir cambios fuera de estilo
- puede ignorar restricciones importantes
- puede repetir errores ya conocidos

Con archivos de contexto, el agente trabaja con más consistencia.

## 3. Archivos de contexto más comunes

No todos los equipos usan exactamente los mismos archivos, pero hay varios patrones que aparecen una y otra vez cuando se trabaja con agentes.

## 4. ¿Qué aporta `README.md`?

`README.md` suele ser el primer archivo que revisa una persona y también uno de los más valiosos para un agente.

Normalmente resume:

- qué hace el proyecto
- cómo está organizado
- cómo ejecutarlo
- dependencias principales
- flujo básico de uso

### ¿Por qué ayuda tanto?

Porque da una vista general del repositorio y reduce errores de interpretación desde el inicio.

## 5. ¿Qué es `AGENTS.md`?

`AGENTS.md` es un archivo muy útil para darle a un agente instrucciones operativas sobre cómo trabajar dentro del repositorio.

Suele incluir cosas como:

- objetivo del proyecto
- estructura del workspace
- comandos frecuentes
- restricciones importantes
- reglas para editar, probar o documentar cambios

### ¿Para qué sirve?

Sirve como guía de trabajo para agentes como Codex, especialmente cuando queremos que el agente entienda cómo colaborar dentro del repo y no solo qué contiene.

## 6. ¿Qué es `CLAUDE.md`?

`CLAUDE.md` es un archivo de instrucciones de proyecto orientado a Claude Code.

Normalmente se usa para dejar claro:

- propósito del proyecto
- estructura del repositorio
- convenciones importantes
- comandos frecuentes
- restricciones
- forma esperada de trabajar

### ¿Para qué sirve?

Sirve como guía rápida para que el agente no tenga que inferir todo desde cero cada vez.

## 7. ¿Qué es `MEMORY.md`?

`MEMORY.md` se puede usar como archivo de memoria de trabajo o de decisiones acumuladas del proyecto.

Puede contener cosas como:

- decisiones ya tomadas
- errores frecuentes conocidos
- hallazgos importantes
- contexto histórico
- cosas que el agente debería recordar entre tareas

### Diferencia simple

- `AGENTS.md` o `CLAUDE.md`: instrucciones y reglas del proyecto
- `MEMORY.md`: recuerdos útiles, hallazgos y decisiones acumuladas

## 8. ¿Qué es `ARCHITECTURE.md`?

`ARCHITECTURE.md` sirve para explicar cómo está diseñado el sistema más allá de la estructura de carpetas.

Puede incluir:

- componentes principales
- relación entre servicios o módulos
- flujo de datos
- decisiones arquitectónicas relevantes
- límites o responsabilidades de cada parte del sistema

### ¿Cuándo ayuda especialmente?

Cuando el repositorio ya no es pequeño y entender solo archivos y carpetas no alcanza para comprender el sistema.

## 9. ¿Qué es `TASKS.md`?

`TASKS.md` sirve para registrar trabajo pendiente o pasos de ejecución de una forma simple y visible.

Puede contener:

- tareas abiertas
- prioridades
- checklist de implementación
- próximos pasos
- validaciones pendientes

### ¿Por qué puede ser útil para un agente?

Porque le da contexto sobre qué se esperaba hacer, qué está pendiente y qué partes del trabajo todavía no deben darse por cerradas.

## 10. Otros archivos que también ayudan mucho

Además de los archivos anteriores, hay documentos que no siempre se crean pensando en agentes, pero que igual aportan muchísimo contexto.

### `CONTRIBUTING.md`

Sí, suele ser muy importante también. Aunque no sea un archivo de contexto "especial" para IA, ayuda a Codex y a otros agentes porque explica:

- cómo contribuir al proyecto
- convenciones de ramas o commits
- cómo correr pruebas
- reglas de revisión
- expectativas del equipo para aceptar cambios

### `docs/`

La carpeta `docs/` también suele ser valiosa cuando existe, porque puede contener:

- decisiones técnicas
- diagramas
- manuales de uso
- documentación funcional
- notas de operación

En muchos proyectos, `docs/` termina siendo más útil para el agente que un único archivo corto, porque conserva contexto técnico que no cabe completo en `README.md`.

### Otros ejemplos útiles

- `.gitignore`
- `requirements.txt` o `pyproject.toml`
- ejemplos de prompts
- `.claude/settings.json`
- `.claude/settings.local.json`

## 11. ¿Qué podría contener un buen `CLAUDE.md`?

Ejemplos de secciones útiles:

- resumen del proyecto
- estructura de carpetas
- stack tecnológico
- comandos frecuentes
- estilo esperado
- cosas que no debe tocar el agente
- criterios de validación

## 12. ¿Qué podría contener un buen `MEMORY.md`?

Ejemplos de contenido útil:

- problemas ya detectados
- decisiones arquitectónicas
- limitaciones del entorno
- ideas pendientes
- pasos típicos de análisis

## 13. Comandos principales de Claude Code

En Claude Code existen varios comandos slash útiles en el trabajo diario.

### `/help`

Muestra ayuda general y comandos disponibles.

### `/init`

Inicializa el proyecto con una guía de `CLAUDE.md`.

### `/memory`

Permite editar o gestionar archivos de memoria relacionados con `CLAUDE.md`.

### `/config`

Permite ver o modificar configuración.

### `/status`

Muestra estados generales de cuenta y sistema.

### `/model`

Permite elegir o cambiar modelo.

### `/clear`

Limpia el historial de conversación de la sesión actual.

### `/doctor`

Verifica el estado de la instalación de Claude Code.

## 14. Comandos principales de Codex

En Codex, a diferencia de Claude Code, es común trabajar con comandos de terminal del CLI más que con comandos slash.

### `codex`

Abre Codex en modo interactivo dentro del directorio actual. También puede recibir un prompt inicial.

### `codex exec`

Ejecuta Codex de forma no interactiva para resolver una tarea puntual desde terminal.

### `codex review`

Sirve para pedir una revisión de código no interactiva sobre el repositorio actual.

### `codex resume`

Permite retomar una sesión interactiva anterior.

### `codex fork`

Permite bifurcar una sesión previa para explorar otra alternativa sin perder el historial anterior.

### `codex apply`

Aplica al árbol de trabajo el último diff generado por Codex.

### `codex doctor`

Diagnostica la instalación local, la autenticación, la configuración y el estado general de Codex.

### `codex update`

Actualiza Codex a la versión más reciente disponible.

### `codex mcp`

Permite gestionar servidores MCP conectados a Codex.

### `codex plugin`

Permite gestionar plugins disponibles para ampliar capacidades.

### `codex archive` y `codex unarchive`

Sirven para archivar o restaurar sesiones guardadas.

## 15. Buenas prácticas para archivos de contexto

- escribir instrucciones concretas
- evitar texto demasiado ambiguo
- mantenerlos actualizados
- no convertirlos en documentación infinita
- separar reglas del proyecto de memoria histórica
- evitar duplicar la misma información en muchos archivos
- dejar claro qué archivo explica el qué, el cómo y el porqué

## 16. Idea clave para llevarse

Los agentes no solo necesitan acceso al código. También necesitan contexto claro. Archivos como `README.md`, `AGENTS.md`, `CLAUDE.md`, `MEMORY.md`, `ARCHITECTURE.md`, `TASKS.md`, `CONTRIBUTING.md` y `docs/` ayudan a transformar un repositorio en un entorno mucho más comprensible para una IA.
