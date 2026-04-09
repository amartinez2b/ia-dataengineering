# Ejercicio 01 - Diseñar una arquitectura on premise segura para usar IA

## Objetivo

Diseñar una propuesta de arquitectura on premise segura para una empresa que quiere incorporar IA en sus procesos internos sin exponer información sensible ni permitir acciones destructivas sobre sus bases transaccionales.

## Escenario del ejercicio

La empresa tiene este contexto:

- trabaja principalmente con servidores **on premise**
- usa bases de datos transaccionales internas, especialmente **Oracle**
- hoy los equipos de desarrollo, analítica e ingeniería de datos se conectan con autenticación básica
- quiere incorporar IA para análisis, documentación, generación de SQL, desarrollo y soporte a procesos técnicos

La preocupación principal es:

- evitar fuga de información
- evitar que la IA borre datos o estructuras
- limitar el acceso a sistemas sensibles
- registrar y auditar el uso de IA

## Duración sugerida

45 a 60 minutos

## Parte A - Identificar los riesgos del escenario actual

Antes de diseñar la arquitectura objetivo, enumera al menos 8 riesgos del escenario actual.

Ejemplos de líneas de análisis:

- uso de usuarios compartidos
- ausencia de MFA
- acceso directo a bases transaccionales
- privilegios excesivos
- falta de auditoría centralizada
- credenciales en scripts o notebooks
- consultas destructivas sin control
- exposición de datos sensibles a herramientas de IA

## Parte B - Definir los componentes de la arquitectura objetivo

Diseña una propuesta mínima que incluya como mínimo estos componentes:

- capa de identidad corporativa
- gestión de secretos
- gateway o capa de acceso a IA
- zona de inferencia on premise
- conectores o MCP controlados
- capa de acceso seguro a datos
- auditoría y monitoreo

### Preguntas guía

1. ¿Dónde deberían autenticarse los usuarios?
2. ¿Dónde vivirían los modelos o agentes?
3. ¿Cómo se conectaría la IA a los datos?
4. ¿Qué capa impide acceso directo a producción?
5. ¿Dónde se registraría la actividad?

## Parte C - Diseñar el acceso a datos

Propón explícitamente cómo debería acceder la IA a los datos Oracle.

La respuesta debe cubrir:

- si la IA accede a producción o a una réplica
- si usa tablas directas, vistas o APIs
- qué permisos tendría la cuenta técnica de IA
- qué operaciones deben estar prohibidas

### Restricción clave

En tu propuesta, la IA no debe tener permisos para:

- `DELETE`
- `DROP`
- `TRUNCATE`
- `ALTER`

## Parte D - Definir controles de seguridad

Debes proponer controles concretos para estas áreas:

### Identidad y acceso

- SSO
- MFA
- roles por perfil
- cuentas técnicas separadas

### Secretos

- vault corporativo
- no guardar passwords en prompts
- rotación de credenciales

### Datos

- vistas curadas
- esquemas read-only
- enmascaramiento o redacción
- clasificación de datos

### Auditoría

- logs de agente
- logs de consultas
- correlación con usuario
- envío a SIEM

## Parte E - Diseñar el flujo permitido

Escribe un flujo permitido de extremo a extremo, por ejemplo:

1. el usuario entra con SSO + MFA
2. el usuario accede al gateway de IA
3. el agente usa un conector controlado
4. el conector consulta una vista read-only o réplica
5. la solicitud queda auditada
6. la respuesta vuelve al usuario con filtrado

## Parte F - Diseñar el flujo prohibido

Ahora describe al menos 3 flujos que tu arquitectura debe bloquear.

Ejemplos:

- un agente intentando conectarse directo a producción
- un prompt intentando borrar una tabla
- un usuario copiando secretos en un notebook

## Parte G - Usar IA para acelerar el diseño

Puedes usar un agente o un chat de IA para ayudarte a estructurar la propuesta.

### Prompt base sugerido

```markdown
# Rol
Actúa como un arquitecto empresarial de seguridad y datos.

# Contexto
Debo diseñar una arquitectura on premise segura para incorporar IA en una empresa con bases Oracle transaccionales.

# Objetivo
Ayúdame a proponer una arquitectura que reduzca fuga de información y evite acciones destructivas por parte de agentes o asistentes de IA.

# Requisitos
- incluye componentes de identidad, secretos, acceso a datos, inferencia, auditoría y monitoreo
- evita acceso directo de la IA a producción
- considera cuentas técnicas read-only
- usa lenguaje claro y técnico

# Formato de salida
1. riesgos actuales
2. arquitectura objetivo
3. componentes
4. controles
5. flujos permitidos
6. flujos prohibidos
```

## Parte H - Entregable

El estudiante debe entregar una propuesta que incluya:

1. lista de riesgos del escenario actual
2. arquitectura objetivo por componentes
3. política de acceso a datos para IA
4. controles de seguridad propuestos
5. flujo permitido
6. flujos prohibidos
7. recomendación final de implementación por fases

## Parte I - Criterio de éxito

El ejercicio está completo si el estudiante logra:

- identificar los riesgos principales del escenario actual
- proponer una arquitectura segura y realista
- separar claramente usuarios, agentes, datos y controles
- justificar cómo su propuesta reduce fuga de información y acciones destructivas
