# Ejercicio 01 - Refactorización y debugging con Claude Code

## Objetivo

Practicar un flujo real de desarrollo asistido con Claude Code sobre el repositorio `multihope`: importar el proyecto a GitHub personal, clonarlo localmente, analizarlo, pedir mejoras y usar el agente para debugging.

## Duración sugerida

35 a 45 minutos

## Repositorio base

- Original: [amartinez2b/multihope](https://github.com/amartinez2b/multihope)

## Parte A - Importar el repositorio a tu cuenta personal de GitHub

En este ejercicio el estudiante **no debe hacer fork**. Debe **importar** el repositorio a su cuenta personal.

Pasos sugeridos:

1. entra a GitHub
2. usa la opción `Import repository`
3. como repositorio de origen usa:

```text
https://github.com/amartinez2b/multihope.git
```

4. crea una copia nueva en tu cuenta personal

## Parte B - Clonar el repositorio desde tu cuenta personal

Una vez importado, clónalo desde tu propia cuenta:

```bash
git clone https://github.com/TU-USUARIO/multihope.git
cd multihope
```

## Parte C - Abrir Claude Code en el proyecto local

Desde la carpeta del proyecto ejecuta:

```bash
claude
```

Ahora todo el ejercicio se realizará dentro de este repositorio local usando Claude Code.

## Parte D - Pedir análisis inicial

Abre Claude Code dentro del proyecto y pide algo como:

```markdown
# Rol
Actúa como un ingeniero de datos senior.

# Objetivo
Analiza este proyecto y dime qué archivo debería revisar primero para entender la lógica principal.

# Formato de salida
- archivo recomendado
- motivo
- riesgos o dudas iniciales
```

## Parte E - Pedir una mejora o refactor

Después selecciona un archivo pequeño y prueba:

```markdown
# Objetivo
Revisa este archivo y propón una refactorización pequeña que mejore legibilidad o mantenibilidad.

# Restricciones
- No cambies el comportamiento esperado.
- Explica primero qué cambiarías antes de editar.

# Formato de salida
1. diagnóstico breve
2. propuesta de cambio
3. advertencias
```

## Parte F - Probar debugging con un error real

En este caso, el estudiante debe trabajar con errores reales del proyecto `multihope`, especialmente si aparecen al revisar notebooks, scripts o rutas de datos.

Luego pide:

```markdown
# Objetivo
Ayúdame a entender este error y proponer una corrección.

# Error
<pega aquí el traceback o mensaje>

# Contexto
<explica brevemente qué estabas ejecutando>

# Formato de salida
1. causa probable
2. evidencia
3. posible corrección
4. validación posterior
```

## Parte G - Validación humana

Revisa:

- si la propuesta del agente tiene sentido
- si cambió algo que no debía
- si la corrección realmente resuelve el problema
- si harías ese cambio en producción o no

## Entregable

El estudiante debe entregar:

1. URL del repositorio importado en su cuenta personal
2. evidencia de clonación local
3. el prompt usado para el análisis inicial
4. la propuesta de refactorización
5. el prompt y respuesta sobre debugging
6. una reflexión breve sobre qué hizo bien Claude Code y qué tuvo que validar manualmente

## Conclusión esperada

El estudiante debería observar que Claude Code puede acelerar bastante el análisis, la refactorización y el debugging de un proyecto real como `multihope`, pero que la validación técnica y la decisión final siguen siendo responsabilidad del humano.
