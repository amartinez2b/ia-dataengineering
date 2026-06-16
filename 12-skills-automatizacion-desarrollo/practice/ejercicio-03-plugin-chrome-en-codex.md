# Ejercicio 03 - Instalar el plugin Chrome en Codex y resumir un sitio web

## Objetivo

Instalar el plugin `Chrome` en Codex, completar la configuración de la extensión de Chrome y usarlo en una tarea simple de navegación asistida sobre un sitio web real.

Aunque para páginas públicas sin login el navegador integrado de Codex suele ser suficiente, en este ejercicio usaremos `@chrome` de forma explícita para aprender cómo se instala y cómo se invoca un plugin en Codex.

## Duración sugerida

20 a 30 minutos

## Requisitos

Antes de comenzar, el estudiante debe contar con:

- Codex App funcionando en su equipo
- Google Chrome instalado
- conexión a internet
- permisos para instalar la extensión oficial de Codex en Chrome

## Referencias

- Plugin objetivo: `Chrome`
- Extensión requerida: [Codex Chrome Extension](https://chromewebstore.google.com/detail/codex/hehggadaopoacecdllhhajmbjkdcmajg)

## Idea clave

En Codex, un plugin amplía las capacidades del agente y puede habilitar flujos especializados.

En este caso, el plugin `Chrome` permite que Codex use el navegador Chrome cuando hace falta trabajar con contexto real del navegador, pestañas abiertas o sesiones autenticadas.

## Parte A - Abrir la sección de plugins en Codex

Abre Codex y entra a la sección:

- `Plugins`

Desde ahí podrás ver los plugins disponibles e instalarlos dentro de tu entorno.

## Parte B - Instalar el plugin `Chrome`

Dentro de `Plugins`:

1. busca el plugin `Chrome`
2. abre su detalle
3. selecciona `Add to Codex`
4. sigue el flujo de instalación que aparezca en pantalla

Durante ese flujo, Codex debería guiarte para:

- instalar la extensión `Codex Chrome Extension`
- aceptar los permisos que Chrome solicite
- conectar Codex con Chrome

## Parte C - Confirmar que la extensión quedó conectada

Abre Google Chrome y revisa la extensión de Codex.

La validación mínima es que la extensión muestre el estado:

- `Connected`

Si la extensión no aparece conectada, revisa:

- que estés usando el mismo perfil de Chrome donde instalaste la extensión
- que la extensión esté habilitada
- que el plugin `Chrome` siga activo dentro de Codex

## Parte D - Iniciar una nueva conversación en Codex

Después de terminar la instalación, crea un nuevo thread en Codex.

Esto ayuda a que el agente reconozca correctamente el plugin ya disponible y empiece la tarea con el flujo actualizado.

## Parte E - Usar el plugin con un prompt simple

Prueba el plugin con un prompt como este:

```markdown
Utiliza el plugin [@chrome](plugin://chrome@openai-bundled) y conéctate a la página web https://www.dulce-hogar.com y dame un resumen.
```

La idea es que Codex abra la página usando Chrome y entregue un resumen breve del sitio.

## Parte F - Mejorar el prompt para obtener un mejor resultado

Después de la primera prueba, mejora el prompt para pedir un resumen más útil y más estructurado.

### Prompt mejorado sugerido

```markdown
Utiliza el plugin [@chrome](plugin://chrome@openai-bundled) y abre la página https://www.dulce-hogar.com.

Haz una revisión solo de lectura de la página principal y dame un resumen en español que incluya:
- a qué se dedica el sitio
- qué productos o categorías se destacan
- cuál parece ser su propuesta de valor
- qué canales de contacto o atención se ven disponibles
- una observación breve sobre la experiencia de usuario del sitio

No llenes formularios ni intentes hacer compras.
```

## Parte G - Qué debería pasar durante el uso

Durante la ejecución es normal que Codex:

- pida permiso para usar el sitio `dulce-hogar.com`
- abra Chrome si no está abierto
- trabaje sobre una pestaña del navegador
- devuelva el resumen directamente en la conversación

## Parte H - Reflexión breve

Responde al final:

1. ¿Qué diferencia notaste entre usar una skill y usar un plugin?
2. ¿Qué ventaja ofrece `@chrome` frente a pedir solo un resumen genérico por texto?
3. ¿En qué tipo de tareas de datos o negocio podría servir este plugin?

## Entregable

El estudiante debe presentar:

1. evidencia de que el plugin `Chrome` fue agregado en Codex
2. evidencia de que la extensión de Chrome quedó en estado `Connected`
3. el prompt usado
4. el resumen generado por Codex
5. una reflexión breve sobre el uso del plugin

## Criterio de éxito

El ejercicio está completo si el estudiante logra:

- instalar correctamente el plugin `Chrome` en Codex
- dejar conectada la extensión de Chrome
- invocar el plugin usando `@chrome`
- obtener un resumen real del sitio web solicitado
