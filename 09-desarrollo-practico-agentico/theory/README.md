# Teoría - Módulo 09

## 1. Claude Code como flujo de trabajo

Claude Code no es solo una interfaz para hacer preguntas. Puede convertirse en parte activa del flujo de desarrollo cuando lo usamos dentro de un repositorio real.

En la práctica, eso significa:

- pedir análisis
- pedir cambios
- revisar resultados
- volver a iterar
- validar antes de integrar

## 2. Codex como flujo de trabajo

Codex también puede actuar como parte activa del flujo de desarrollo cuando trabaja dentro de un workspace real.

En la práctica, eso significa:

- explorar archivos del proyecto
- proponer o aplicar cambios
- ejecutar análisis o revisiones
- retomar sesiones anteriores
- iterar hasta cerrar una tarea concreta

## 3. Cómo pedir tareas complejas

Una tarea compleja no debería pedirse como una frase suelta.

Conviene incluir:

- objetivo
- contexto
- archivos o áreas involucradas
- restricciones
- criterio de éxito

Ejemplo débil:

```text
Arregla esto.
```

Ejemplo mejorado:

```markdown
# Objetivo
Corrige el error de ejecución del notebook principal.

# Contexto
El proyecto es de ingeniería de datos y depende de archivos CSV locales.

# Restricciones
- No cambies rutas sin explicar por qué.
- No borres celdas del notebook.

# Criterio de éxito
El notebook debe ejecutar sin error en el entorno actual.
```

Esto aplica tanto para Claude Code como para Codex.

## 4. Claude Code para refactorización asistida

Claude Code puede ayudar a:

- ordenar scripts
- mejorar nombres
- extraer funciones
- reducir duplicación
- proponer estructura más clara

Pero en una refactorización hay que tener cuidado:

- no cambiar comportamiento por accidente
- no romper compatibilidad
- revisar cuidadosamente diffs y pruebas

## 5. Codex para refactorización asistida

Codex puede ayudar a:

- reorganizar archivos o funciones
- limpiar código repetido
- proponer cambios acotados
- revisar diffs antes de integrar
- apoyar revisiones puntuales con `codex review`

Al igual que con Claude Code, una buena refactorización asistida requiere:

- alcance claro
- criterio de validación
- revisión humana del cambio

## 6. Claude Code para debugging

Una forma útil de usar Claude Code en debugging es pedir:

- causa probable del error
- análisis del traceback
- propuesta de corrección
- pasos de validación después del cambio

## 7. Codex para debugging

Con Codex también conviene trabajar a partir de errores reales y pedir:

- lectura del error
- hipótesis principales
- archivos posiblemente implicados
- corrección sugerida
- validación posterior

Además, Codex puede ser especialmente útil cuando el debugging exige navegar varios archivos o revisar cambios del repositorio junto con terminal.

## 8. Flujo recomendado de debugging con agentes

1. reproducir el error
2. capturar mensaje exacto
3. compartir contexto y fragmento relevante
4. pedir hipótesis
5. validar la solución
6. volver a probar

Este flujo aplica bien tanto a Claude Code como a Codex.

## 9. Qué hace bueno a un flujo de trabajo agentico

### Contexto claro

El agente rinde mejor si sabe:

- qué hace el proyecto
- qué archivo revisar
- qué restricción no debe romper

### Límites claros

Es mejor decir:

- qué puede cambiar
- qué no debe tocar

### Iteración corta

Pequeños pasos suelen funcionar mejor que una instrucción gigante y ambigua.

### Uso de herramientas concretas

En Claude Code o Codex conviene aprovechar bien la interfaz disponible:

- terminal
- editor o app visual
- diffs
- historial de cambios
- sesiones anteriores si el flujo lo permite

## 10. Qué no conviene hacer

- delegar cambios enormes sin revisar
- aceptar todo lo que propone el agente
- pedir refactors sin criterio de validación
- ignorar pruebas y errores posteriores

## 11. Buenas prácticas para clase

- pedir primero análisis antes de pedir edición
- trabajar sobre una rama o copia segura
- revisar cambios antes de aceptar
- usar Claude Code o Codex para acelerar, no para evitar pensar
- comparar qué se siente mejor en terminal y qué se siente mejor en interfaz visual

## 12. Ideas clave para llevarse

- Claude Code y Codex ayudan mucho en tareas complejas si el prompt está bien armado
- la refactorización asistida necesita revisión humana
- el debugging con IA funciona mejor con errores reales y contexto concreto
- usar un agente bien no es delegar ciegamente, sino colaborar con control
