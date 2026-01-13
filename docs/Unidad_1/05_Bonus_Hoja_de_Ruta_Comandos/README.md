# Bonus: Hoja de Ruta de Comandos de Git

## Introducción

Esta hoja de ruta no pretende ser un reemplazo de la documentación oficial, sino una guía contextual y categorizada de los comandos de Git más utilizados en un entorno de ingeniería de software profesional.

Los comandos se agrupan por su **propósito** dentro del ciclo de vida del desarrollo. Comprender la categoría de un comando ayuda a entender su impacto en el repositorio.

---

## 1. Comandos de Configuración e Inicialización

*Propósito: Configurar el entorno de Git y crear nuevos repositorios.*

-   `git config --global user.name "[nombre]"`
    -   **Uso:** Establece el nombre que se asociará a tus commits. Se hace una sola vez por máquina.
-   `git config --global user.email "[email]"`
    -   **Uso:** Establece el email que se asociará a tus commits.
-   `git init`
    -   **Uso:** Inicializa un nuevo repositorio de Git en el directorio actual. Crea la subcarpeta `.git`.
-   `git clone [url]`
    -   **Uso:** Crea una copia local completa (un clon) de un repositorio remoto.

---

## 2. Comandos del Flujo de Trabajo Básico (El "Inner Loop")

*Propósito: Gestionar el ciclo de vida de los cambios en el modelo de tres estados.*

-   `git status`
    -   **Uso:** El comando más importante. Muestra el estado del Directorio de Trabajo y el Índice (Staging Area).
-   `git add [archivo]`
    -   **Uso:** Promueve los cambios de un archivo del Directorio de Trabajo al Índice.
    -   **Variantes:** `git add .` (añade todos los cambios), `git add -p` (modo interactivo para añadir fragmentos de código).
-   `git commit -m "[mensaje]"`
    -   **Uso:** Crea una nueva instantánea (commit) a partir del estado del Índice.
    -   **Variantes:** `git commit -am "[mensaje]"` (añade y hace commit de todos los archivos rastreados en un solo paso; usar con precaución). `git commit --amend` (modifica el último commit).
-   `git log`
    -   **Uso:** Muestra el historial de commits.
    -   **Variantes:** `git log --oneline` (versión compacta), `git log --graph` (muestra el historial como un grafo), `git log --stat` (muestra las estadísticas de los archivos cambiados).
-   `git diff`
    -   **Uso:** Muestra las diferencias.
    -   **Variantes:** `git diff` (cambios en el Directorio de Trabajo no preparados), `git diff --staged` (cambios en el Índice no confirmados), `git diff [commit1] [commit2]` (diferencias entre dos commits).
-   `git rm [archivo]`
    -   **Uso:** Elimina un archivo tanto del Directorio de Trabajo como del Índice.
-   `git mv [origen] [destino]`
    -   **Uso:** Renombra o mueve un archivo, manteniendo el historial.

---

## 3. Comandos de Ramificación e Integración

*Propósito: Gestionar los flujos de trabajo paralelos (ramas) y la fusión de sus historiales.*

-   `git branch`
    -   **Uso:** Lista todas las ramas locales. `git branch -r` (remotas), `git branch -a` (todas).
-   `git branch [nombre-rama]`
    -   **Uso:** Crea una nueva rama (un puntero a tu commit actual).
-   `git checkout [nombre-rama]`
    -   **Uso:** Cambia tu `HEAD` para apuntar a la rama especificada, actualizando tu Directorio de Trabajo.
    -   **Variantes:** `git checkout -b [nombre-rama]` (crea y se cambia a la nueva rama en un solo paso).
-   `git merge [nombre-rama]`
    -   **Uso:** Fusiona la rama especificada en tu rama actual, creando un merge commit si es necesario.
-   `git rebase [nombre-rama]`
    -   **Uso:** Reaplica los commits de tu rama actual sobre la punta de la rama especificada. **Reescribe el historial.**
-   `git branch -d [nombre-rama]`
    -   **Uso:** Elimina una rama local que ya ha sido fusionada. `-D` para forzar la eliminación.

---

## 4. Comandos de Sincronización Remota

*Propósito: Interactuar con repositorios remotos (ej. GitHub).*

-   `git remote -v`
    -   **Uso:** Lista los repositorios remotos configurados y sus URLs.
-   `git remote add [alias] [url]`
    -   **Uso:** Añade un nuevo repositorio remoto con un alias (normalmente `origin`).
-   `git fetch [alias-remoto]`
    -   **Uso:** Descarga los objetos y referencias del repositorio remoto, pero **no fusiona** los cambios en tus ramas locales. Actualiza tus ramas de seguimiento remoto (ej. `origin/main`).
-   `git pull [alias-remoto] [rama]`
    -   **Uso:** Es un atajo para `git fetch` seguido de `git merge`. Descarga y fusiona los cambios.
    -   **Variantes:** `git pull --rebase` (descarga y hace rebase en lugar de merge).
-   `git push [alias-remoto] [rama]`
    -   **Uso:** Sube tus commits locales a la rama especificada del repositorio remoto.
    -   **Variantes:** `git push -u origin [rama]` (establece la rama local para que siga a la remota), `git push --force` (sobrescribe la historia remota; **extremadamente peligroso**).

---

## 5. Comandos Avanzados y de "Fontanería"

*Propósito: Herramientas potentes para la manipulación del historial y la recuperación de errores.*

-   `git reset [commit]`
    -   **Uso:** Mueve el puntero de la rama actual a un commit anterior, reescribiendo la historia.
    -   **Modos:** `--soft` (solo mueve el puntero de la rama), `--mixed` (por defecto, actualiza también el Índice), `--hard` (actualiza la rama, el Índice y el Directorio de Trabajo; **los cambios no confirmados se pierden**).
-   `git revert [commit]`
    -   **Uso:** Crea un **nuevo commit** que deshace los cambios introducidos por un commit anterior. Es la forma segura de deshacer cambios en una rama pública porque no reescribe la historia.
-   `git stash`
    -   **Uso:** Guarda temporalmente tus cambios no confirmados (del Directorio de Trabajo y el Índice) para que puedas cambiar de rama. `git stash pop` o `git stash apply` para recuperarlos.
-   `git cherry-pick [commit]`
    -   **Uso:** Aplica los cambios introducidos por un commit existente en otra rama a tu rama actual.
-   `git reflog`
    -   **Uso:** Muestra un log de todas las acciones que han cambiado la punta de tus ramas (`HEAD`). Es una red de seguridad para recuperar commits "perdidos" después de un `reset` o `rebase` destructivo.
-   `git bisect`
    -   **Uso:** Inicia una búsqueda binaria interactiva en el historial para encontrar el commit que introdujo un bug.
