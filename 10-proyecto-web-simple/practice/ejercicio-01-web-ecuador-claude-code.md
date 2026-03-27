# Ejercicio 01 - Construir una web turística de Ecuador con Claude Code

## Objetivo

Construir desde cero una página web simple que promocione turísticamente al Ecuador usando Claude Code, ya sea por consola o desde el plugin de Visual Studio Code.

## Duración sugerida

40 a 50 minutos

## Herramienta

Puedes hacer este ejercicio con:

- Claude Code en consola
- Claude Code desde Visual Studio Code

## Parte A - Crear la carpeta del proyecto

Crea una carpeta vacía para el proyecto.

### Linux / macOS

```bash
mkdir ecuador-turismo-web
cd ecuador-turismo-web
```

### Windows PowerShell

```powershell
mkdir ecuador-turismo-web
cd ecuador-turismo-web
```

## Parte B - Abrir Claude Code

Según la modalidad elegida:

- si trabajas en terminal, ejecuta `claude`
- si trabajas en VS Code, abre la carpeta y usa la integración de Claude Code

## Parte C - Pedir una primera versión del sitio

Usa este prompt base:

```markdown
# Rol
Actúa como un desarrollador frontend senior.

# Objetivo
Construye una página web estática desde cero que promocione turísticamente al Ecuador.

# Requisitos mínimos
- Crea los archivos necesarios del proyecto.
- Incluye un título principal atractivo.
- Incluye secciones sobre destinos, gastronomía, cultura y naturaleza.
- Haz que la página se vea moderna y agradable.
- Usa HTML, CSS y JavaScript simple si hace falta.

# Restricciones
- No uses frameworks.
- Mantén el proyecto simple y fácil de abrir localmente.
- Todo debe quedar listo para abrir en navegador.

# Formato de trabajo
1. Primero dime qué archivos vas a crear.
2. Luego crea la primera versión.
3. Finalmente indícame cómo abrir la página.
```

## Parte D - Enriquecer el prompt

Después de la primera versión, mejora el prompt para hacer la página más llamativa y funcional.

Ideas de mejora:

- agregar navegación superior
- incluir una sección hero con llamada a la acción
- usar una paleta inspirada en Ecuador
- mejorar el diseño para móvil
- agregar tarjetas de destinos
- hacer la experiencia más visual
- incluir una sección final de “por qué visitar Ecuador”

## Parte E - Abrir la web en el navegador

Una vez creados los archivos:

- abre `index.html` directamente

o, si hace falta:

### Linux / macOS

```bash
python -m http.server 8000
```

### Windows PowerShell

```powershell
python -m http.server 8000
```

Luego visita:

```text
http://localhost:8000
```

## Parte F - Validación final

Revisa:

- si la página abre correctamente
- si el contenido es coherente
- si el diseño resulta atractivo
- si la navegación o estructura funciona
- si el resultado final mejoró respecto a la primera versión

## Entregable

El estudiante debe entregar:

1. el prompt base
2. la versión enriquecida del prompt
3. evidencia de la web abierta en el navegador
4. una reflexión breve sobre cómo mejoró el resultado al iterar con Claude Code

## Conclusión esperada

El estudiante debería observar que Claude Code puede construir un proyecto web pequeño desde cero, pero que la calidad visual y funcional mejora mucho cuando el estudiante refina bien el prompt y revisa el resultado en navegador.
