# Teoría - Módulo 09

## 1. Claude Code como flujo de trabajo

Claude Code no es solo una interfaz para hacer preguntas. Puede convertirse en parte activa del flujo de desarrollo cuando lo usamos dentro de un repositorio real.

En la práctica, eso significa:

- pedir análisis
- pedir cambios
- revisar resultados
- volver a iterar
- validar antes de integrar

## 2. Cómo pedir tareas complejas

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

## 3. Claude Code para refactorización asistida

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

## 4. Claude Code para debugging

Una forma útil de usar Claude Code en debugging es pedir:

- causa probable del error
- análisis del traceback
- propuesta de corrección
- pasos de validación después del cambio

## 5. Flujo recomendado de debugging con Claude Code

1. reproducir el error
2. capturar mensaje exacto
3. compartir contexto y fragmento relevante
4. pedir hipótesis
5. validar la solución
6. volver a probar

## 6. Qué hace bueno a un flujo de trabajo con Claude Code

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

## 7. Qué no conviene hacer

- delegar cambios enormes sin revisar
- aceptar todo lo que propone el agente
- pedir refactors sin criterio de validación
- ignorar pruebas y errores posteriores

## 8. Buenas prácticas para clase

- pedir primero análisis antes de pedir edición
- trabajar sobre una rama o copia segura
- revisar cambios antes de aceptar
- usar Claude Code para acelerar, no para evitar pensar

## 9. Ideas clave para llevarse

- Claude Code ayuda mucho en tareas complejas si el prompt está bien armado
- la refactorización asistida necesita revisión humana
- el debugging con IA funciona mejor con errores reales y contexto concreto
- usar un agente bien no es delegar ciegamente, sino colaborar con control
