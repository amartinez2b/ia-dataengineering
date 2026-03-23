# Ejercicio 02 - Instalar Gemini CLI y autenticar con Google AI Studio

## Objetivo

Crear una cuenta o acceso en Google AI Studio, generar una API key, instalar Gemini CLI y autenticar la herramienta.

## Duración sugerida

20 minutos

## Referencias oficiales

- API key Gemini: [ai.google.dev/gemini-api/docs/api-key](https://ai.google.dev/gemini-api/docs/api-key)
- Gemini CLI: [github.com/google-gemini/gemini-cli](https://github.com/google-gemini/gemini-cli)

## Paso 1 - Entrar a Google AI Studio

Abre:

- [Google AI Studio](https://aistudio.google.com/)

## Paso 2 - Generar una API key

Dentro de AI Studio:

1. entra con tu cuenta Google
2. busca la opción para crear API key
3. genera una clave nueva
4. guárdala de forma segura

## Paso 3 - Instalar Gemini CLI

### Opción con npm

```bash
npm install -g @google/gemini-cli
```

### Opción sin instalación global

```bash
npx https://github.com/google-gemini/gemini-cli
```

Luego verifica que quedó disponible:

```bash
gemini --version
```

## Paso 4 - Configurar autenticación

Carga la variable de entorno:

### Windows PowerShell

```powershell
$env:GEMINI_API_KEY="pega_aqui_tu_api_key"
```

### macOS / Linux / zsh / bash

```bash
export GEMINI_API_KEY="pega_aqui_tu_api_key"
```

## Paso 5 - Iniciar la CLI

Abre Gemini CLI y valida que arranca correctamente:

```bash
gemini
```

## Paso 6 - Prompt de prueba

Usa un prompt como:

```text
Analiza este proyecto y dime qué carpetas o archivos mirarías primero para entenderlo.
```

## Entregable

El estudiante debe mostrar:

1. evidencia de creación de API key en AI Studio
2. evidencia de instalación de Gemini CLI
3. evidencia de autenticación correcta
4. una breve impresión sobre la experiencia de uso
