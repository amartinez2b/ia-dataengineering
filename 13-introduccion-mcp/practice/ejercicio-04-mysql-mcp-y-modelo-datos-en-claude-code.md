# Ejercicio 04 - Instalar MySQL MCP en Claude Code y generar un modelo de datos

## Objetivo

Instalar el MCP de MySQL en Claude Code, conectarse a la base `fake`, leer las tablas reales y generar un modelo de datos inicial con ayuda del agente.

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

La contraseña no debe quedar escrita dentro del repositorio ni en archivos compartidos del proyecto. Debe mantenerse solo en configuración local del estudiante.

## Duración sugerida

40 a 60 minutos

## Parte A - Instalar el MCP de MySQL en Claude Code

Usa el comando:

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

Para este ejercicio conviene usar:

- `local` o `user`

Evita configuraciones compartidas si incluyen credenciales reales.

## Parte B - Verificar la configuración en Claude Code

Después de agregar el servidor, puedes revisar:

```bash
claude mcp list
claude mcp get mcp_server_mysql
```

Y dentro de Claude Code:

```text
/mcp
```

## Parte C - Probar la conexión a la base

Haz primero una prueba mínima:

```markdown
# Rol
Actúa como un ingeniero de datos.

# Objetivo
Usa el servidor MCP `mcp_server_mysql` para conectarte a la base `fake` y decirme qué tablas existen.

# Restricciones
- no ejecutes operaciones de escritura
- solo inspecciona estructura
```

Si la conexión funciona, ya puedes pasar al modelo de datos.

## Parte D - Inspeccionar tablas y relaciones candidatas

Ahora pide a Claude Code una lectura más estructurada del esquema.

### Prompt base sugerido

```markdown
# Rol
Actúa como un data architect.

# Objetivo
Usa el servidor MCP `mcp_server_mysql` para inspeccionar las tablas reales de la base `fake`.

# Requisitos
- identifica tablas disponibles
- resume columnas importantes
- detecta claves aparentes
- propone relaciones candidatas entre tablas
- distingue claramente entre relación confirmada e inferida
- no inventes información que no esté respaldada por el esquema

# Formato de salida
1. tablas detectadas
2. columnas clave por tabla
3. relaciones candidatas
4. observaciones y dudas
```

## Parte E - Generar el modelo de datos

El entregable principal de este ejercicio es un modelo de datos inicial.

Una forma útil de pedirlo es en Mermaid `erDiagram`, acompañado por observaciones técnicas.

### Prompt base sugerido

```markdown
# Rol
Actúa como un arquitecto de datos y modelador.

# Objetivo
Usa el servidor MCP `mcp_server_mysql` para generar un modelo de datos inicial de la base `fake`.

# Requisitos
- analiza tablas y columnas reales
- propone entidades y relaciones
- si una relación no es completamente segura, márcala como candidata
- entrega el modelo en formato Mermaid `erDiagram`
- agrega una breve explicación en español
- no ejecutes operaciones de escritura

# Formato esperado
1. resumen del esquema
2. diagrama Mermaid `erDiagram`
3. relaciones confirmadas o candidatas
4. advertencias de interpretación
```

## Parte F - Revisión del resultado

Después de generar el modelo de datos, valida:

- si el agente realmente leyó tablas existentes
- si el modelo cita entidades coherentes con la base
- si las relaciones dudosas están marcadas como inferencias
- si el Mermaid se puede reutilizar como documentación técnica

## Entregable

El estudiante debe presentar:

1. evidencia de instalación del MCP de MySQL en Claude Code
2. evidencia de conexión exitosa a la base `fake`
3. lista de tablas detectadas
4. el prompt usado para generar el modelo
5. el modelo de datos resultante
6. una breve reflexión sobre cómo MCP ayudó a inspeccionar la base

## Criterio de éxito

El ejercicio está completo si el estudiante logra:

- instalar el MCP de MySQL en Claude Code
- conectarse a la base `fake`
- inspeccionar tablas reales con el agente
- generar un modelo de datos inicial utilizable
- separar claramente observación real e inferencia
