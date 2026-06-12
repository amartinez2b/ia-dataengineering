# Teoría - Módulo 15

## 1. MCP como puente hacia herramientas reales

En el módulo anterior vimos MCP como concepto. En este módulo lo aterrizamos a un caso muy útil en ingeniería de datos:

- conectar un agente a una base de datos

Esto permite que el agente no solo “hable sobre datos”, sino que pueda:

- inspeccionar esquemas
- listar tablas
- revisar columnas
- ejecutar consultas controladas
- producir documentación a partir de la estructura real

## 2. Por qué esto importa en ingeniería de datos

Muchos equipos pierden tiempo documentando manualmente:

- tablas
- columnas
- relaciones
- reglas de negocio

Si un agente puede conectarse a la base y explorar el esquema con seguridad, se vuelve mucho más fácil generar:

- catálogos de datos
- diccionarios de datos
- resúmenes técnicos
- documentación de onboarding

## 3. Qué rol cumple el MCP de MySQL

Un MCP de MySQL permite exponer al agente operaciones orientadas a:

- conectarse a una instancia MySQL
- explorar metadatos
- consultar información de tablas
- ejecutar consultas SQL controladas

En este curso, el objetivo no es hacer escritura sobre la base, sino usar el acceso para documentación e inspección.

## 4. ¿Existe MCP para Oracle?

Sí. Hoy ya existe oferta oficial de Oracle alrededor de MCP.

Hay dos líneas importantes:

- **Oracle SQLcl MCP Server**
- **Oracle Autonomous AI Database MCP Server**

### 4.1 Oracle SQLcl MCP Server

Oracle integró capacidades MCP en **SQLcl**, su herramienta de línea de comandos para Oracle Database.

Esto permite que un cliente compatible con MCP pueda interactuar con Oracle Database a través de SQLcl usando conexiones ya configuradas.

Según Oracle, este enfoque:

- permite interactuar con Oracle Database vía MCP
- usa conexiones preconfiguradas en SQLcl
- puede ejecutar consultas SQL, PL/SQL y comandos asociados
- funciona tanto en entornos on-prem como en nube

Esto es especialmente relevante para empresas con Oracle on premise, porque acerca un camino oficial para conectar agentes con bases Oracle sin depender solo de integraciones de terceros.

Referencia oficial:

- [Oracle SQLcl MCP Server](https://docs.oracle.com/en/database/oracle/sql-developer-vscode/25.3/sqdnx/sqlcl-mcp-server.html)

### 4.2 Oracle Autonomous AI Database MCP Server

Oracle también ofrece un MCP administrado para **Autonomous AI Database**.

En este caso, el MCP viene como una capacidad gestionada por Oracle y se integra con:

- identidad
- autorización
- auditoría
- gobierno

La ventaja de este enfoque es que reduce la necesidad de operar tu propia infraestructura MCP para esa base administrada.

### 4.3 ¿Tiene costo usar el MCP de Oracle?

En la práctica, el camino más claro hoy es el de **SQLcl MCP Server**.

Oracle describe **SQLcl** como una herramienta **free** o **no-cost** dentro de su ecosistema.

Eso sugiere que:

- usar SQLcl y su capacidad MCP no requiere una licencia separada adicional como producto independiente
- no es exactamente igual a un proyecto open source comunitario como el MCP de MySQL que usamos en este curso
- el soporte oficial está ligado al ecosistema Oracle y a la relación de soporte/mantenimiento de Oracle Database

En otras palabras:

- desde el punto de vista práctico, **no parece tener un costo extra separado**
- desde el punto de vista empresarial, sigue estando dentro del mundo Oracle, su soporte y sus políticas

### Diferencia práctica frente al MCP de MySQL

El MCP de MySQL del curso:

- es un paquete npm abierto y simple
- se instala como una integración externa
- no depende de un stack licenciado como Oracle

El enfoque Oracle con SQLcl:

- es una opción oficial del ecosistema Oracle
- se apoya en una herramienta oficial de Oracle Database
- puede ser más adecuado para empresas que ya operan con Oracle on premise y soporte corporativo

### Referencias oficiales sobre costo y soporte

- [Oracle SQLcl](https://www.oracle.com/database/sqldeveloper/technologies/sqlcl/)
- [Downloading and Installing SQLcl](https://docs.oracle.com/en/database/oracle/application-express/22.1/aeadm/downloading-and-installing-sqlcl.html)
- [Oracle SQLcl Support Policy](https://www.oracle.com/tools/sqlcl/support.html)

### 4.4 Qué implica esto para una empresa on premise

Si una empresa trabaja con Oracle on premise, el camino más relevante es estudiar:

- **SQLcl MCP Server**

porque permite conectar agentes a bases Oracle existentes manteniendo el control de conexiones, credenciales y políticas desde el entorno corporativo.

Pero incluso con una solución oficial, sigue siendo fundamental aplicar:

- mínimo privilegio
- cuentas separadas
- réplicas o vistas curadas
- auditoría
- evitar acceso libre a producción

### 4.5 Idea clave

Que exista un MCP oficial para Oracle **no significa** que deba darse acceso amplio a la base. Significa que ahora hay un mecanismo más estándar para exponer herramientas de Oracle a clientes MCP, y por lo tanto el diseño de seguridad y gobierno sigue siendo crítico.

## 5. Qué precauciones hay que tomar

Cuando se conecta un agente a una base de datos, hay que cuidar:

- no exponer credenciales en archivos compartidos
- evitar guardar contraseñas en el repositorio
- limitar operaciones de escritura
- validar las consultas ejecutadas
- distinguir entre entorno de práctica y producción

## 6. Qué es un catálogo de datos

Un catálogo de datos es un inventario estructurado de los activos de datos.

A nivel básico, para cada tabla puede incluir:

- nombre de la tabla
- propósito
- columnas
- tipos de datos
- claves aparentes
- observaciones de calidad o uso

## 7. Qué puede aportar la IA en este proceso

Con ayuda del MCP, el agente puede:

- leer el esquema real
- resumir estructuras
- proponer descripciones
- detectar patrones comunes
- redactar un catálogo inicial mucho más rápido

## 8. Qué sigue siendo responsabilidad del estudiante

Aunque el agente ayude a documentar, el estudiante debe validar:

- si las descripciones tienen sentido
- si las tablas realmente significan lo que el agente interpreta
- si hay columnas ambiguas
- si el catálogo es útil para otros usuarios

## 9. Qué se aprende realmente en este módulo

Más allá de conectar MySQL, este módulo enseña:

- cómo integrar agentes con recursos externos
- cómo usar IA sobre una fuente real de datos
- cómo convertir exploración técnica en documentación útil

## 10. Ideas clave para llevarse

- un agente conectado a datos reales puede ser mucho más útil
- MCP permite pasar de conversación a integración operativa
- la documentación automática ahorra tiempo, pero siempre requiere validación humana
- Oracle ya tiene caminos oficiales para MCP, pero la seguridad sigue dependiendo del diseño de acceso y gobierno
