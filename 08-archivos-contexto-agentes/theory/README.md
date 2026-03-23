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

## 3. ¿Qué es `CLAUDE.md`?

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

## 4. ¿Qué es `MEMORY.md`?

`MEMORY.md` se puede usar como archivo de memoria de trabajo o de decisiones acumuladas del proyecto.

Puede contener cosas como:

- decisiones ya tomadas
- errores frecuentes conocidos
- hallazgos importantes
- contexto histórico
- cosas que el agente debería recordar entre tareas

### Diferencia simple

- `CLAUDE.md`: instrucciones y reglas del proyecto
- `MEMORY.md`: recuerdos útiles y decisiones acumuladas

## 5. ¿Qué otros archivos ayudan al agente?

Además de `CLAUDE.md` y `MEMORY.md`, suele ayudar tener:

- `README.md`
- `.gitignore`
- `requirements.txt` o `pyproject.toml`
- documentación técnica
- ejemplos de prompts
- `.claude/settings.json`
- `.claude/settings.local.json`

## 6. ¿Qué podría contener un buen `CLAUDE.md`?

Ejemplos de secciones útiles:

- resumen del proyecto
- estructura de carpetas
- stack tecnológico
- comandos frecuentes
- estilo esperado
- cosas que no debe tocar el agente
- criterios de validación

## 7. ¿Qué podría contener un buen `MEMORY.md`?

Ejemplos de contenido útil:

- problemas ya detectados
- decisiones arquitectónicas
- limitaciones del entorno
- ideas pendientes
- pasos típicos de análisis

## 8. Comandos principales de Claude Code

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

## 9. Buenas prácticas para archivos de contexto

- escribir instrucciones concretas
- evitar texto demasiado ambiguo
- mantenerlos actualizados
- no convertirlos en documentación infinita
- separar reglas del proyecto de memoria histórica

## 10. Idea clave para llevarse

Los agentes no solo necesitan acceso al código. También necesitan contexto claro. `CLAUDE.md` y `MEMORY.md` ayudan a transformar un repositorio en un entorno mucho más comprensible para una IA.
