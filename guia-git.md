# Guía de Git y GitHub para el equipo

Esta guía explica cómo trabajar con el repositorio de ReclutApp sin
experiencia previa en Git ni en GitHub. Cubre las dos formas de hacerlo:

- **GitHub Desktop**: programa con ventanas y botones, no requiere
  escribir comandos. Recomendado para empezar.
- **Línea de comandos (Git)**: los mismos pasos escritos como comandos.
  Útil una vez que el flujo básico ya se entiende, porque es más rápido
  y funciona igual en cualquier computadora.

No hace falta elegir una sola forma para siempre: se puede usar GitHub
Desktop para el día a día y la terminal solo cuando GitHub Desktop no
alcanza (por ejemplo, algunos casos de conflictos).

Cada sección trae primero el paso en GitHub Desktop y después el
comando equivalente, para poder saltar directo a la que se esté usando.

## Índice

1. [Conceptos básicos](#1-conceptos-básicos)
2. [Instalación y configuración inicial](#2-instalación-y-configuración-inicial)
3. [Clonar el repositorio](#3-clonar-el-repositorio)
4. [Crear una rama](#4-crear-una-rama)
5. [Moverse entre ramas](#5-moverse-entre-ramas)
6. [Guardar cambios (commit)](#6-guardar-cambios-commit)
7. [Subir cambios (push)](#7-subir-cambios-push)
8. [Traer cambios (pull)](#8-traer-cambios-pull)
9. [Pull Request: pedir que se sumen los cambios a `main`](#9-pull-request-pedir-que-se-sumen-los-cambios-a-main)
10. [Revisar y aprobar un Pull Request (merge)](#10-revisar-y-aprobar-un-pull-request-merge)
11. [Si hay un conflicto](#11-si-hay-un-conflicto)
12. [Navegar la página de GitHub](#12-navegar-la-página-de-github)
13. [Glosario rápido](#13-glosario-rápido)

---

## 1. Conceptos básicos

- **Repositorio (repo)**: la carpeta del proyecto con todo su historial
  de cambios. `ReclutApp` es el repo.
- **Commit**: una "foto" guardada de los cambios hechos, con un mensaje
  que explica qué se cambió y por qué.
- **Rama (branch)**: una copia paralela del código para trabajar sin
  afectar a nadie más. `main` es la rama principal, la que queda
  siempre en un estado funcionando. **Nunca se trabaja directo sobre
  `main`**: se crea una rama nueva para cada tarea.
- **Push**: subir los commits hechos en la computadora propia a
  GitHub, para que los demás los vean.
- **Pull**: traer a la computadora propia los cambios que otros ya
  subieron a GitHub.
- **Pull Request (PR)**: un pedido formal de "quiero sumar los cambios
  de mi rama a `main`". Permite que otra persona revise antes de
  aceptarlo.
- **Merge**: la acción de sumar los cambios de una rama a otra (por
  ejemplo, de una rama de tarea a `main`), normalmente aceptando un
  Pull Request.

Flujo típico de una tarea: crear rama → hacer cambios → commit → push
→ abrir Pull Request → alguien lo revisa → merge a `main`.

---

## 2. Instalación y configuración inicial

### Opción A: GitHub Desktop

1. Descargar e instalar desde [desktop.github.com](https://desktop.github.com/).
2. Al abrirlo la primera vez, hacer clic en **"Sign in to GitHub.com"**
   e iniciar sesión con la cuenta de GitHub (si no se tiene una,
   crearla antes en [github.com](https://github.com)).
3. Completar nombre y correo cuando lo pida (queda asociado a cada
   commit que se haga, para saber quién hizo qué cambio).

### Opción B: línea de comandos

1. Instalar Git desde [git-scm.com](https://git-scm.com/downloads).
   En Windows, dejar las opciones por defecto durante la instalación.
2. Abrir una terminal (PowerShell) y configurar nombre y correo una
   sola vez:
   ```bash
   git config --global user.name "Nombre Apellido"
   git config --global user.email "correo@ejemplo.com"
   ```
3. Iniciar sesión con la cuenta de GitHub. La forma más simple es
   instalar [GitHub CLI](https://cli.github.com/) y ejecutar:
   ```bash
   gh auth login
   ```
   y seguir las instrucciones en pantalla (elegir GitHub.com, HTTPS, y
   loguearse desde el navegador). Esto deja Git configurado para no
   pedir usuario y contraseña en cada `push`.

---

## 3. Clonar el repositorio

Clonar significa traer una copia completa del repo (con todo su
historial) a la computadora. Se hace **una sola vez** por computadora.

### GitHub Desktop

1. Menú **File → Clone Repository**.
2. Pestaña "GitHub.com", buscar `Aknudans/ReclutApp` en la lista (o
   pegar la URL en la pestaña "URL").
3. Elegir en qué carpeta local guardarlo y hacer clic en **Clone**.

### Línea de comandos

```bash
git clone https://github.com/Aknudans/ReclutApp.git
cd ReclutApp
```

---

## 4. Crear una rama

Antes de empezar cualquier tarea nueva, crear una rama con un nombre
que describa lo que se va a hacer (por ejemplo `arreglo-descarga-pdf`
o `agregar-filtro-email`).

### GitHub Desktop

1. Con el repo abierto, hacer clic en el selector de ramas (arriba,
   dice "Current branch").
2. **New branch**, escribir el nombre y **Create branch**. Queda
   parada automáticamente sobre esa rama nueva.

### Línea de comandos

```bash
git checkout main
git pull
git checkout -b nombre-de-la-rama
```

(las primeras dos líneas aseguran arrancar la rama nueva desde la
versión más actualizada de `main`)

---

## 5. Moverse entre ramas

### GitHub Desktop

Hacer clic en el selector de ramas (arriba) y elegir la rama deseada
de la lista.

⚠️ Si hay cambios sin guardar (sin commit) en la rama actual, GitHub
Desktop avisa y ofrece guardarlos aparte ("stash") antes de cambiar.

### Línea de comandos

```bash
git checkout nombre-de-la-rama
```

Para ver todas las ramas disponibles:
```bash
git branch -a
```

---

## 6. Guardar cambios (commit)

Después de modificar uno o varios archivos:

### GitHub Desktop

1. En la pestaña **Changes** (izquierda) aparecen los archivos
   modificados. Tildar los que se quieran incluir en este commit (por
   defecto vienen todos tildados).
2. Abajo a la izquierda, escribir un **resumen corto** (obligatorio) y,
   opcionalmente, una **descripción** más larga.
3. Hacer clic en **Commit to nombre-de-la-rama**.

### Línea de comandos

```bash
git add .
git commit -m "Resumen corto del cambio"
```

`git add .` agrega todos los archivos modificados al commit. Para
agregar solo algunos: `git add ruta/al/archivo.py`.

**Mensajes de commit**: describir qué cambia y, si no es obvio, por
qué (ej. "Corrige error al fusionar personas sin CV" en vez de
"cambios").

---

## 7. Subir cambios (push)

Sube los commits hechos localmente a GitHub, para que queden
respaldados y visibles para el resto del equipo.

### GitHub Desktop

Hacer clic en **Push origin** (arriba). Si es la primera vez que se
sube esa rama, el botón puede decir **Publish branch**.

### Línea de comandos

```bash
git push
```

Si es la primera vez que se sube esa rama nueva, Git puede pedir:
```bash
git push -u origin nombre-de-la-rama
```
(después de esa primera vez, alcanza con `git push` a secas)

---

## 8. Traer cambios (pull)

Trae a la computadora los cambios que otros subieron a GitHub. Conviene
hacerlo seguido, sobre todo antes de empezar a trabajar y antes de
crear una rama nueva.

### GitHub Desktop

Hacer clic en **Fetch origin** y, si aparecen cambios nuevos, el botón
pasa a decir **Pull origin** — hacer clic ahí.

### Línea de comandos

```bash
git pull
```

---

## 9. Pull Request: pedir que se sumen los cambios a `main`

Una vez que la tarea está lista (con sus commits ya subidos con
`push`), se pide que esos cambios se sumen a `main` mediante un Pull
Request (PR). Esto se hace siempre desde la página de GitHub, no desde
GitHub Desktop ni la terminal (aunque ambos ofrecen un atajo para
abrir el navegador directo en esta pantalla).

1. Ir a `https://github.com/Aknudans/ReclutApp`.
2. Si se subió una rama hace poco, suele aparecer un cartel amarillo
   arriba: **"Compare & pull request"** — hacer clic ahí. Si no
   aparece, ir a la pestaña **Pull requests** → **New pull request** y
   elegir la rama propia como "compare" contra `main` como "base".
3. Escribir un título y, en la descripción, explicar qué se hizo y por
   qué (ayuda mucho a quien lo revisa).
4. Hacer clic en **Create pull request**.

Desde GitHub Desktop también se puede: botón **Create Pull Request**
(arriba a la derecha), que abre el navegador ya en el paso 3.

A partir de acá, el PR queda esperando revisión antes del merge (ver
sección siguiente). Se pueden seguir subiendo más commits a la misma
rama con `push` mientras el PR está abierto — se agregan solos al PR.

---

## 10. Revisar y aprobar un Pull Request (merge)

**Al empezar, esta parte la hace una sola persona del equipo** (para
evitar mezclar cambios de forma riesgosa mientras el resto se
familiariza con Git). Se documenta igual acá para cuando el equipo
esté listo para repartir esta tarea.

1. En la pestaña **Pull requests** de GitHub, abrir el PR a revisar.
2. Pestaña **Files changed** muestra línea por línea qué cambió
   (verde = agregado, rojo = borrado). Se puede comentar sobre una
   línea puntual pasando el mouse por al lado y haciendo clic en el
   `+` que aparece.
3. Si está todo bien, volver a la pestaña **Conversation**, bajar
   hasta el final y hacer clic en **Merge pull request** → **Confirm
   merge**.
4. Botón **Delete branch** (aparece después del merge): borra la rama
   ya usada en GitHub — no hace falta conservarla, el historial queda
   igual en `main`.

Después de un merge, todos los demás deberían hacer **pull** sobre su
copia de `main` para tener lo último (sección 8, primero cambiándose a
`main` con la sección 5).

---

## 11. Si hay un conflicto

Un conflicto pasa cuando dos personas modificaron las mismas líneas de
un mismo archivo en ramas distintas, y Git no puede decidir solo cuál
versión dejar. Aparece al hacer `pull` o al intentar el merge de un
Pull Request.

- **En GitHub Desktop**: avisa con un mensaje señalando los archivos en
  conflicto. Hace falta abrirlos en un editor de texto (o el editor
  configurado en GitHub Desktop) y buscar bloques marcados así:
  ```
  <<<<<<< HEAD
  (versión propia)
  =======
  (versión de la otra persona)
  >>>>>>> nombre-de-la-otra-rama
  ```
  Editar a mano hasta dejar el archivo como debería quedar (borrando
  las marcas `<<<<<<<`, `=======` y `>>>>>>>`), guardar, y hacer commit
  normalmente (sección 6).
- **Por línea de comandos**: mismo procedimiento — `git status` indica
  qué archivos están en conflicto, se editan a mano, y después:
  ```bash
  git add .
  git commit
  ```

Si el conflicto no queda claro, mejor frenar y pedir ayuda antes de
adivinar — es preferible perder cinco minutos preguntando que perder
el trabajo de alguien por elegir mal una versión.

---

## 12. Navegar la página de GitHub

Con el repo abierto en `https://github.com/Aknudans/ReclutApp`:

- **Pestaña "Code"** (la que aparece por defecto): lista de archivos y
  carpetas del repo, tal como está en la rama seleccionada. El
  selector de rama está arriba a la izquierda (dice el nombre de la
  rama, por defecto `main`) — cambiarlo muestra el contenido de esa
  otra rama.
- **Pestaña "Pull requests"**: todos los PR, abiertos y cerrados. Los
  abiertos son los que esperan revisión o están en curso.
- **Pestaña "Issues"** (si está habilitada): lista de tareas o
  problemas reportados, si el equipo la usa para organizar trabajo.
- **Historial de commits**: desde "Code", hacer clic en el reloj con
  un número al lado (cerca del botón verde "Code", arriba a la
  derecha de la lista de archivos) — muestra todos los commits de esa
  rama, más recientes primero, con quién los hizo y cuándo.
- **Ver un archivo puntual**: hacer clic en su nombre desde la lista.
  Arriba a la derecha del archivo hay un ícono de lápiz (editar
  directo en GitHub, no recomendado para cambios de código salvo algo
  muy chico) y un ícono de historial (reloj) para ver solo los cambios
  de ese archivo.
- **Comparar dos ramas o dos commits**: agregar `/compare` a la URL
  del repo (`https://github.com/Aknudans/ReclutApp/compare`) y elegir
  qué comparar contra qué.
- **Notificaciones**: campanita arriba a la derecha de cualquier
  página de GitHub — avisa de comentarios en PR propios, menciones,
  etc.
- **Buscar en el repo**: tecla `/` en cualquier página del repo enfoca
  la barra de búsqueda arriba.

---

## 13. Glosario rápido

| Término | Qué es |
|---|---|
| Repo | La carpeta del proyecto con todo su historial |
| Clonar | Traer una copia del repo a la computadora (una sola vez) |
| Rama / branch | Copia paralela del código para trabajar sin afectar a nadie |
| Commit | Una "foto" guardada de los cambios, con mensaje |
| Push | Subir los commits propios a GitHub |
| Pull | Traer a la computadora los cambios que otros subieron |
| Pull Request (PR) | Pedido de sumar los cambios de una rama a `main` |
| Merge | Sumar los cambios de una rama a otra |
| Conflicto | Cuando Git no puede decidir solo entre dos versiones de una misma línea |
| `main` | La rama principal, siempre en estado funcionando — nunca se trabaja directo ahí |
