# Ejercicio 01 - Preparar contexto persistente para Claude Code

## Objetivo

Hacer fork del repositorio `multihope`, clonarlo localmente y crear archivos de contexto que ayuden a Claude Code a entender mejor el proyecto.

## Duración sugerida

35 a 45 minutos

## Repositorio base

- Original: [amartinez2b/multihope](https://github.com/amartinez2b/multihope)

## Parte A - Hacer fork en tu cuenta personal

En GitHub:

1. entra al repositorio original
2. haz clic en `Fork`
3. crea una copia en tu cuenta personal

## Parte B - Clonar tu fork localmente

Desde terminal:

```bash
git clone https://github.com/TU-USUARIO/multihope.git
cd multihope
```

## Parte C - Generar `CLAUDE.md` con `/init`

En Claude Code, el archivo `CLAUDE.md` puede generarse automáticamente usando el comando:

```text
/init
```

Ese comando ayuda a crear una primera versión del archivo de contexto del proyecto.

Por lo tanto, en este ejercicio el estudiante no debe crear `CLAUDE.md` desde cero manualmente al principio. Primero debe:

1. abrir Claude Code dentro del repositorio
2. ejecutar `/init`
3. revisar el contenido generado
4. mejorarlo o completarlo según el proyecto

### ¿Para qué sirve?

Sirve para decirle a Claude Code:

- qué es el proyecto
- cómo está organizado
- qué tecnologías usa
- qué debe tener cuidado de no romper
- cómo debería trabajar en este repo

### Qué revisar o completar después de `/init`

```markdown
# Proyecto
Este repositorio contiene un proyecto de ingeniería de datos.

# Estructura
- notebooks/
- scripts/
- data/

# Objetivo
Ayudar a analizar, mantener y mejorar el proyecto sin romper notebooks ni rutas de datos.

# Reglas
- No borrar archivos sin justificarlo.
- Explicar cambios antes de hacer modificaciones grandes.
- Priorizar análisis de notebooks, dependencias y fallas de ejecución.
```

## Parte D - Abrir Claude Code y crear `MEMORY.md` con `/memory`

Desde la raíz del repositorio, abre Claude Code:

```bash
claude
```

Una vez dentro de Claude Code, ejecuta:

```text
/memory
```

Ese comando te permitirá crear o editar memoria útil para el proyecto.

### Qué debe hacer el estudiante

1. abrir Claude Code con `claude`
2. ejecutar `/memory`
3. crear memoria útil del proyecto
4. revisar el contenido generado
5. ajustarlo para que sea claro y corto

### ¿Para qué sirve `MEMORY.md`?

Sirve para guardar memoria útil del proyecto, por ejemplo:

- hallazgos importantes
- problemas conocidos
- decisiones tomadas
- recordatorios para tareas futuras

### Contenido mínimo sugerido

```markdown
# Memoria del proyecto

## Hallazgos iniciales
- El proyecto contiene notebooks que deben revisarse manualmente.
- Hay que validar dependencias y rutas de datos.

## Riesgos conocidos
- Posibles errores al ejecutar notebooks si faltan datasets o librerías.

## Próximas revisiones
- Revisar README
- Revisar dependencias
- Revisar notebooks principales
```

## Parte E - Ejercicio práctico de análisis y consumo de tokens

Ahora realiza una comparación simple para observar cómo el contexto persistente puede ayudar a trabajar con menos tokens.

### Escenario

Vas a pedir a Claude Code que analice el proyecto y te explique:

- propósito del repositorio
- carpetas principales
- riesgos funcionales iniciales

### Prueba 1 - Sin apoyarte en el contexto persistente

Haz una consulta detallada como esta:

```markdown
# Rol
Actúa como un ingeniero de datos senior.

# Objetivo
Analiza este repositorio y dime:
- cuál parece ser su propósito
- cuáles son sus carpetas principales
- qué riesgos funcionales iniciales detectas

# Formato de salida
Entrega una lista estructurada.
```

Observa y registra:

- número de tokens consumidos
- longitud de la respuesta
- calidad de la respuesta

### Prueba 2 - Apoyándote en `CLAUDE.md` y `MEMORY.md`

Ahora haz una consulta más corta, por ejemplo:

```markdown
Analiza el proyecto y resume propósito, estructura principal y riesgos iniciales.
```

Observa nuevamente:

- número de tokens consumidos
- longitud de la respuesta
- calidad de la respuesta

### Qué se espera observar

La idea no es garantizar que siempre baje drásticamente el número de tokens, sino que el estudiante note que:

- parte del contexto ya vive en `CLAUDE.md`
- el prompt puede ser más corto
- el agente necesita menos repetición para entender el proyecto
- el trabajo con contexto persistente puede volver más eficiente la interacción

## Actividad final

El estudiante debe dejar preparado el repositorio con:

- fork en GitHub
- clon local
- archivo `CLAUDE.md` generado con `/init` y luego ajustado
- archivo `MEMORY.md`
- una lista breve de otros archivos útiles para contexto
- una explicación corta de los comandos principales de Claude Code
- una comparación simple del análisis antes y después del contexto persistente

## Entregable

El estudiante debe entregar:

1. URL de su fork
2. evidencia de clonación local
3. evidencia de haber ejecutado `/init`
4. contenido final de `CLAUDE.md`
5. contenido de `MEMORY.md`
6. lista de otros archivos útiles
7. resumen corto de los comandos principales de Claude Code
8. comparación breve del análisis con foco en consumo de tokens y calidad de respuesta

## Conclusión esperada

El estudiante debería observar que un repositorio con contexto persistente bien escrito ayuda a Claude Code a trabajar con más claridad, menos ambigüedad y, en muchos casos, con prompts más cortos y eficientes en tokens.
