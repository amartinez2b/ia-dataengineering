# Teoría - Módulo 03

## 1. ¿Qué problema resuelve Git?

Git es un sistema de control de versiones. Su objetivo principal es registrar cambios en archivos a lo largo del tiempo para que podamos:

- saber qué cambió
- saber quién lo cambió
- volver atrás si algo sale mal
- trabajar en paralelo sin pisarnos

En proyectos de software e ingeniería de datos, esto es fundamental porque el código evoluciona constantemente.

## 2. Repositorio local y repositorio remoto

### Repositorio local

Es la copia del proyecto que vive en tu máquina. Allí haces cambios, pruebas y commits.

### Repositorio remoto

Es la copia alojada en una plataforma como GitHub. Sirve para compartir, respaldar y colaborar con otras personas.

Una forma simple de explicarlo:

- `local` es donde trabajas
- `remote` es donde sincronizas y compartes

## 3. Conceptos básicos de Git

### Working directory

Son los archivos tal como están ahora en tu carpeta del proyecto.

### Staging area

Es la zona donde decides qué cambios entrarán en el próximo commit.

### Commit

Es una fotografía con mensaje. No guarda solo archivos: guarda el estado del proyecto en un momento concreto.

### Branch

Una rama es una línea de trabajo independiente. Permite probar cambios sin afectar directamente la rama principal.

### Merge o Pull Request

Es la forma de integrar cambios revisados a una rama principal.

## 4. Flujo básico de trabajo

Flujo mínimo recomendado:

1. clonar el repositorio
2. crear una rama
3. hacer cambios
4. revisar con `git status`
5. agregar con `git add`
6. confirmar con `git commit`
7. subir con `git push`
8. abrir Pull Request en GitHub si aplica

## 5. GitHub como plataforma de colaboración

GitHub no es Git. GitHub es una plataforma construida alrededor de Git para facilitar:

- colaboración
- revisión de código
- issues
- pull requests
- documentación
- automatización

En cursos y equipos con IA, GitHub también actúa como punto central para:

- almacenar instrucciones del proyecto
- ver historial de cambios
- revisar qué generó la IA y qué corrigió el humano

## 6. ¿Por qué Git es todavía más importante cuando usamos IA?

Cuando se trabaja con asistentes o agentes de IA:

- se generan muchos cambios rápidamente
- a veces se aceptan sugerencias que no entendemos del todo
- es fácil introducir errores sin notarlo
- necesitamos comparar versiones y revertir cuando algo sale mal

Por eso Git se vuelve todavía más importante.

### Beneficios concretos al trabajar con IA

- permite probar cambios en ramas separadas
- facilita revisar lo generado por la IA antes de integrarlo
- ayuda a documentar decisiones con mensajes de commit
- da seguridad para experimentar sin miedo

## 7. Buenas prácticas para repositorios asistidos por IA

### 1. Mantener un README claro

El repositorio debe explicar:

- qué hace el proyecto
- cómo correrlo
- qué carpetas son importantes
- qué objetivo tiene

### 2. Versionar archivos de contexto útiles

Ejemplos:

- `README.md`
- `CLAUDE.md`
- `MEMORY.md`
- instrucciones del proyecto
- ejemplos de prompts útiles

### 3. Hacer commits pequeños y frecuentes

Es mejor:

- un commit pequeño con intención clara

que:

- un commit enorme con muchos cambios mezclados

### 4. No confiar ciegamente en lo que genera la IA

Todo cambio sugerido por IA debería revisarse antes de integrarse.

### 5. Usar ramas para experimentar

Si la IA va a proponer refactors, cambios masivos o pruebas arriesgadas, conviene hacerlo en una rama separada.

### 6. No subir secretos

Nunca deben subirse:

- API keys
- tokens
- contraseñas
- archivos `.env` con secretos reales

## 8. Comandos mínimos para empezar

```bash
git clone <url>
git status
git add .
git commit -m "mensaje"
git branch
git checkout -b nombre-rama
git push origin nombre-rama
```

## 9. Ideas clave para llevarse

- Git controla versiones; GitHub facilita colaborar.
- El repositorio local y el remoto no son lo mismo.
- Un commit debe tener intención clara.
- Las ramas permiten experimentar sin romper la base principal.
- Cuando usamos IA, Git es la red de seguridad del proyecto.
