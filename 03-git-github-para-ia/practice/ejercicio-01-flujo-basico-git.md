# Ejercicio 01 - Flujo básico con Git

## Objetivo

Practicar el flujo mínimo de Git haciendo un fork del repositorio Multihope a tu cuenta personal de GitHub y trabajando sobre tu propia copia del proyecto.

## Duración sugerida

20 a 25 minutos

## Requisitos

- tener una cuenta personal de GitHub
- tener Git instalado
- tener un Personal Access Token (PAT) generado en tu cuenta de GitHub con scope `repo`

---

## Paso 1 - Hacer fork del repositorio

Un **fork** crea una copia del repositorio en tu cuenta personal de GitHub. A partir de ahí trabajas de forma independiente sin afectar el repositorio original.

1. Ingresa a: [https://github.com/amartinez2b/multihope](https://github.com/amartinez2b/multihope)
2. Haz clic en el botón **Fork** (esquina superior derecha)
3. Selecciona tu cuenta personal como destino
4. Deja el nombre `multihope` y haz clic en **Create fork**

Al terminar, GitHub te redirige a tu propio repositorio:
```
https://github.com/<tu-usuario>/multihope
```

A partir de este punto, **todos los pasos se realizan sobre tu fork**.

---

## Paso 2 - Clonar tu fork en tu máquina

Incluye tu usuario de GitHub en la URL para que el sistema de credenciales lo asocie correctamente:

```bash
git clone https://<tu-usuario>@github.com/<tu-usuario>/multihope.git
cd multihope
```

Cuando te pida contraseña, ingresa tu **Personal Access Token** (no tu contraseña de GitHub).

---

## Paso 3 - Configurar tu identidad en el repo

```bash
git config user.name "Tu Nombre"
git config user.email "tucorreo@ejemplo.com"
```

Esta configuración es local: aplica solo a este repositorio y no afecta otros proyectos en tu máquina.

---

## Paso 4 - Verificar que el remote apunta a tu fork

```bash
git remote -v
```

Debes ver tu usuario en la URL, no `amartinez2b`:

```
origin  https://<tu-usuario>@github.com/<tu-usuario>/multihope.git (fetch)
origin  https://<tu-usuario>@github.com/<tu-usuario>/multihope.git (push)
```

---

## Paso 5 - Explorar la estructura del proyecto

```bash
ls -la
```

Familiarízate con las carpetas del proyecto:

| Carpeta | Contenido |
|---|---|
| `src/` | Scripts del pipeline (ingestion, transform, aggregation) |
| `notebooks/` | Notebooks Jupyter del pipeline (00 al 03) |
| `config/` | Configuración de base de datos y Spark |
| `catalog/comercial/` | Catálogo de datos del producto Comercial |
| `tests/` | Pruebas unitarias |

---

## Paso 6 - Revisar el estado actual

```bash
git status
git log --oneline -n 5
```

Preguntas:

- ¿En qué rama estás?
- ¿Cuántos commits tiene el historial reciente?
- ¿Los mensajes de commit son descriptivos?

---

## Paso 7 - Crear una rama de trabajo personal

```bash
git checkout -b practica/<tu-nombre>
```

Por ejemplo: `practica/ana-torres`

---

## Paso 8 - Hacer un cambio concreto

Abre el archivo `catalog/comercial/catalog.md` y agrega al final de la sección **Glosario de negocio** una nueva fila con un término que tú definirías. Por ejemplo:

```markdown
| **Margen por producto** | Diferencia entre `products.precio_unitario` y `sales.precio_unitario`. Indica el descuento aplicado por sucursal. |
```

---

## Paso 9 - Revisar el cambio

```bash
git status
git diff catalog/comercial/catalog.md
```

---

## Paso 10 - Preparar y crear el commit

```bash
git add catalog/comercial/catalog.md
git commit -m "docs: agrega termino <nombre-del-termino> al glosario del catalogo Comercial"
```

---

## Paso 11 - Subir los cambios a tu fork en GitHub

```bash
git push origin practica/<tu-nombre>
```

Verifica en `https://github.com/<tu-usuario>/multihope` que tu rama aparece publicada.

---

## Paso 12 - Ver el historial final

```bash
git log --oneline -n 5
```

---

## Preguntas de reflexión

- ¿Qué diferencia hay entre clonar un repo directamente y hacer un fork primero?
- ¿Por qué es útil que cada estudiante trabaje sobre su propio fork y no sobre el repositorio original?
- Si un agente de IA hiciera cambios en el proyecto sin commits claros, ¿cómo sabrías qué modificó?
- ¿Qué ventaja tiene que el mensaje de commit describa el archivo y el motivo del cambio?

---

## Entregable

El estudiante debe presentar:

1. la URL de su fork (`https://github.com/<tu-usuario>/multihope`)
2. el nombre de su rama (`practica/<tu-nombre>`)
3. el mensaje de commit usado
4. el output de `git log --oneline -n 3`
5. una explicación de una línea sobre qué aprendió del flujo
