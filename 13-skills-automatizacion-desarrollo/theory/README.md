# Teoría - Módulo 13

## 1. ¿Qué es una skill?

Una **skill** es un paquete de instrucciones y recursos que le enseña a un agente cómo resolver mejor una tarea específica.

En lugar de pedirle al agente que improvise desde cero, una skill le da:

- contexto especializado
- reglas de trabajo
- formatos esperados
- herramientas o scripts asociados

## 2. ¿Por qué son útiles en ingeniería de datos?

En ingeniería de datos hay muchas tareas repetitivas o altamente estructuradas, por ejemplo:

- documentar pipelines
- generar plantillas técnicas
- revisar notebooks
- estructurar entregables
- crear reportes de ejecución

Una skill ayuda a que el agente sea más consistente y más eficiente al resolver ese tipo de tareas.

## 3. Qué problema resuelven las skills

Sin skill, el agente suele depender más del prompt puntual del usuario.

Con skill, el agente ya cuenta con una guía especializada que le ayuda a:

- reducir ambigüedad
- seguir un formato consistente
- evitar omisiones frecuentes
- producir resultados más profesionales

## 4. Qué tipos de skills existen

Según el caso de uso, puede haber skills para:

- documentos
- análisis de código
- testing
- automatización técnica
- diseño
- uso de herramientas externas

En este módulo trabajaremos con una skill de documentos:

- `docx`

## 5. Qué hace la skill `docx`

La skill `docx` está pensada para crear, leer, editar o manipular archivos Word `.docx`.

En este curso la usaremos para generar un documento técnico del proyecto que ya fue desarrollado en los temas 11 y 12.

Esto permite convertir el trabajo técnico del pipeline en un entregable formal para:

- líderes técnicos
- revisores del proyecto
- clientes internos
- equipos de soporte o continuidad

## 6. Cómo se integra una skill en Claude Code

En Claude Code, las skills pueden instalarse desde un marketplace o estar disponibles localmente.

En el caso del repositorio público de Anthropic, la instalación se hace registrando el marketplace y luego instalando el plugin correspondiente.

Para la skill `docx`, el punto importante es que forma parte del conjunto:

- `document-skills`

## 7. Qué sigue siendo responsabilidad del estudiante

Aunque la skill ayude a crear el documento, el estudiante debe validar:

- si la documentación representa correctamente el proyecto
- si el flujo `raw -> bronze -> silver -> gold` está bien explicado
- si el DAG de Airflow quedó bien descrito
- si el documento tiene estructura clara y usable

## 8. Flujo recomendado de trabajo con skills

Un flujo útil para este módulo es:

1. instalar la skill o el plugin que la contiene
2. revisar qué información del proyecto se va a documentar
3. preparar un prompt claro con el contenido esperado
4. pedir al agente que use la skill
5. revisar el documento final

## 9. Qué se aprende realmente en este módulo

Más allá de crear un archivo Word, este módulo enseña:

- cómo especializar agentes
- cómo automatizar entregables técnicos
- cómo documentar un proyecto de datos con mejor calidad
- cómo transformar trabajo técnico en un activo reutilizable

## 10. Ideas clave para llevarse

- una skill hace al agente más específico y más útil en un tipo de tarea
- documentar bien también es parte del desarrollo
- la automatización de documentación puede ahorrar mucho tiempo
- un buen entregable técnico debe ser claro, verificable y mantenible
