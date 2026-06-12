# Ejercicio 02 - Configurar MCP de MySQL en OpenCode y generar un catálogo de datos

## Objetivo

Repetir el ejercicio 01, pero esta vez usando **OpenCode** para conectarse a la base de datos `fake` mediante el servidor MCP `mcp_server_mysql` y generar el catálogo de datos de sus tablas.

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

La contraseña **no debe quedar escrita dentro del repositorio** ni en archivos compartidos. Debe mantenerse solo en configuración local del estudiante.

## Duración sugerida

40 a 60 minutos

## Cómo se configura MCP en OpenCode

La documentación oficial de OpenCode indica que los servidores MCP se configuran en el archivo:

```text
opencode.json
```

usando la clave:

- `mcp`

## Parte A - Crear o editar `opencode.json`

En la raíz del proyecto, crea o edita este archivo:

```text
opencode.json
```

Y agrega la configuración del MCP así:

```json
{
  "$schema": "https://opencode.ai/config.json",
  "mcp": {
    "mcp_server_mysql": {
      "type": "local",
      "command": [
        "npx",
        "-y",
        "@benborla29/mcp-server-mysql"
      ],
      "environment": {
        "MYSQL_HOST": "www.bigdataybi.com",
        "MYSQL_PORT": "3306",
        "MYSQL_USER": "curso",
        "MYSQL_PASS": "PASSWORD_PROPORCIONADO_POR_EL_INSTRUCTOR",
        "MYSQL_DB": "fake",
        "ALLOW_INSERT_OPERATION": "false",
        "ALLOW_UPDATE_OPERATION": "false",
        "ALLOW_DELETE_OPERATION": "false"
      }
    }
  }
}
```

## Parte B - Qué hace esta configuración

Esta configuración le dice a OpenCode que:

- registre un servidor MCP llamado `mcp_server_mysql`
- lo ejecute localmente con `npx`
- use el paquete oficial `@benborla29/mcp-server-mysql`
- aplique variables de entorno para conectarse a la base `fake`
- mantenga bloqueadas operaciones de escritura

## Parte C - Recomendación de seguridad

Para este laboratorio, la forma más segura es:

- editar `opencode.json` solo en tu entorno local
- no subirlo al repositorio si contiene la contraseña real

Si quieres mayor orden, puedes también evaluar una estrategia donde la contraseña provenga de variables locales del sistema, pero para clase este archivo local controlado puede ser suficiente siempre que no se comparta.

## Parte D - Reiniciar OpenCode

Después de guardar el archivo, cierra y vuelve a abrir OpenCode dentro del proyecto para que detecte el nuevo servidor MCP.

## Parte E - Validar que el MCP fue instalado correctamente

Antes de pedir el catálogo completo, haz una validación simple.

### Prompt de prueba sugerido

```markdown
# Rol
Actúa como un ingeniero de datos.

# Objetivo
Usa el servidor MCP `mcp_server_mysql` para conectarte a la base `fake` y decirme qué tablas existen.

# Restricciones
- no ejecutes operaciones de escritura
- solo inspecciona estructura
```

### Qué deberías observar

Si todo está bien configurado, OpenCode debería:

- detectar el servidor `mcp_server_mysql`
- conectarse a la base `fake`
- devolver una lista de tablas o una respuesta equivalente

## Parte F - Generar el catálogo de datos

Ahora pide el catálogo técnico de las tablas.

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

## Parte G - Actividad adicional

Pide a OpenCode un análisis más interpretativo:

```markdown
Usa el servidor MCP `mcp_server_mysql`, analiza el esquema de la base `fake` y dime:
- qué tablas parecen maestras o de dimensión
- cuáles parecen transaccionales
- qué relaciones potenciales ves entre ellas
- qué advertencias tendría que considerar antes de diseñar un pipeline sobre esta base
```

## Parte H - Revisión del catálogo

Después de generar el catálogo, valida:

- si todas las tablas quedaron documentadas
- si las descripciones tienen sentido
- si hay columnas importantes omitidas
- si el lenguaje es claro para otro ingeniero de datos

## Entregable

El estudiante debe presentar:

1. el archivo `opencode.json` con la configuración del MCP
2. evidencia de que OpenCode detectó o usó `mcp_server_mysql`
3. evidencia de conexión exitosa a la base `fake`
4. el catálogo de datos generado
5. una breve comparación con el ejercicio 01 en Claude Code

## Criterio de éxito

El ejercicio está completo si el estudiante logra:

- configurar correctamente `mcp_server_mysql` en OpenCode
- conectarse a la base `fake`
- inspeccionar las tablas con ayuda del agente
- producir un catálogo de datos técnico y usable
