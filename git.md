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

Para mostrar información del ultimó commit y parte de los cambios en el código.

`git show`

Para mostrar el historial del archivo

`git log [nombre del archivo]`

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

# Linea de comandos

Mostrar directorio actual

`pwd`

Cambiar de directorio

`cd [carpeta]`

Regresar a carpeta anterior

`cd ..`

Regresar a home

`cd`

Listar archivos y carpetas

`ls`

Listar archivos y carpetas formateados

`ls -l`

Listar archivos y carpetas ocultos

`ls -a`

Listar archivos y carpetas formateados (incluido los ocultos)

`ls -la`

crear una carpeta

`mkdir [proyecto1]`

Ir a la carpeta

`cd proyecto1`

Crear archivos vacios

`touch archivo.txt`

Escribir texto en el archivo

`cat > archivo.txt`

Mostrar contenido de archivo

`cat archivo.txt`

Ver comandos escritos

`history`

Invocar numero de comando

`![numero]`

Borrar archivos

`rm archivo.txt`

Ver opciones del comando

`rm --help`

Limpiar la consola

`clear`
