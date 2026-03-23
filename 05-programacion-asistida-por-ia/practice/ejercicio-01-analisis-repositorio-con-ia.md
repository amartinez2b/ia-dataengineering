# Ejercicio 01 - Analizar un proyecto de ingeniería de datos con apoyo de ChatGPT

## Objetivo

Usar ChatGPT como apoyo para analizar manualmente un proyecto real de ingeniería de datos, detectar fallas de funcionamiento, revisar vulnerabilidades, ejecutar notebooks y entender errores de ejecución de forma estructurada.

## Duración sugerida

35 a 45 minutos

## Repositorio base

- Repositorio: [amartinez2b/multihope](https://github.com/amartinez2b/multihope)


## Parte A - Descargar el repositorio como archivo `.zip`

En GitHub:

1. entra al repositorio [amartinez2b/multihope](https://github.com/amartinez2b/multihope)
2. usa la opción `Code`
3. selecciona `Download ZIP`
4. guarda el archivo en tu máquina

Opcionalmente, descomprime el proyecto para poder revisarlo localmente y ejecutar notebooks.

## Parte B - Subir el proyecto a ChatGPT

Abre ChatGPT y carga el archivo `.zip` del proyecto en un chat.

Luego usa un prompt como este:

```markdown
# Rol
Actúa como un ingeniero de datos senior.

# Objetivo
Ayúdame a analizar este proyecto de ingeniería de datos a partir del contenido del archivo cargado.

# Tarea
Quiero que identifiques:
- propósito probable del proyecto
- tecnologías usadas
- archivos y carpetas principales
- posibles puntos de entrada
- dudas o piezas que haría falta validar manualmente

# Formato de salida
Responde en una lista estructurada.
```

## Parte C - Hacer el análisis manual del proyecto

Con el proyecto abierto localmente, el estudiante debe revisar manualmente:

- estructura de carpetas
- notebooks
- scripts
- archivos de dependencias
- configuración
- documentación disponible

La IA puede ayudar a interpretar, pero el estudiante debe observar y decidir por sí mismo.

## Parte D - Detectar fallas de funcionamiento

Revisa manualmente el proyecto y usa ChatGPT para ayudarte a razonar sobre preguntas como:

- ¿hay archivos faltantes?
- ¿hay dependencias no declaradas?
- ¿hay notebooks o scripts que parecen incompletos?
- ¿el proyecto tiene instrucciones claras de ejecución?
- ¿hay señales de que algo podría fallar al correr?

Prompt sugerido:

```markdown
# Rol
Actúa como un reviewer técnico.

# Objetivo
Analiza este repositorio y detecta posibles fallas de funcionamiento.

# Criterios
- dependencias faltantes
- rutas rotas
- configuraciones incompletas
- notebooks que dependan de datos no incluidos
- problemas de mantenibilidad

# Formato de salida
Entrega una tabla con:
- problema
- impacto
- evidencia
- posible solución
```

## Parte E - Hacer un análisis básico de vulnerabilidades

Revisa el proyecto como si fuera un proyecto de datos que podría manejar información sensible. Apóyate en ChatGPT para ordenar el análisis, pero identifica tú mismo la evidencia dentro del código o notebooks.

Qué buscar:

- secretos expuestos
- dependencias desactualizadas o riesgosas
- ejecución insegura de código
- lectura/escritura de archivos sin validación
- celdas de notebook con prácticas inseguras

Prompt sugerido:

```markdown
# Rol
Actúa como un analista de seguridad de aplicaciones.

# Objetivo
Revisa este repositorio y detecta vulnerabilidades o malas prácticas de seguridad.

# Alcance
- secretos o credenciales
- dependencias inseguras
- riesgos de ejecución
- prácticas inseguras en notebooks o scripts

# Formato de salida
Entrega hallazgos priorizados con:
- severidad
- descripción
- evidencia
- recomendación
```

## Parte F - Ejecutar notebooks y analizar errores con ChatGPT

Abre los notebooks del proyecto y ejecútalos localmente.

Si aparece un error:

1. copia el error exacto
2. pégalo en ChatGPT junto con el fragmento relevante de código
3. pide una explicación de la causa probable
4. pide una propuesta de corrección

Prompt sugerido:

```markdown
# Rol
Actúa como un ingeniero de datos senior.

# Objetivo
Ayúdame a diagnosticar este error al ejecutar un notebook.

# Código o contexto
<pega aquí el fragmento relevante>

# Error
<pega aquí el traceback completo>

# Formato de salida
1. causa probable
2. explicación técnica
3. pasos para corregirlo
4. qué debería validar después de aplicar el cambio
```

## Parte G - Actividad adicional recomendada

Además del análisis anterior, realiza una de estas actividades:

- pedir a la IA una propuesta de mejora para el `README.md`
- pedir a la IA una lista de pruebas mínimas que faltan
- pedir a la IA una propuesta de refactor para un notebook o script
- pedir a la IA una lista de issues técnicos priorizados para abrir en GitHub

## Entregable

El estudiante debe entregar un informe breve con:

1. resumen del propósito del repositorio
2. fallas de funcionamiento detectadas
3. hallazgos de seguridad o vulnerabilidades
4. errores encontrados al ejecutar notebooks
5. explicación generada por ChatGPT sobre al menos un error
6. una actividad adicional realizada
7. reflexión final: ¿en qué ayudó ChatGPT y qué tuvo que analizar manualmente el estudiante?

## Conclusión esperada

El estudiante debería observar que ChatGPT puede acelerar mucho el análisis de un proyecto de ingeniería de datos, pero que la comprensión real del repositorio, la validación de funcionamiento y la identificación de evidencia siguen dependiendo del análisis manual del estudiante.
