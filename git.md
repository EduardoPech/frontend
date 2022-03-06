# Git

### ¿Por qué usar un sistema de control de versiones?

Git es un sistema de control de versiones creado por Linus Torvalds para manejar las distribuciones de Linux inicialmente.

### Comandos básicos

Para iniciar el sistema control de versiones

`git init`

Para agregar los archivos al staging(estado donde se guardan temporalmente).

`git add miArchivo.txt`

Para guardar los cambios de los archivos que se encuentran en el staging. También se agrega un comentario al final para saber que cambios hicimos en ese commit.

`git commit -m ‘Mi comentario’`

Para ver el estado de los archivos

`git status`

Para mostrar información del ultimó commit.

`git show`

Para enviar los cambios a un repositorio remoto

`git push`

Para traer los ultimos cambios desde un repositorio remoto

`git pull`

Para clonar un proyecto

`git clone [nombre del proyecto]`

Agregar configuración global

`git config --global user.name "Eduardo Pech"`

`git config --global user.email nombre@micorreo.com`

Agregar configuración local

`git config --local user.name "Eduardo Pech"`

`git config --local user.email nombre@micorreo.com`
