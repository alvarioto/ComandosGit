Comandos más útiles de Git
Puedes encontrar info en esta web

git add
Mueve los cambios del working directory hacia el area de staging. Esto te permite preparar lo que quieres commitear.

git add .
git branch
Muesta la rama en la que te encuentras actualmente.

git branch
git checkout
Nos permite cambiar de rama y crear ramas nuevas.

# Cambiamos a la rama existente
git checkout development

# Creamos una nueva rama llamada development
git checkout -b development
git clean
Elimina los archivos no rastreados en el working directory. Esos son los archivos que no están bajo control de versión, es decir, no han sido agregados al índice de Git ni han sido comprometidos previamente.

# Tienes archvios no rastreados y los quieres eliminar
git clean -n

# Elimina los archivos no rastreados de manera permanenete
git clean -f
git clone
Con este comando hacemos una clonación del repositorio a nuestro equipo, de manera que tendremos el repositorio en local.

# Clona el repositorio nonsible.
git clone https://github.com/NeddM/nonsible

# Clona el repositorio usando un protocolo específico
git clone git@github.com:NeddM/nonsible.git --ssh
git commit
Se utiliza para guardar los cambios realizados en el área de preparación en el historial de versiones del respositorio.

# Crea un commit con el mensaje
git commit -m "Mensaje del commit"

# Modifica el último commit sin crear uno nuevo
git commit --amend -m "Nuevo mensaje del commit"
git config
Se utiliza para configurar opciones específicas de Git tanto a nivel global como a nivel de repositorio.

# Establece configuraciones globales
git config --global user.name "Nedd"
git config --global user.email "neddchairiweb@gmail.com"

# Listar configuración actual
git config [--global] --list

# Eliminar configuración
git config --unset user.name
git fetch
Recupera los cambios del repositorio remoto sin fusionarlos automáticamente con tu trabajo actual. Es como un git pull, pero también recupera los cambios en otras ramas.

git fetch origin
git init
Inicia un nuevo repositorio de Git.

git init
git log
Se utiliza para ver el historial de commits en un repositorio de Git.

git log
git merge
Se utiliza para fusionar los cambios de una rama en otra.

git merge development
git pull
Recupera los cambios desde un repositorio remoto y los fusiona automáticamente con la rama local actual.

git pull

git pull origin main
git push
Envía los commits locales a un repositorio remoto.

# Pushea la rama en la que te encuentras ahora
git push

# Pushea indicando la rama
git push origin main

# Pushea hacia un repositorio remoto una rama
git push https://github.com/NeddM/nonsible development

# Pushea una rama que no existía en remoto
git push --set-upstream origin development
git rebase
Se utiliza en Git para reorganizar o modificar el historial de commits de una rama. A diferencia de git merge, que fusiona los cambios de una rama en otra, git rebase reorganiza la historia de commits de una rama sobre la base de otra.

git rebase main

# Trabaja con los tres últimos commits
git rebase -i HEAD~3
git reflog
Se utiliza para ver el registro de referencia del repositorio, que muestra un historial detallado de todas las acciones realizadas en el repositorio.

git reflog
git remote
Se utiliza para administrar conexiones a repositorios remotos. Permite ver, agregar y eliminar repositorios remotos asociados con tu repositorio local.

# Agrega un neuvo repositorio remoto
git remote add nonsible https://github.com/NeddM/nonsible

# Elimina un repositorio remoto
git remote remove nonsible

# Cambiar el nombre de un repositorio remoto
git remote rename nonsible nonsible-nuevo-nombre

# Ver información detallada sobre un repositorio remoto
git remote show nonsible
git reset
Se utiliza para mover el puntero HEAD y, opcionalmente, la rama actual, a un commit específico o deshacer cambios en el área de preparación (staging) y/o en el working directory.

# Resetear commit específico
git reset <commit>

# Deshace el commit pero mantiene los cambios en el area de preparación y en el working directory
git reset --soft <commit>

# Deshace los commits, el staging y los cambios en el working directory
git reset --hard <commit>

# Deshace los cambios en el area de preparación, sin afectar el working directory
git reset [--mixed] HEAD

# Deshace los 3 últimos commits, eliminando el staging y el working directory
git reset --hard HEAD~3
git revert
Se utiliza para deshacer uno o varios commits existentes creando un nuevo commit que revierte los cambios introducidos por los commits especificados. A diferencia de git reset, que reescribe el historial de commits, git revert crea nuevos commits para deshacer los cambios de los commits especificados, lo que significa que no elimina la historia existente.

# Revertir uno o varios commits
git revert <id_commit1> <id_commit2>

# Revertir un solo commit
git revert HEAD
git status
Se utiliza para mostrar el estado actual del repositorio de trabajo, incluyendo información sobre los archivos modificados, los archivos de staging y el estado de la rama local en relación con el nuevo repositorio remoto.

git status
