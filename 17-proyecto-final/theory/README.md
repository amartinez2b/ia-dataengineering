# Teoría - Módulo 17

## 1. Qué debe demostrar el proyecto final

El proyecto final debe demostrar que el estudiante puede construir una solución de datos completa con apoyo de IA.

Eso implica combinar:

- acceso a datos
- transformación
- modelado analítico
- visualización
- documentación
- publicación del resultado

## 2. Flujo general esperado

El flujo del reto tiene esta secuencia:

1. conectarse a la base de datos
2. ingerir tablas de negocio
3. consolidar una sola estructura analítica
4. guardar el resultado en Parquet
5. construir un dashboard HTML
6. documentar el trabajo
7. publicar el proyecto en GitHub

## 3. Qué tablas participan

Las tablas base del reto son:

- `customers`
- `products`
- `sales`
- `shops`

Estas tablas deben integrarse en una única estructura llamada:

- `comercial`

## 4. Qué debe tener el dataset final

El dataset `comercial` debe quedar orientado al análisis de ventas y permitir responder preguntas como:

- cuánto se vendió
- cómo evolucionan las ventas en el tiempo
- qué tiendas venden más
- qué productos venden más

## 5. Por qué se pide Parquet

Parquet es un formato muy adecuado para el reto porque:

- es eficiente para análisis
- se integra bien con Python y PySpark
- permite separar claramente la etapa de transformación de la etapa de visualización

## 6. Qué debe lograr el dashboard

El dashboard final debe convertir el dataset en una vista ejecutiva simple y útil.

No se busca una aplicación compleja, sino un entregable claro que permita visualizar:

- KPI de ventas
- tendencia diaria
- participación por tienda
- ventas por producto

## 7. Qué sigue siendo responsabilidad del estudiante

Aunque se use IA para acelerar el desarrollo, el estudiante debe validar:

- que los joins tengan sentido
- que el dataset final sea coherente
- que el dashboard muestre resultados correctos
- que el repositorio quede ordenado
- que la documentación sea entendible para otra persona

## 8. Qué se evalúa realmente

Más allá de producir un dashboard, este proyecto evalúa:

- capacidad de integrar varias etapas técnicas
- claridad para estructurar un repositorio
- capacidad de documentar el proceso
- uso responsable y útil de agentes o asistentes de IA

## 9. Ideas clave para llevarse

- un buen proyecto final une datos, código, contexto y presentación
- la IA ayuda a acelerar, pero no reemplaza validación
- un repositorio bien organizado es parte de la entrega
- publicar el resultado obliga a trabajar con mayor claridad y orden
