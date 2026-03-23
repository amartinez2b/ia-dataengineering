# Ejercicio 02 - Visualización de ML y LLMs

## Objetivo

Usar herramientas visuales interactivas para comprender mejor cómo aprende un modelo simple y cómo se explica visualmente el funcionamiento de un LLM.

## Duración sugerida

15 a 20 minutos

## Herramientas sugeridas

- TensorFlow Playground: [playground.tensorflow.org](https://playground.tensorflow.org/?authuser=00&hl=es)
- LLM Visualization de Brendan Bycroft: [bbycroft.net/llm](https://bbycroft.net/llm)

## Opción A - Visualizar un modelo de machine learning

En TensorFlow Playground:

1. Abre la herramienta.
2. Cambia el dataset entre patrones simples.
3. Agrega o quita capas ocultas.
4. Observa cómo cambia la frontera de decisión.

Ejemplo:
- Dataset: en circulos (primer dataset)
- Features (Variables de entrada. Ejm: Predecir la venta Features: Edad, Ingreso ): 2
- Hidden Layers: 1
- Neuron: 1
- Neuron Out: 1

Luego:
- Dataset: en circulos (primer dataset)
- Features: 2
- Hidden Layers: 2
- Neuron: 4
- Neuron Out: 2

### Preguntas para responder

- ¿Qué cambia cuando agregas más neuronas o más capas?
- ¿Qué pasa si el modelo es demasiado simple?
- ¿Qué pasa si entrenas demasiado o con una configuración poco adecuada?

## Opción B - Visualizar el flujo de un LLM

En LLM Visualization:

1. Abre la visualización.
2. Recorre el paso a paso del procesamiento.
3. Identifica dónde entra el texto, dónde se transforma y cómo se genera la salida.

### Preguntas para responder

- ¿Qué partes del proceso te ayudaron a entender mejor un LLM?
- ¿Qué diferencia notas entre "entender" lenguaje y "predecir" el siguiente token?
- ¿Por qué esta idea importa al evaluar respuestas de ChatGPT?

## Sugerencia para el instructor

Si hay poco tiempo, usa:

- TensorFlow Playground para explicar ML de forma visual
- LLM Visualization para conectar esa intuición con modelos de lenguaje modernos

## Conclusión esperada

El estudiante debería salir con una intuición visual más fuerte:

- un modelo aprende ajustando parámetros
- más complejidad no siempre significa mejor resultado
- un LLM genera respuesta a partir de patrones y predicción secuencial
