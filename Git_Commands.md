# Git — Tabla de comandos esenciales y avanzados

Referencia rápida para Git y GitHub en formato Markdown, lista para copiar directamente a un archivo `README.md` o `GIT_CHEATSHEET.md`.

## 1. Configuración e inicialización

| Comando                                               | Descripción                                 |
| ----------------------------------------------------- | ------------------------------------------- |
| `git --version`                                       | Ver versión de Git                          |
| `git config --list`                                   | Ver configuración                           |
| `git config --global user.name "Nombre"`              | Configurar usuario                          |
| `git config --global user.email "correo@ejemplo.com"` | Configurar correo                           |
| `git config --global init.defaultBranch main`         | Rama inicial predeterminada                 |
| `git config --global core.editor "code --wait"`       | Configurar VS Code como editor              |
| `git config user.name`                                | Consultar usuario del repositorio           |
| `git init`                                            | Inicializar repositorio                     |
| `git init -b main`                                    | Inicializar con rama `main`                 |
| `git clone URL`                                       | Clonar repositorio                          |
| `git clone URL carpeta`                               | Clonar en una carpeta específica            |
| `git clone --depth 1 URL`                             | Clonar solo el historial reciente           |
| `git rev-parse --show-toplevel`                       | Mostrar raíz del repositorio                |
| `git rev-parse --is-inside-work-tree`                 | Verificar si estás dentro de un repositorio |

## 2. Estado y revisión de cambios

| Comando                                    | Descripción                                     |
| ------------------------------------------ | ----------------------------------------------- |
| `git status`                               | Ver estado actual                               |
| `git status -sb`                           | Estado resumido                                 |
| `git diff`                                 | Ver cambios sin preparar                        |
| `git diff --staged`                        | Ver cambios preparados para commit              |
| `git diff HEAD`                            | Ver todos los cambios respecto al último commit |
| `git diff --stat`                          | Resumen de cambios                              |
| `git diff --name-only`                     | Mostrar archivos modificados                    |
| `git diff --check`                         | Detectar espacios problemáticos                 |
| `git diff rama1..rama2`                    | Comparar ramas                                  |
| `git diff commit1 commit2`                 | Comparar commits                                |
| `git diff -- archivo`                      | Comparar un archivo                             |
| `git status --ignored`                     | Mostrar también archivos ignorados              |
| `git ls-files`                             | Listar archivos bajo seguimiento                |
| `git ls-files --others --exclude-standard` | Listar archivos nuevos no ignorados             |

## 3. Agregar y preparar archivos (staging)

| Comando                        | Descripción                                                     |
| ------------------------------ | --------------------------------------------------------------- |
| `git add archivo`              | Preparar un archivo                                             |
| `git add .`                    | Preparar cambios del directorio actual                          |
| `git add -A`                   | Preparar todos los cambios del repositorio                      |
| `git add *.c`                  | Preparar archivos que coincidan con el patrón en la ruta actual |
| `git add -p`                   | Preparar cambios por fragmentos                                 |
| `git add -u`                   | Preparar modificaciones y eliminaciones de archivos rastreados  |
| `git reset archivo`            | Quitar un archivo del staging sin borrar sus cambios            |
| `git restore --staged archivo` | Retirar un archivo del staging                                  |
| `git diff --cached`            | Revisar lo preparado                                            |
| `git status`                   | Verificar qué se incluirá en el commit                          |

## 4. Commits e historial

| Comando                                 | Descripción                                                   |
| --------------------------------------- | ------------------------------------------------------------- |
| `git commit -m "mensaje"`               | Crear commit                                                  |
| `git commit -am "mensaje"`              | Preparar modificaciones de archivos rastreados y crear commit |
| `git commit`                            | Crear commit con editor                                       |
| `git commit --amend`                    | Modificar el último commit                                    |
| `git commit --amend -m "mensaje"`       | Cambiar mensaje del último commit                             |
| `git commit --allow-empty -m "mensaje"` | Crear commit vacío                                            |
| `git log`                               | Ver historial                                                 |
| `git log --oneline`                     | Historial resumido                                            |
| `git log --oneline --graph --all`       | Historial gráfico de todas las ramas                          |
| `git log -n 10`                         | Mostrar los últimos 10 commits                                |
| `git log --stat`                        | Historial con archivos afectados                              |
| `git log -p`                            | Historial con diferencias                                     |
| `git log -- archivo`                    | Historial de un archivo                                       |
| `git log --author="Nombre"`             | Filtrar por autor                                             |
| `git log --since="2026-01-01"`          | Filtrar por fecha inicial                                     |
| `git log --grep="texto"`                | Buscar mensajes de commits                                    |
| `git show`                              | Mostrar último commit                                         |
| `git show HASH`                         | Mostrar un commit específico                                  |
| `git show --stat HASH`                  | Resumen de archivos de un commit                              |
| `git shortlog -sn`                      | Resumir commits por autor                                     |
| `git reflog`                            | Consultar movimientos recientes de referencias                |
| `git blame archivo`                     | Ver autor y commit por línea                                  |

## 5. Ramas (branches)

| Comando                      | Descripción                            |
| ---------------------------- | -------------------------------------- |
| `git branch`                 | Listar ramas locales                   |
| `git branch -a`              | Listar ramas locales y remotas         |
| `git branch -r`              | Listar ramas remotas                   |
| `git branch -v`              | Ramas con último commit                |
| `git branch -vv`             | Ramas y seguimiento remoto             |
| `git branch nueva`           | Crear rama                             |
| `git switch nueva`           | Cambiar de rama                        |
| `git switch -c nueva`        | Crear y cambiar de rama                |
| `git checkout nueva`         | Cambiar de rama (alternativa clásica)  |
| `git checkout -b nueva`      | Crear y cambiar de rama                |
| `git branch -m nuevo-nombre` | Renombrar rama actual                  |
| `git branch -m viejo nuevo`  | Renombrar una rama                     |
| `git branch -d rama`         | Eliminar rama fusionada                |
| `git branch -D rama`         | Forzar eliminación de rama local       |
| `git branch --merged`        | Listar ramas fusionadas                |
| `git branch --no-merged`     | Listar ramas no fusionadas             |
| `git switch -`               | Volver a la rama anterior              |
| `git push -u origin rama`    | Publicar rama y configurar seguimiento |

## 6. Sincronización con GitHub y remotos

| Comando                           | Descripción                                            |
| --------------------------------- | ------------------------------------------------------ |
| `git remote -v`                   | Ver remotos y URL                                      |
| `git remote add origin URL`       | Agregar remoto                                         |
| `git remote remove origin`        | Eliminar remoto                                        |
| `git remote rename origin github` | Renombrar remoto                                       |
| `git remote set-url origin URL`   | Cambiar URL del remoto                                 |
| `git fetch`                       | Descargar referencias y objetos remotos                |
| `git fetch origin`                | Actualizar referencias desde `origin`                  |
| `git fetch --all`                 | Actualizar desde todos los remotos                     |
| `git fetch --prune`               | Eliminar referencias remotas obsoletas                 |
| `git pull`                        | Descargar e integrar cambios                           |
| `git pull --rebase`               | Integrar cambios mediante rebase                       |
| `git pull origin main`            | Actualizar desde `origin/main`                         |
| `git push`                        | Publicar cambios según configuración                   |
| `git push origin main`            | Publicar la rama `main`                                |
| `git push -u origin main`         | Publicar y establecer seguimiento                      |
| `git push --all origin`           | Publicar todas las ramas locales                       |
| `git push --tags`                 | Publicar etiquetas                                     |
| `git push --force-with-lease`     | Forzar publicación con comprobación de cambios remotos |
| `git ls-remote origin`            | Consultar referencias del remoto                       |
| `git remote show origin`          | Consultar información del remoto                       |

## 7. Merge, rebase y cherry-pick

| Comando                      | Descripción                                     |
| ---------------------------- | ----------------------------------------------- |
| `git merge rama`             | Fusionar una rama en la actual                  |
| `git merge --no-ff rama`     | Fusionar creando commit de merge                |
| `git merge --squash rama`    | Preparar cambios fusionados en un solo conjunto |
| `git merge --abort`          | Cancelar un merge en curso                      |
| `git rebase main`            | Reaplicar commits sobre `main`                  |
| `git rebase -i HEAD~3`       | Editar los últimos 3 commits                    |
| `git rebase --continue`      | Continuar rebase después de resolver conflictos |
| `git rebase --abort`         | Cancelar rebase                                 |
| `git rebase --skip`          | Omitir commit actual del rebase                 |
| `git cherry-pick HASH`       | Aplicar un commit específico                    |
| `git cherry-pick A..B`       | Aplicar commits posteriores a A hasta B         |
| `git cherry-pick --continue` | Continuar cherry-pick                           |
| `git cherry-pick --abort`    | Cancelar cherry-pick                            |
| `git mergetool`              | Abrir herramienta de resolución de conflictos   |

## 8. Deshacer cambios y recuperar archivos

| Comando                               | Descripción                                                    |
| ------------------------------------- | -------------------------------------------------------------- |
| `git restore archivo`                 | Descartar cambios no preparados de un archivo                  |
| `git restore .`                       | Descartar cambios no preparados del directorio actual          |
| `git restore --source=HEAD~1 archivo` | Recuperar archivo desde el commit anterior                     |
| `git reset archivo`                   | Quitar archivo del staging                                     |
| `git reset --soft HEAD~1`             | Deshacer último commit conservando cambios preparados          |
| `git reset --mixed HEAD~1`            | Deshacer último commit conservando cambios sin preparar        |
| `git reset --hard HEAD~1`             | Deshacer último commit y descartar cambios afectados           |
| `git revert HASH`                     | Crear commit que revierte otro commit                          |
| `git revert HEAD`                     | Revertir el último commit                                      |
| `git clean -n`                        | Previsualizar archivos no rastreados que se borrarían          |
| `git clean -f`                        | Eliminar archivos no rastreados                                |
| `git clean -fd`                       | Eliminar archivos y carpetas no rastreados                     |
| `git reflog`                          | Buscar referencias anteriores para recuperación                |
| `git reset --hard HASH`               | Mover la rama al commit indicado y descartar cambios afectados |

Cuidado: `reset --hard`, `restore` y `clean -f` pueden provocar pérdida de trabajo. `reset --hard` no es equivalente a `revert`: el primero mueve la referencia y puede descartar cambios; el segundo genera un commit inverso.

## 9. Resolución de conflictos

| Comando                                | Descripción                                            |
| -------------------------------------- | ------------------------------------------------------ |
| `git status`                           | Identificar archivos en conflicto                      |
| `git diff --name-only --diff-filter=U` | Listar archivos sin resolver                           |
| `git diff -- archivo`                  | Inspeccionar conflictos                                |
| `git add archivo`                      | Marcar conflicto como resuelto                         |
| `git restore --ours archivo`           | Conservar la versión de la rama actual                 |
| `git restore --theirs archivo`         | Conservar la versión entrante                          |
| `git checkout --ours archivo`          | Alternativa clásica para conservar la versión actual   |
| `git checkout --theirs archivo`        | Alternativa clásica para conservar la versión entrante |
| `git merge --continue`                 | Continuar merge después de resolver conflictos         |
| `git merge --abort`                    | Cancelar merge                                         |
| `git rebase --continue`                | Continuar rebase                                       |
| `git rebase --abort`                   | Cancelar rebase                                        |

Nota: `--ours` y `--theirs` pueden resultar menos intuitivos durante un rebase; verifica cuál versión necesitas antes de elegir.

## 10. Etiquetas (tags) y versiones

| Comando                                | Descripción                               |
| -------------------------------------- | ----------------------------------------- |
| `git tag`                              | Listar etiquetas                          |
| `git tag v1.0.0`                       | Crear etiqueta ligera                     |
| `git tag -a v1.0.0 -m "Release 1.0.0"` | Crear etiqueta anotada                    |
| `git show v1.0.0`                      | Ver detalles de etiqueta                  |
| `git tag -d v1.0.0`                    | Eliminar etiqueta local                   |
| `git push origin v1.0.0`               | Publicar una etiqueta                     |
| `git push origin --tags`               | Publicar todas las etiquetas              |
| `git push origin --delete v1.0.0`      | Eliminar etiqueta remota                  |
| `git describe --tags`                  | Identificar versión cercana por etiquetas |

## 11. Archivos ignorados y seguimiento

| Comando                            | Descripción                               |
| ---------------------------------- | ----------------------------------------- |
| `git check-ignore -v archivo`      | Identificar regla que ignora un archivo   |
| `git status --ignored`             | Ver archivos ignorados                    |
| `git ls-files --others`            | Ver archivos no rastreados                |
| `git rm archivo`                   | Eliminar archivo y registrar eliminación  |
| `git rm --cached archivo`          | Dejar de rastrear sin borrar del disco    |
| `git rm -r --cached carpeta/`      | Dejar de rastrear una carpeta             |
| `git mv viejo nuevo`               | Renombrar o mover un archivo              |
| `git add -f archivo`               | Forzar seguimiento de un archivo ignorado |
| `git check-attr -a -- archivo`     | Consultar atributos Git del archivo       |
| `git sparse-checkout init`         | Activar checkout parcial de rutas         |
| `git sparse-checkout set carpeta/` | Limitar checkout a rutas seleccionadas    |

## 12. Stash (guardar cambios temporalmente)

| Comando                       | Descripción                                              |
| ----------------------------- | -------------------------------------------------------- |
| `git stash`                   | Guardar cambios rastreados temporalmente                 |
| `git stash push -m "mensaje"` | Guardar cambios con descripción                          |
| `git stash -u`                | Guardar también archivos no rastreados                   |
| `git stash -a`                | Guardar también archivos ignorados                       |
| `git stash list`              | Listar stashes                                           |
| `git stash show`              | Resumir último stash                                     |
| `git stash show -p`           | Mostrar diferencias del stash                            |
| `git stash apply`             | Recuperar sin eliminar el stash                          |
| `git stash apply stash@{1}`   | Aplicar un stash específico                              |
| `git stash pop`               | Recuperar y eliminar el stash si se aplica correctamente |
| `git stash drop stash@{0}`    | Eliminar un stash                                        |
| `git stash clear`             | Eliminar todos los stashes                               |

## 13. Búsqueda y diagnóstico

| Comando                      | Descripción                                            |
| ---------------------------- | ------------------------------------------------------ |
| `git grep "texto"`           | Buscar texto en archivos rastreados                    |
| `git grep -n "texto"`        | Buscar mostrando números de línea                      |
| `git log --grep="texto"`     | Buscar en mensajes de commits                          |
| `git log -S"texto"`          | Buscar cambios en el número de apariciones de texto    |
| `git log -G"regex"`          | Buscar cambios que coincidan con una expresión regular |
| `git blame -L 10,20 archivo` | Identificar autores entre líneas 10 y 20               |
| `git bisect start`           | Iniciar búsqueda binaria de un error                   |
| `git bisect bad`             | Marcar versión actual como defectuosa                  |
| `git bisect good HASH`       | Marcar versión conocida como correcta                  |
| `git bisect reset`           | Finalizar búsqueda binaria                             |
| `git fsck --full`            | Comprobar integridad de objetos                        |
| `git count-objects -vH`      | Consultar uso y cantidad de objetos                    |
| `git gc`                     | Optimizar almacenamiento interno                       |
| `git verify-commit HASH`     | Verificar firma de un commit                           |
| `git verify-tag TAG`         | Verificar firma de una etiqueta                        |

## 14. Submódulos y repositorios relacionados

| Comando                                        | Descripción                                    |
| ---------------------------------------------- | ---------------------------------------------- |
| `git submodule status`                         | Consultar estado de submódulos                 |
| `git submodule add URL ruta/`                  | Agregar un submódulo                           |
| `git submodule update --init`                  | Inicializar y actualizar submódulos            |
| `git submodule update --init --recursive`      | Actualizar también submódulos anidados         |
| `git submodule update --remote`                | Actualizar según la rama remota configurada    |
| `git clone --recurse-submodules URL`           | Clonar incluyendo submódulos                   |
| `git worktree list`                            | Listar árboles de trabajo                      |
| `git worktree add ../proyecto-feature feature` | Crear otro directorio de trabajo para una rama |
| `git worktree remove ../proyecto-feature`      | Eliminar un árbol de trabajo adicional         |

## 15. Configuración avanzada y alias

| Comando                                       | Descripción                                                          |
| --------------------------------------------- | -------------------------------------------------------------------- |
| `git config --global core.autocrlf true`      | Convertir finales de línea al trabajar en Windows                    |
| `git config --global core.autocrlf input`     | Normalizar finales de línea al confirmar cambios                     |
| `git config --global pull.rebase true`        | Preferir rebase al ejecutar `git pull`                               |
| `git config --global fetch.prune true`        | Limpiar referencias remotas obsoletas automáticamente al hacer fetch |
| `git config --global init.defaultBranch main` | Definir rama inicial `main`                                          |
| `git config --global alias.st status`         | Crear alias `git st`                                                 |
| `git config --global alias.co checkout`       | Crear alias `git co`                                                 |
| `git config --global alias.br branch`         | Crear alias `git br`                                                 |
| `git config --global alias.ci commit`         | Crear alias `git ci`                                                 |
| `git config --global --unset alias.st`        | Eliminar un alias                                                    |
| `git config --show-origin --list`             | Ver configuración y archivo de origen                                |
| `git config --local --list`                   | Ver configuración local del repositorio                              |
| `git config --global --edit`                  | Editar configuración global                                          |
| `git help -a`                                 | Listar comandos disponibles                                          |
| `git help comando`                            | Abrir ayuda de un comando                                            |
| `git comando -h`                              | Mostrar ayuda resumida                                               |

## 16. Workflows frecuentes

| Objetivo                                         | Secuencia de comandos                                                          |
| ------------------------------------------------ | ------------------------------------------------------------------------------ |
| Crear repositorio local                          | `git init` → `git add .` → `git commit -m "Initial commit"`                    |
| Subir proyecto existente a GitHub                | `git remote add origin URL` → `git branch -M main` → `git push -u origin main` |
| Descargar proyecto                               | `git clone URL`                                                                |
| Guardar cambios                                  | `git add -A` → `git commit -m "Descripción"`                                   |
| Subir cambios                                    | `git push`                                                                     |
| Actualizar proyecto                              | `git pull`                                                                     |
| Crear nueva funcionalidad                        | `git switch -c feature/nombre`                                                 |
| Publicar una rama nueva                          | `git push -u origin feature/nombre`                                            |
| Actualizar rama de trabajo                       | `git fetch origin` → `git merge origin/main`                                   |
| Actualizar con rebase                            | `git fetch origin` → `git rebase origin/main`                                  |
| Fusionar funcionalidad                           | `git switch main` → `git merge feature/nombre`                                 |
| Deshacer último commit local conservando cambios | `git reset --soft HEAD~1`                                                      |
| Revertir un commit publicado                     | `git revert HASH`                                                              |
| Guardar cambios sin commit                       | `git stash` → `git stash pop`                                                  |
| Crear versión                                    | `git tag -a v1.0.0 -m "Release 1.0.0"` → `git push origin v1.0.0`              |
| Resolver conflicto de merge                      | Editar archivos → `git add archivo` → `git merge --continue`                   |
| Recuperar un commit perdido                      | `git reflog` → `git switch -c recuperacion HASH`                               |

## 17. Convenciones y buenas prácticas

| Elemento                | Recomendación                                                   |
| ----------------------- | --------------------------------------------------------------- |
| Mensajes de commit      | Claros, breves y orientados a la acción                         |
| Rama principal          | `main`                                                          |
| Nuevas funcionalidades  | `feature/nombre`                                                |
| Corrección de errores   | `fix/nombre`                                                    |
| Versiones               | Etiquetas como `v1.0.0`                                         |
| Archivos sensibles      | Excluir claves, contraseñas y tokens mediante `.gitignore`      |
| Antes de un commit      | Revisar `git status` y `git diff --staged`                      |
| Antes de un merge       | Actualizar referencias con `git fetch`                          |
| Ramas compartidas       | Evitar reescribir el historial publicado                        |
| Historial compartido    | Preferir `git revert` para deshacer commits publicados          |
| Autenticación en GitHub | Usar SSH o HTTPS con un método de autenticación compatible      |
| Dependencias            | Documentar versiones y no subir carpetas generadas innecesarias |

## 18. Chuleta mínima: los 15 comandos que más usarás

| Comando                           | Uso                               |
| --------------------------------- | --------------------------------- |
| `git clone URL`                   | Descargar repositorio             |
| `git status`                      | Ver estado                        |
| `git add -A`                      | Preparar cambios                  |
| `git commit -m "mensaje"`         | Guardar cambios                   |
| `git pull`                        | Actualizar                        |
| `git push`                        | Publicar cambios                  |
| `git fetch`                       | Consultar actualizaciones remotas |
| `git switch -c rama`              | Crear rama                        |
| `git switch rama`                 | Cambiar de rama                   |
| `git branch -a`                   | Ver ramas                         |
| `git merge rama`                  | Fusionar rama                     |
| `git log --oneline --graph --all` | Ver historial gráfico             |
| `git diff`                        | Revisar cambios                   |
| `git stash`                       | Guardar cambios temporalmente     |
| `git revert HASH`                 | Revertir un commit                |

Regla de oro: `add` prepara, `commit` guarda localmente, `push` publica, `fetch` consulta el remoto, `pull` descarga e integra y `revert` deshace mediante un nuevo commit.
