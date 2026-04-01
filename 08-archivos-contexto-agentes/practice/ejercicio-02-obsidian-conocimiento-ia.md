# Ejercicio 02 - Instalar Obsidian para gestionar conocimiento generado por IA

## Objetivo

Instalar y configurar **Obsidian** como una base personal de conocimiento para guardar ideas, prompts, decisiones, errores frecuentes y aprendizajes generados durante el trabajo con IA.

La idea de este ejercicio es complementar el contexto del proyecto:

- `CLAUDE.md` sirve para darle contexto operativo al agente dentro de un repositorio
- `MEMORY.md` sirve para guardar memoria útil del proyecto
- **Obsidian** sirve para construir una base de conocimiento más amplia y personal, reutilizable entre distintos proyectos

## Escenario del laboratorio

Durante el curso vas a trabajar con chats, agentes, prompts, repositorios, errores de ejecución y decisiones técnicas. Si todo eso queda disperso en conversaciones, se pierde valor. Obsidian te ayuda a convertir ese conocimiento en notas conectadas entre sí.

En este laboratorio vas a:

1. instalar Obsidian
2. crear un vault para el curso
3. configurar el `obsidian-cli`
4. crear tus primeras notas desde la terminal
5. organizar conocimiento generado por IA

## Requisitos previos

- conexión a internet
- Obsidian Desktop
- terminal disponible
- Node.js instalado para verificar entorno con `node --version`

## Parte A - Instalar Obsidian

### macOS

1. Ve a [Obsidian Download](https://obsidian.md/download)
2. Descarga el archivo `.dmg`
3. Ábrelo y arrastra Obsidian a **Applications**
4. Ejecuta Obsidian

### Windows

1. Ve a [Obsidian Download](https://obsidian.md/download)
2. Descarga el instalador `.exe`
3. Ejecuta el instalador
4. Abre Obsidian cuando termine

## Parte B - Crear el vault del curso

Un **vault** es la carpeta raíz donde Obsidian almacena todas tus notas.

Crea un vault con este nombre:

`IA-DataEngineering-Knowledge`

Ubicación sugerida:

- macOS: `~/Documents/IA-DataEngineering-Knowledge`
- Windows: `C:\Users\TU_USUARIO\Documents\IA-DataEngineering-Knowledge`

## Parte C - Instalar el plugin Local REST API

Este plugin permite que el CLI se comunique con Obsidian.

1. En Obsidian abre **Settings**
2. Entra en **Community plugins**
3. Desactiva **Restricted mode**
4. Haz clic en **Browse**
5. Busca `Local REST API`
6. Instálalo
7. Actívalo

## Parte D - Configurar el CLI de Obsidian

### macOS

```bash
ls /Applications/Obsidian.app/Contents/MacOS/obsidian-cli
echo 'alias obsidian="/Applications/Obsidian.app/Contents/MacOS/obsidian-cli"' >> ~/.zshrc
source ~/.zshrc
obsidian vaults
```

### Windows PowerShell

```powershell
$cliPath = "$env:LOCALAPPDATA\Obsidian\obsidian-cli.exe"
Test-Path $cliPath

[Environment]::SetEnvironmentVariable(
  "PATH",
  "$env:PATH;$env:LOCALAPPDATA\Obsidian",
  "User"
)

$env:PATH += ";$env:LOCALAPPDATA\Obsidian"
Set-Alias -Name obsidian -Value obsidian-cli
obsidian-cli vaults
```

## Parte E - Verificar conexión con el vault

Con Obsidian abierto y el plugin activo, valida que el vault aparezca en consola.

### macOS

```bash
obsidian vaults
```

### Windows

```powershell
obsidian-cli vaults
```

Debe aparecer:

```text
IA-DataEngineering-Knowledge
```

## Parte F - Crear las primeras notas del curso

Ahora vas a crear una estructura inicial para guardar conocimiento generado por IA.

Notas sugeridas:

- `00-Inbox`
- `Prompts utiles`
- `Errores frecuentes`
- `Aprendizajes del curso`
- `Ideas de automatizacion`

### macOS

```bash
obsidian create vault=IA-DataEngineering-Knowledge name="00-Inbox" \
  content="# 00-Inbox\n\nEspacio para capturar ideas rápidas, hallazgos y tareas.\n" \
  silent

obsidian create vault=IA-DataEngineering-Knowledge name="Prompts utiles" \
  content="# Prompts utiles\n\n## Plantillas\n\n- Prompt para analizar código\n- Prompt para depurar errores\n- Prompt para generar documentación\n" \
  silent

obsidian create vault=IA-DataEngineering-Knowledge name="Errores frecuentes" \
  content="# Errores frecuentes\n\n## Registro\n\n- Error:\n- Causa:\n- Solución:\n" \
  silent
```

### Windows PowerShell

```powershell
obsidian-cli create vault=IA-DataEngineering-Knowledge name="00-Inbox" `
  content="# 00-Inbox`n`nEspacio para capturar ideas rápidas, hallazgos y tareas.`n" `
  silent

obsidian-cli create vault=IA-DataEngineering-Knowledge name="Prompts utiles" `
  content="# Prompts utiles`n`n## Plantillas`n`n- Prompt para analizar código`n- Prompt para depurar errores`n- Prompt para generar documentación`n" `
  silent

obsidian-cli create vault=IA-DataEngineering-Knowledge name="Errores frecuentes" `
  content="# Errores frecuentes`n`n## Registro`n`n- Error:`n- Causa:`n- Solución:`n" `
  silent
```

## Parte G - Crear una nota específica sobre IA

Crea una nota llamada `Buenas practicas con IA` con ideas como estas:

- escribir prompts en Markdown
- dar contexto suficiente
- incluir ejemplos de entrada y salida
- validar resultados antes de usar el código
- registrar decisiones importantes

### macOS

```bash
obsidian create vault=IA-DataEngineering-Knowledge name="Buenas practicas con IA" \
  content="# Buenas practicas con IA\n\n- Escribir prompts en Markdown\n- Dar contexto del proyecto\n- Incluir ejemplos\n- Validar resultados del modelo\n- Registrar aprendizajes reutilizables\n" \
  silent
```

### Windows PowerShell

```powershell
obsidian-cli create vault=IA-DataEngineering-Knowledge name="Buenas practicas con IA" `
  content="# Buenas practicas con IA`n`n- Escribir prompts en Markdown`n- Dar contexto del proyecto`n- Incluir ejemplos`n- Validar resultados del modelo`n- Registrar aprendizajes reutilizables`n" `
  silent
```

## Parte H - Buscar y leer notas desde la terminal

### macOS

```bash
obsidian files vault=IA-DataEngineering-Knowledge
obsidian read vault=IA-DataEngineering-Knowledge file="Buenas practicas con IA"
obsidian search vault=IA-DataEngineering-Knowledge query="prompt"
```

### Windows PowerShell

```powershell
obsidian-cli files vault=IA-DataEngineering-Knowledge
obsidian-cli read vault=IA-DataEngineering-Knowledge file="Buenas practicas con IA"
obsidian-cli search vault=IA-DataEngineering-Knowledge query="prompt"
```

## Parte I - Actividad aplicada al curso

Usa Obsidian para registrar conocimiento generado por IA durante una tarea real del curso.

Puedes elegir una de estas opciones:

1. documentar un prompt útil que hayas probado en ChatGPT, Claude o Gemini
2. registrar un error técnico que te haya ocurrido y cómo lo resolviste
3. guardar ideas para mejorar una práctica o proyecto del curso
4. resumir aprendizajes obtenidos al usar `CLAUDE.md` y `MEMORY.md`

La nota debe incluir como mínimo:

- título claro
- fecha
- contexto
- hallazgo o problema
- respuesta o solución propuesta por la IA
- validación humana final

## Comandos útiles

| Comando | Descripción |
| --- | --- |
| `obsidian vaults` | Lista los vaults abiertos |
| `obsidian files` | Lista las notas del vault |
| `obsidian create` | Crea una nueva nota |
| `obsidian read` | Lee una nota |
| `obsidian append` | Agrega contenido a una nota existente |
| `obsidian search` | Busca texto dentro del vault |
| `obsidian tags` | Lista los tags detectados |

En Windows puedes usar los mismos comandos con `obsidian-cli`.

## Reflexión final

Responde estas preguntas:

1. ¿Qué tipo de conocimiento generado por IA conviene guardar en Obsidian y no solo en un chat?
2. ¿Cómo se complementa Obsidian con `CLAUDE.md` y `MEMORY.md`?
3. ¿Qué ventaja tiene convertir respuestas de IA en notas reutilizables?

## Entregable

Debes presentar:

- captura de pantalla del vault creado en Obsidian
- evidencia de que el CLI reconoce el vault
- al menos 4 notas creadas
- una nota aplicada a una experiencia real del curso

## Criterio de éxito

El ejercicio está completo si el estudiante logra:

- instalar Obsidian correctamente
- crear y abrir un vault funcional
- configurar el CLI
- crear y consultar notas desde terminal
- usar Obsidian para organizar conocimiento útil generado por IA
