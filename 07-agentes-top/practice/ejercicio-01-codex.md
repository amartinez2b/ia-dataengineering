# Ejercicio 01 - Instalar Codex y autenticar con API key

## Objetivo

Instalar Codex CLI y configurarlo con autenticación basada en API key de OpenAI.

## Duración sugerida

20 minutos

## Referencia oficial

- Codex CLI repo: [github.com/openai/codex](https://github.com/openai/codex)
- GPT-5-Codex model docs: [developers.openai.com/api/docs/models/gpt-5-codex](https://developers.openai.com/api/docs/models/gpt-5-codex)

## Requisitos

- Node.js instalado
- cuenta de OpenAI con API key
- terminal disponible

## Paso 1 - Crear la API key

Desde OpenAI Platform:

1. entra al panel de OpenAI
2. crea una API key
3. cópiala y guárdala de forma segura

## Paso 2 - Instalar Codex

### Con npm

```bash
npm install -g @openai/codex
```

Después puedes verificar:

```bash
codex --version
```

## Paso 3 - Configurar autenticación

Carga la API key en la terminal como variable de entorno de la sesión:

### Windows PowerShell

```powershell
$env:OPENAI_API_KEY="pega_aqui_tu_api_key"
```

### macOS / Linux / zsh / bash

```bash
export OPENAI_API_KEY="pega_aqui_tu_api_key"
```

## Paso 4 - Verificar la herramienta

Inicia Codex desde terminal y confirma que la CLI arranca correctamente:

```bash
codex
```

## Paso 5 - Probar un prompt simple

Usa un prompt corto como:

```text
Explícame qué hace este proyecto y cómo podría ayudarme a modificarlo.
```

## Entregable

El estudiante debe mostrar:

1. evidencia de instalación
2. evidencia de autenticación con API key
3. evidencia de arranque correcto de la CLI
4. una breve impresión de la experiencia de uso
