# Ejercicio 02 - Ejecutar el pipeline Multihope con notebooks

## Objetivo

Ejecutar en orden los notebooks del proyecto Multihope para correr el pipeline completo RAW → BRONZE → SILVER → GOLD sobre datos reales.

## Duración sugerida

30 a 40 minutos

## Requisitos

- haber completado el Ejercicio 01 (fork clonado y configurado)
- tener el entorno virtual activado con las dependencias instaladas
- tener el archivo `.env` configurado con las credenciales de la base de datos

---

## Paso 1 - Preparar el entorno virtual

Desde la raíz del proyecto:

```bash
python -m venv .venv
source .venv/bin/activate        # macOS / Linux
# .venv\Scripts\activate         # Windows

pip install -r requirements.txt
```

---

## Paso 2 - Configurar las credenciales

```bash
cp .env.example .env
```

Abre `.env` y completa los valores con las credenciales que te entregó el instructor:

```
DB_USER=...
DB_PASSWORD=...
```

---

## Paso 3 - Registrar el entorno virtual como kernel de Jupyter

```bash
python -m ipykernel install --user --name=multihope --display-name "Python (multihope)"
```

Esto permite que los notebooks usen el entorno virtual donde instalaste las dependencias.

---

## Paso 4 - Abrir Jupyter

```bash
jupyter notebook notebooks/
```

---

## Paso 5 - Ejecutar `00_precheck.ipynb`

Abre el notebook `00_precheck.ipynb` y ejecuta todas las celdas en orden.

Este notebook valida que el entorno está listo antes de correr el pipeline. Verifica:

- versión de Python
- librerías instaladas con sus versiones mínimas
- variables de entorno (`DB_USER`, `DB_PASSWORD`)
- archivos de configuración (`database.yml`, `spark_config.yml`)
- Java disponible en el PATH (requerido por PySpark)
- que se puede crear y cerrar una SparkSession

**Criterio de éxito:** todas las celdas muestran ✅. Si alguna muestra ⚠️ o ❌ resuelve el problema antes de continuar.

---

## Paso 6 - Ejecutar `01_raw_to_bronze_customers.ipynb`

Este notebook se conecta a la base de datos MySQL y guarda los datos de la tabla `customers` en formato Parquet en la capa Bronze (`data/bronze/customers/`).

Ejecuta todas las celdas en orden y verifica:

- que la conexión JDBC a la base de datos fue exitosa
- el schema del DataFrame Bronze que se imprime
- el total de registros ingresados

---

## Paso 7 - Ejecutar `02_bronze_to_silver_customers.ipynb`

Este notebook lee la capa Bronze, aplica validaciones de calidad con **DQX** y guarda los datos limpios en la capa Silver (`data/silver/customers/`).

Ejecuta todas las celdas en orden y verifica:

- cuántos registros pasaron las validaciones DQX (válidos)
- si se generó una capa de cuarentena (`data/quarantine/customers/`) con registros que fallaron
- el schema del DataFrame Silver
- que no hay nulos en la columna `customer_id`

---

## Paso 8 - Ejecutar `03_silver_to_gold_customers.ipynb`

Este notebook lee la capa Silver y genera un resumen agregado por estado en la capa Gold (`data/gold/customers_summary/`).

Ejecuta todas las celdas en orden y verifica:

- el schema del DataFrame Gold
- la tabla de resumen de customers por estado
- el total de filas en Gold

---

## Paso 9 - Confirmar las capas generadas

Verifica que se crearon los directorios de datos:

```bash
ls data/bronze/customers/
ls data/silver/customers/
ls data/gold/customers_summary/
```

Deberías ver archivos `.parquet` en cada carpeta.

---

## Preguntas de reflexión

- ¿Qué pasó en el paso de DQX? ¿Hubo registros en cuarentena?
- ¿Qué diferencia hay entre los datos en Bronze y los datos en Silver?
- ¿Por qué el notebook `00_precheck` es importante antes de ejecutar el pipeline?
- ¿Qué error obtendrías si ejecutaras el notebook 02 sin haber ejecutado el 01 primero?

---

## Entregable

El estudiante debe presentar:

1. captura o copia del output final de `00_precheck.ipynb` (resumen con ✅)
2. total de registros en cada capa: Bronze, Silver y Gold
3. si hubo registros en cuarentena: cuántos y por qué regla DQX fallaron
4. respuesta breve a las preguntas de reflexión
