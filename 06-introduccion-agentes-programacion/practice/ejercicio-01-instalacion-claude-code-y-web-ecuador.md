# Ejercicio 01 - Instalar Claude Code y crear una web turística de Ecuador

## Objetivo

Instalar Claude Code en Windows, configurarlo con autenticación por API key y usarlo como agente para construir una página web simple que promocione turísticamente al Ecuador.

## Duración sugerida

35 a 45 minutos

## Requisitos

Antes de comenzar, el estudiante debería tener:

- Windows con terminal PowerShell
- Node.js instalado
- una API key válida de Anthropic
- acceso a internet

## Referencias oficiales

- Claude Code quickstart: [docs.anthropic.com - Claude Code Quickstart](https://docs.anthropic.com/en/docs/claude-code/quickstart)

## Parte A - Crear la carpeta del proyecto en Windows

En PowerShell, crea una carpeta como esta:

```powershell
mkdir C:\Users\TU_USUARIO\Documents\ecuador-turismo-claude
cd C:\Users\TU_USUARIO\Documents\ecuador-turismo-claude
```

Puedes cambiar `TU_USUARIO` por tu usuario real de Windows.

## Parte B - Instalar Claude Code

### Opción recomendada con npm

Si ya tienes Node.js 18 o superior:

```powershell
npm install -g @anthropic-ai/claude-code
```

### Opción nativa para Windows PowerShell

También puedes usar la instalación oficial para PowerShell:

```powershell
irm https://claude.ai/install.ps1 | iex
```

## Parte C - Configurar autenticación con API key

En esta práctica **no se usará login por Claude.ai**, sino autenticación con API key.

En PowerShell configura la variable de entorno de la sesión:

```powershell
$env:ANTHROPIC_API_KEY="pega_aqui_tu_api_key"
```

Para verificar, puedes ejecutar:

```powershell
echo $env:ANTHROPIC_API_KEY
```

Si ves un valor cargado, la variable quedó disponible para esa sesión.

## Parte D - Iniciar Claude Code dentro de la carpeta

Desde la carpeta del proyecto ejecuta:

```powershell
claude
```

Claude Code debería abrir dentro del directorio actual y reconocer ese folder como el espacio de trabajo del ejercicio.

## Parte E - Pedir a Claude Code una primera versión de la página

Usa este prompt base:

```markdown
# Rol
Actúa como un desarrollador frontend senior.

# Objetivo
Construye una página web estática que promocione turísticamente al Ecuador.

# Requisitos mínimos
- Debe incluir un título principal atractivo.
- Debe incluir secciones sobre naturaleza, gastronomía, cultura y destinos destacados.
- Debe tener diseño llamativo.
- Debe funcionar como sitio estático simple con HTML, CSS y JavaScript si hace falta.

# Restricciones
- No uses frameworks.
- Crea todos los archivos necesarios dentro de esta carpeta.
- Usa texto e imágenes de apoyo mediante placeholders o referencias simples si es necesario.

# Formato de trabajo
1. Primero explícame brevemente qué archivos vas a crear.
2. Luego crea los archivos.
3. Al final indícame cómo abrir la página en el navegador.
```

## Parte F - Enriquecer el prompt

El estudiante **no debe quedarse solo con el prompt base**. Debe mejorarlo para que la página sea más funcional y llamativa.

Algunas ideas para enriquecerlo:

- pedir una paleta visual inspirada en Ecuador
- incluir navegación entre secciones
- agregar tarjetas de destinos
- incluir una sección de llamada a la acción
- mejorar tipografía y layout
- hacer el diseño responsive para desktop y móvil
- pedir animaciones suaves o transiciones
- incluir una sección final con razones para visitar Ecuador

Ejemplos de mejoras que el estudiante puede agregar:

- "Haz que la página tenga estilo visual moderno y turístico."
- "Incluye una sección hero con llamada a la acción."
- "Haz que la web se vea bien en celular."
- "Usa colores inspirados en biodiversidad, volcanes y costa."

## Parte G - Ejecutar y abrir la página

Una vez que Claude Code cree los archivos, abre la página en el navegador.

Si el proyecto genera un archivo `index.html`, puedes abrirlo directamente desde el Explorador de Windows o desde PowerShell.

También puedes usar un servidor simple si hace falta, por ejemplo:

```powershell
python -m http.server 8000
```

Luego abrir:

```text
http://localhost:8000
```

## Entregable

El estudiante debe entregar:

1. evidencia de que instaló Claude Code
2. evidencia de que configuró la API key en la sesión
3. el prompt base usado
4. la versión enriquecida del prompt
5. la página web abierta en el navegador
6. una reflexión breve: ¿qué mejoró cuando refinó el prompt?

## Conclusión esperada

El estudiante debería observar que un agente como Claude Code no solo responde preguntas: puede crear archivos, estructurar un proyecto y ejecutar una tarea de desarrollo completa dentro de una carpeta real. También debería notar que la calidad del resultado mejora bastante cuando el prompt se enriquece con más contexto, intención visual y requisitos funcionales.
