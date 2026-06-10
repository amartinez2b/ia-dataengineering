# Ejercicio 02 - Crear `AGENTS.md` en Codex con `/init`

## Objetivo

Usar Codex dentro de un repositorio real para generar una primera versión de `AGENTS.md`, revisarla y ajustarla para que el agente entienda mejor el proyecto.

## Duración sugerida

20 a 30 minutos

## Requisitos previos

- haber completado el Ejercicio 01 o tener un repositorio local listo
- Codex disponible dentro del repositorio
- terminal disponible

## Contexto del ejercicio

En Claude Code el contexto persistente suele vivir en `CLAUDE.md` y `MEMORY.md`.

En Codex, en este curso vamos a usar `AGENTS.md` como archivo de contexto operativo del proyecto.

La idea es que el archivo le diga al agente:

- qué contiene el repositorio
- cómo está organizado
- qué comandos sirven para validar cambios
- qué riesgos o reglas debe respetar

## Parte A - Abrir el repositorio en Codex

Desde la raíz del repositorio, abre Codex:

```bash
codex
```

Si vienes del ejercicio anterior, puedes reutilizar el mismo repositorio trabajado allí.

## Parte B - Ejecutar `/init`

Dentro de Codex, ejecuta:

```text
/init
```

El objetivo de este paso es obtener una primera propuesta de contexto del workspace.

Si tu instalación no muestra `/init` en `/help`, usa un prompt equivalente como este:

```markdown
Ayúdame a crear un archivo `AGENTS.md` con una puesta en contexto clara de este workspace.
Incluye objetivo del proyecto, estructura principal, comandos útiles, riesgos y reglas de trabajo.
```

Luego guarda el resultado en `AGENTS.md`.

## Parte C - Revisar la primera versión de `AGENTS.md`

Después de `/init` o del prompt equivalente, revisa que `AGENTS.md` contenga como mínimo:

- propósito del proyecto
- carpetas o archivos principales
- tecnologías o dependencias visibles
- comandos útiles para inspección o validación
- reglas para no romper el repositorio
- riesgos o puntos sensibles

### Plantilla mínima sugerida

```markdown
# Proyecto
Breve descripción del repositorio y su objetivo.

# Estructura
- carpeta o archivo clave 1
- carpeta o archivo clave 2
- carpeta o archivo clave 3

# Flujo de trabajo
- primero revisar README
- luego inspeccionar estructura y dependencias
- validar cambios antes de cerrar la tarea

# Comandos útiles
- comando 1
- comando 2
- comando 3

# Reglas
- no borrar archivos sin justificarlo
- evitar cambios grandes sin explicar impacto
- respetar rutas de datos, notebooks o scripts críticos

# Riesgos
- dependencias faltantes
- datos no versionados
- pasos manuales de ejecución
```

## Parte D - Ajustar `AGENTS.md` al repositorio real

El archivo generado por IA no debe quedarse genérico. Debes:

1. reemplazar descripciones vagas por datos reales del repo
2. listar carpetas verdaderas del proyecto
3. anotar comandos que sí funcionen en tu entorno
4. agregar advertencias sobre archivos sensibles
5. dejar reglas cortas y accionables

## Parte E - Probar el valor del contexto

Haz dos consultas breves en Codex sobre el mismo repositorio.

### Prueba 1 - Antes de mejorar `AGENTS.md`

Pregunta algo como:

```markdown
Analiza este repositorio y resume propósito, estructura y riesgos iniciales.
```

Anota:

- claridad de la respuesta
- partes incompletas o genéricas
- longitud del prompt

### Prueba 2 - Después de ajustar `AGENTS.md`

Repite la misma consulta o una más corta, por ejemplo:

```markdown
Resume propósito, estructura y riesgos del proyecto.
```

Observa si:

- el agente usa mejor el contexto del repo
- necesitas menos explicación en el prompt
- la respuesta es más concreta

## Actividad final

El estudiante debe dejar listo:

- repositorio abierto en Codex
- archivo `AGENTS.md` generado y corregido
- lista breve de ajustes manuales realizados
- comparación corta sobre el valor del contexto persistente

## Entregable

1. evidencia de haber abierto Codex en el repositorio
2. evidencia de haber ejecutado `/init` o del prompt equivalente
3. contenido final de `AGENTS.md`
4. lista de mejoras hechas sobre la versión inicial
5. comparación breve entre la prueba antes y después de ajustar el contexto

## Conclusión esperada

El estudiante debería notar que `AGENTS.md` ayuda a que Codex entienda mejor el workspace, reduzca ambigüedad y responda con menos necesidad de repetir contexto en cada prompt.
