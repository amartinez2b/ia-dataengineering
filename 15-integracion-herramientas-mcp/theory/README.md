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

## 4. Qué precauciones hay que tomar

Cuando se conecta un agente a una base de datos, hay que cuidar:

- no exponer credenciales en archivos compartidos
- evitar guardar contraseñas en el repositorio
- limitar operaciones de escritura
- validar las consultas ejecutadas
- distinguir entre entorno de práctica y producción

## 5. Qué es un catálogo de datos

Un catálogo de datos es un inventario estructurado de los activos de datos.

A nivel básico, para cada tabla puede incluir:

- nombre de la tabla
- propósito
- columnas
- tipos de datos
- claves aparentes
- observaciones de calidad o uso

## 6. Qué puede aportar la IA en este proceso

Con ayuda del MCP, el agente puede:

- leer el esquema real
- resumir estructuras
- proponer descripciones
- detectar patrones comunes
- redactar un catálogo inicial mucho más rápido

## 7. Qué sigue siendo responsabilidad del estudiante

Aunque el agente ayude a documentar, el estudiante debe validar:

- si las descripciones tienen sentido
- si las tablas realmente significan lo que el agente interpreta
- si hay columnas ambiguas
- si el catálogo es útil para otros usuarios

## 8. Qué se aprende realmente en este módulo

Más allá de conectar MySQL, este módulo enseña:

- cómo integrar agentes con recursos externos
- cómo usar IA sobre una fuente real de datos
- cómo convertir exploración técnica en documentación útil

## 9. Ideas clave para llevarse

- un agente conectado a datos reales puede ser mucho más útil
- MCP permite pasar de conversación a integración operativa
- la documentación automática ahorra tiempo, pero siempre requiere validación humana
