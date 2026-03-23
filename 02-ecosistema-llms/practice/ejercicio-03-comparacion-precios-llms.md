# Ejercicio 03 - Comparación de precios de LLMs

## Objetivo

Comparar precios de distintos LLMs en una herramienta web pública y entender cómo cambia el costo según el modelo y el volumen de tokens.

## Duración sugerida

15 a 20 minutos

## Herramientas sugeridas

- WhatLLM Compare: [whatllm.org/compare](https://whatllm.org/compare)
- LLM Price Calculator: [llmprice.dev](https://llmprice.dev/)

## Opción A - Comparar modelos por precio y capacidad

En [WhatLLM Compare](https://whatllm.org/compare):

1. Abre la herramienta.
2. Selecciona entre 2 y 4 modelos conocidos.
3. Revisa la sección de precio, calidad y contexto.
4. Compara cuál parece más conveniente para un caso simple de data engineering.

### Modelos sugeridos para comparar

- GPT-4o mini
- GPT-4o
- Claude Sonnet
- Gemini Flash
- DeepSeek Chat

### Preguntas para responder

- ¿Cuál es el modelo más barato?
- ¿Cuál parece ofrecer mejor balance entre precio y calidad?
- ¿Qué modelo elegirías para un chatbot interno de soporte técnico?
- ¿Qué modelo elegirías para tareas más exigentes de análisis o coding?

## Opción B - Estimar costo de uso

En [LLM Price Calculator](https://llmprice.dev/):

1. Abre la calculadora.
2. Elige un modelo.
3. Ingresa una carga estimada, por ejemplo:
   - input tokens: `100000`
   - output tokens: `20000`
4. Repite con al menos 3 modelos distintos.
5. Compara el costo total estimado.

## Escenario de ejemplo

Supón que un equipo de ingeniería de datos quiere automatizar:

- explicación de scripts SQL
- documentación corta de pipelines
- ayuda para debugging inicial

La aplicación procesará por semana aproximadamente:

- `100000` tokens de entrada
- `20000` tokens de salida

Usa ese escenario para comparar modelos.

## Entregable

El estudiante debe entregar una tabla con estas columnas:

- modelo
- precio estimado
- contexto disponible
- observación
- decisión recomendada

## Conclusión esperada

El estudiante debería concluir que:

- no siempre conviene elegir el modelo más potente
- para muchas tareas simples un modelo pequeño o medio puede ser suficiente
- el costo debe evaluarse junto con calidad, contexto, velocidad y facilidad de integración
