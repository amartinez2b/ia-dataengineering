# Ejercicio 01 - Instalar MCP de MySQL y generar un catálogo de datos

## Objetivo

Instalar el MCP de MySQL, conectarse a una base de datos real y generar un documento con el catálogo de datos de cada una de las tablas de la base.

## Repositorio de referencia

- [benborla/mcp-server-mysql](https://github.com/benborla/mcp-server-mysql)

## Base de datos del ejercicio

Usa estas credenciales:

- `host`: `www.bigdataybi.com`
- `port`: `3306`
- `database`: `fake`
- `user`: `curso`
- `password`: proporcionado por el instructor

## Importante

La contraseña **no debe quedar escrita dentro del repositorio** ni en archivos compartidos del proyecto. Debe ingresarse solo en el comando o configuración local del estudiante.

## Duración sugerida

40 a 60 minutos

## Parte A - Instalar el MCP de MySQL

La guía oficial para Claude Code muestra una instalación manual con `claude mcp add` y variables de entorno.

El formato base indicado en el repositorio es este:

```text
claude mcp add mcp_server_mysql \
  -e MYSQL_HOST="127.0.0.1" \
  -e MYSQL_PORT="3306" \
  -e MYSQL_USER="root" \
  -e MYSQL_PASS="your_password" \
  -e MYSQL_DB="your_database" \
  -e ALLOW_INSERT_OPERATION="false" \
  -e ALLOW_UPDATE_OPERATION="false" \
  -e ALLOW_DELETE_OPERATION="false" \
  -- npx @benborla29/mcp-server-mysql
```

Fuente oficial:

- [README del proyecto](https://github.com/benborla/mcp-server-mysql)

## Parte B - Configurar la conexión del laboratorio

Para este curso, adapta el comando así:

```bash
claude mcp add mcp_server_mysql \
  -e MYSQL_HOST="www.bigdataybi.com" \
  -e MYSQL_PORT="3306" \
  -e MYSQL_USER="curso" \
  -e MYSQL_PASS="PASSWORD_PROPORCIONADO_POR_EL_INSTRUCTOR" \
  -e MYSQL_DB="fake" \
  -e ALLOW_INSERT_OPERATION="false" \
  -e ALLOW_UPDATE_OPERATION="false" \
  -e ALLOW_DELETE_OPERATION="false" \
  -- npx -y @benborla29/mcp-server-mysql
```

### Recomendación de alcance

La documentación del proyecto menciona estos scopes para Claude Code:

- local
- user
- project

Para este ejercicio, conviene usar:

- `local` o `user`

Evita `project scope` si incluye credenciales, para no compartirlas con otras personas a través del repositorio.

## Parte C - Verificar que el servidor quedó configurado

Después de agregar el MCP, usa estos comandos:

```bash
claude mcp list
claude mcp get mcp_server_mysql
```

Y dentro de Claude Code puedes revisar el estado con:

```text
/mcp
```

## Parte D - Conectarse a la base con el agente

Una vez configurado el MCP, pide al agente que inspeccione la base `fake` usando el nombre exacto del servidor configurado:

- `mcp_server_mysql`

### Prompt base sugerido

```markdown
# Rol
Actúa como un ingeniero de datos y analista de metadatos.

# Objetivo
Usa el servidor MCP `mcp_server_mysql` para conectarte a la base `fake` y explorar sus tablas.

# Requisitos
- identifica todas las tablas disponibles
- resume su estructura
- no ejecutes operaciones de escritura
- enfócate en inspección y documentación

# Formato de salida
1. lista de tablas
2. resumen general de cada tabla
3. propuesta de estructura para un catálogo de datos
```

## Parte E - Generar el catálogo de datos

Ahora pide al agente que genere un documento técnico con el catálogo de datos.

El catálogo debe incluir por cada tabla:

- nombre de la tabla
- propósito aparente
- columnas principales
- tipos de datos si están disponibles
- posible clave o identificador principal
- observaciones relevantes

### Prompt base sugerido

```markdown
# Rol
Actúa como un data architect y documentador técnico.

# Objetivo
Usa el servidor MCP `mcp_server_mysql` para generar un catálogo de datos de todas las tablas de la base `fake`.

# Requisitos
- inspecciona las tablas reales
- documenta cada tabla por separado
- usa lenguaje técnico claro en español
- si una columna es ambigua, indícalo
- no inventes relaciones que no estén justificadas

# Formato esperado
Para cada tabla incluye:
1. nombre
2. descripción
3. columnas relevantes
4. posibles claves
5. observaciones
```

## Parte F - Actividad adicional

Pide al agente una vista más analítica del esquema, por ejemplo:

- qué tablas parecen de dimensión
- qué tablas parecen transaccionales
- qué tablas podrían participar en un modelo comercial

### Prompt sugerido

```markdown
Usa el servidor MCP `mcp_server_mysql`, analiza el esquema de la base `fake` y dime:
- qué tablas parecen maestras o de dimensión
- cuáles parecen transaccionales
- qué relaciones potenciales ves entre ellas
- qué advertencias tendría que considerar antes de diseñar un pipeline sobre esta base
```

## Parte G - Revisión del catálogo

Después de generar el catálogo, valida:

- si todas las tablas quedaron documentadas
- si las descripciones tienen sentido
- si hay columnas importantes omitidas
- si el lenguaje es claro para otro ingeniero de datos

## Entregable

El estudiante debe presentar:

1. evidencia de instalación del MCP de MySQL
2. evidencia de conexión exitosa a la base `fake`
3. el catálogo de datos generado
4. una breve reflexión sobre cómo MCP ayudó a documentar la base

## Criterio de éxito

El ejercicio está completo si el estudiante logra:

- instalar correctamente el MCP de MySQL
- conectarse a la base `fake`
- inspeccionar las tablas con ayuda del agente
- producir un catálogo de datos técnico y usable
