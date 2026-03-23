# Ejercicio 03 - Mejorar un prompt con OpenAI Chat

## Objetivo

Tomar un prompt simple, llevarlo a [OpenAI Chat](https://platform.openai.com/chat) y usar la propia herramienta para iterarlo y convertirlo en un prompt más claro, estructurado y útil.

## Duración sugerida

15 a 20 minutos

## Herramienta

- OpenAI Chat: [platform.openai.com/chat](https://platform.openai.com/chat)

## Escenario

Quieres pedir ayuda para generar código, pero comienzas con un prompt demasiado simple.

## Prompt inicial

Usa este prompt:

```text
Hazme un script para procesar órdenes.
```

## Paso 1 - Probar el prompt simple

Pega el prompt inicial en OpenAI Chat y observa:

- qué tan genérica es la respuesta
- cuántas suposiciones hace
- qué información falta
- si el formato de salida es útil o no

## Paso 2 - Pedir a la herramienta que mejore el prompt

Ahora escribe algo como esto:

````markdown
Quiero mejorar este prompt para obtener una mejor respuesta técnica.

Prompt original:

```text
Hazme un script para procesar órdenes.
```

Mejóralo para que:
- esté escrito en Markdown
- tenga rol, objetivo, contexto, restricciones y formato de salida
- esté orientado a ingeniería de datos
- pida código en Python
- reduzca ambigüedad
````

## Paso 3 - Revisar la propuesta mejorada

Analiza si el nuevo prompt:

- está mejor estructurado
- aclara el lenguaje y el objetivo
- incluye restricciones
- pide un formato de salida claro

## Paso 4 - Probar el prompt mejorado

Ejecuta el prompt mejorado y compara el resultado contra la respuesta del prompt original.

## Variante recomendada

Si quieres llevarlo un paso más allá, pide además:

```markdown
Mejora aún más el prompt anterior e incluye un ejemplo de salida esperada en JSON.
```

## Preguntas de reflexión

- ¿Qué cambió entre el prompt simple y el mejorado?
- ¿La segunda respuesta fue más útil?
- ¿Qué partes del prompt mejorado aportaron más valor?
- ¿Qué seguirías ajustando manualmente?

## Entregable

El estudiante debe entregar:

1. el prompt inicial
2. el prompt mejorado propuesto por OpenAI Chat
3. la respuesta del prompt inicial
4. la respuesta del prompt mejorado
5. una comparación breve entre ambas

## Conclusión esperada

El estudiante debería observar que una buena parte del trabajo con IA no es solo pedir una tarea, sino aprender a mejorar el prompt hasta que la instrucción sea suficientemente clara y técnica.
