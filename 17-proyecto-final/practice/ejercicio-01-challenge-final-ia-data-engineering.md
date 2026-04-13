# Ejercicio 01 - Challenge final de IA Data Engineering

## Objetivo

Desarrollar un proyecto final completo que se conecte a una base de datos real, construya un dataset analítico llamado `comercial`, genere un dashboard HTML y publique toda la solución en un repositorio público de GitHub.

## Base de datos del ejercicio

Conéctate usando estas credenciales:

- `host`: `www.bigdataybi.com`
- `port`: `3306`
- `database`: `fake`
- `user`: `curso`
- `password`: proporcionado por el instructor

## Tablas de origen

Debes ingerir estas tablas:

- `customers`
- `products`
- `sales`
- `shops`

## Resultado principal esperado

Debes construir una única estructura de datos llamada:

- `comercial`

Y almacenarla en:

- formato `parquet`

## Dashboard requerido

Con los datos del dataset `comercial`, debes construir una página HTML con al menos estos 4 componentes:

1. KPI del total vendido
2. tendencia diaria de las ventas mostrando los últimos 30 días
3. gráfico de pastel de la participación de las ventas por tienda (`shop`)
4. gráfico de barras de las ventas por producto

## Repositorio final

Debes crear un repositorio público en tu cuenta personal de GitHub con este nombre exacto:

- `ia-challenge`

## Entrega formal

Al finalizar, debes enviar un correo con el enlace del repositorio a:

- `agustin.martinez@bigdataybi.com`

## Duración sugerida

90 a 120 minutos

## Parte A - Crear el repositorio final

En tu cuenta personal de GitHub:

1. crea un repositorio nuevo llamado `ia-challenge`
2. asegúrate de que sea **público**
3. clónalo en tu máquina local

## Parte B - Pedir a la IA una estructura inicial del proyecto

Antes de escribir código, pide a la IA que te sugiera una estructura de carpetas y archivos.

### Prompt base sugerido

```markdown
# Rol
Actúa como un ingeniero de datos senior.

# Objetivo
Sugiere una estructura de carpetas y archivos para un proyecto final llamado `ia-challenge`.

# Contexto
El proyecto debe:
- conectarse a MySQL
- ingerir `customers`, `products`, `sales` y `shops`
- construir un dataset `comercial`
- guardar el resultado en Parquet
- generar un dashboard HTML con 4 gráficos
- incluir archivos de contexto de IA

# Formato de salida
1. árbol de carpetas sugerido
2. propósito de cada archivo
3. orden recomendado de implementación
```

## Parte C - Ingerir las tablas fuente

Construye el código de conexión e ingesta de estas tablas:

- `customers`
- `products`
- `sales`
- `shops`

Puedes hacerlo con Python o PySpark, siempre que el flujo quede claro y reproducible.

### Requisitos mínimos

- separar conexión y extracción en archivos claros
- no dejar la contraseña hardcodeada en el repositorio final
- dejar trazabilidad del origen de cada tabla

## Parte D - Construir el dataset `comercial`

Con las 4 tablas ingeridas, genera una sola estructura analítica llamada `comercial`.

### Qué debe resolver esta parte

- joins correctos entre tablas
- columnas útiles para análisis comercial
- nombres de columnas claros
- consistencia en tipos de datos

### Recomendación

Pide a la IA que explique primero el modelo lógico antes de generar el código final.

## Parte E - Guardar en formato Parquet

El resultado del dataset `comercial` debe quedar almacenado en formato:

- `parquet`

Define una ruta clara dentro del proyecto para el archivo o conjunto de archivos resultantes.

## Parte F - Construir el dashboard HTML

Usa el dataset `comercial` para generar un dashboard en HTML.

El dashboard debe incluir:

1. KPI del total vendido
2. tendencia diaria de ventas de los últimos 30 días
3. participación de ventas por tienda en gráfico de pastel
4. ventas por producto en gráfico de barras

### Recomendación de trabajo con IA

Pide primero:

- estructura del HTML
- librerías sugeridas para gráficos
- organización de datos requerida

Después pide:

- implementación final de `index.html`

## Parte G - Archivos mínimos del repositorio

El repositorio debe contener al menos:

- dashboard en formato HTML
- código fuente de ingesta y transformaciones
- `README.md`
- archivos de contexto de IA según las herramientas usadas

Los archivos de contexto pueden incluir, según corresponda:

- `CLAUDE.md`
- `OPENAI.md`
- `AGENTS.md`

## Parte H - README obligatorio

El `README.md` debe explicar:

- objetivo del proyecto
- proceso realizado
- tablas usadas
- cómo se construyó `comercial`
- dónde se encuentra el dashboard
- cuál es el archivo `index.html`
- cómo ejecutar o revisar el proyecto

## Parte I - Prompt sugerido para documentación final

```markdown
# Rol
Actúa como un documentador técnico.

# Objetivo
Ayúdame a redactar el README final del proyecto `ia-challenge`.

# Requisitos
- explica claramente el flujo realizado
- menciona las tablas de origen
- explica el dataset `comercial`
- indica dónde está el dashboard `index.html`
- redacta en español claro y técnico
```

## Parte J - Publicar en GitHub

Una vez listo el proyecto:

1. sube el código a tu repositorio `ia-challenge`
2. valida que el repositorio sea público
3. verifica que el `README.md` se vea correctamente

## Parte K - Enviar el enlace por correo

Envía un correo a:

- `agustin.martinez@bigdataybi.com`

Incluyendo:

- tu nombre
- el enlace al repositorio público
- una breve nota indicando que corresponde al challenge final

## Entregable

El estudiante debe entregar:

1. enlace público al repositorio `ia-challenge`
2. dataset `comercial` en Parquet dentro del proyecto o claramente referenciado
3. dashboard HTML funcionando
4. `README.md` claro
5. archivos de contexto de IA usados
6. evidencia de envío del correo

## Criterio de éxito

El ejercicio está completo si el estudiante logra:

- conectarse correctamente a la base `fake`
- integrar `customers`, `products`, `sales` y `shops`
- construir el dataset `comercial`
- generar el dashboard con los 4 gráficos pedidos
- publicar el repositorio `ia-challenge`
- dejar una entrega clara, pública y bien documentada
