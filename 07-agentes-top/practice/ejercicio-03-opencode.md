# Ejercicio 03 - Instalar OpenCode y autenticar con OpenAI

## Objetivo

Instalar OpenCode y configurarlo usando una API key de OpenAI.

## Duración sugerida

20 minutos

## Referencia pública

- OpenCode docs: [opencode.ai/docs](https://opencode.ai/docs)
- OpenCode providers: [opencode.ai/docs/providers](https://opencode.ai/docs/providers)

## Requisitos

- Node.js o método de instalación requerido por la herramienta
- API key de OpenAI

## Paso 1 - Preparar la API key

Usa una API key válida de OpenAI.

## Paso 2 - Instalar OpenCode

### Con npm

```bash
npm install -g opencode-ai
```

Luego verifica:

```bash
opencode --version
```

## Paso 3 - Configurar autenticación

OpenCode soporta autenticación interactiva por proveedor.

La forma más simple para este ejercicio es iniciar OpenCode y luego usar el flujo de login:

```bash
opencode auth login
```

Dentro del flujo:

1. selecciona `OpenAI`
2. selecciona `Manually enter API Key`
3. pega tu API key

Si el instructor prefiere usar variable de entorno, también puedes cargar la API key en la sesión:

### Windows PowerShell

```powershell
$env:OPENAI_API_KEY="pega_aqui_tu_api_key"
```

### macOS / Linux / zsh / bash

```bash
export OPENAI_API_KEY="pega_aqui_tu_api_key"
```

## Paso 4 - Iniciar OpenCode

Ejecuta la CLI y confirma que la herramienta inicia correctamente:

```bash
opencode
```

## Paso 5 - Prompt de prueba

Prueba algo como:

```text
Revisa este repositorio y dime tres tareas técnicas que un agente podría hacer aquí.
```

## Entregable

El estudiante debe mostrar:

1. evidencia de instalación
2. evidencia de autenticación con API key
3. evidencia de inicio correcto de la herramienta
4. una comparación breve con Codex o Gemini CLI
