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

# Practica Repositorio

### Configurar nuestro git con nuestros datos

Para ver nuestra configuración

`git config -- list`

Para configuraración global

`git config --global user.name "Eduardo Pech"`

`git config --global user.email "eduardopech.web@gmail.com"`

### Init GIT

Crear un repositorio

`git init`

Ver archivo oculto de git

`ls -al`

Creas un archivo con texto

`touch archivo.txt`

Para ver estado de git

`git status`

Agregarlo al staging

`git add archivo.txt`

Para quitarlo del staging

`git rm --cached archivo.txt`

Para enviarlo al repositorio

`git add archivo.txt`

`git commit -m "Escribir el mensaje"`

Revisar el estado

`git status`

### Corregir algo en el archivo

Modificamos el archivo y guardamos cambios

`git add archivo.txt`

Ó para agregar todos

`git add .`

`git commit -m "Cambios hechos"`

Para ver los cambios

`git log archivo.txt`

Nota: El commit tienen un numero que es el ID y esta en el head->master

---

Para ver los cambios por dentro

`git show archivo.txt`

Se agrega un nuevo cambio al archivo

`git add .`

`git commit -m "Mensaje del nuevo cambio"`

Se agrega otro nuevo cambio al archivo

`git add .`

`git commit -m "Mensaje del nuevo cambio"`

Ver cambios

`git show`

Ver cambios de un archivo entre archivo

`git diff [id_commit] [id_commit]`

## Proceso

`git init`

### Working Directory -> Mi carpeta -> unstracked

`git add [archivo]`

### Staging Area -> Espacio en memoria -> Track

`git commit -m "Mensaje"`

### .git directory(Repository) -> master

---

## Ramas Branches

---

### Master v1 v2 v3 v-actual

### Experimentos(development) v2 -> v3 -v4 -> Merge -> To Master

### Hotfix -> Cambio -> Merge -> To master

Nota: Puede haber conflictos al hacer merge

---

Para ver los cambios

`git log`

Para regresar a un commit y mantiene en staging los ultimos cambios.

`git reset [id_commit]`

Regresar al estado anterior pero mantiene el staging de los ultimos cambios que se hicieron commit.

`git reset [id_commit] --soft`

Para regresar al estado anterior y elimina los cambios realizados en los commits anteriores

`git reset [id_commit] --hard`

Para ver cambios especificos en el archivo

`git log --stat`

Para ver como era el archivo antes

`git checkout [id_commit]`

muestra el ultimo commit

`git checkout master`

---

Para regresar a la version anterior

`git checkout [id_commit]`

Hago un cambio ahora en el archivo

`git add .`

`git commit -m "Hice un cambio"`

Para crear una rama de ese commit y no perder los cambios

`git branch <new-branch-name> [id_commit]`

Para cambiar de rama

`git checkout <name-branch>`

Para regresar a master

`git checkout master`

Elimina los archivos de nuestro repositorio local y del área de staging, pero los mantiene en nuestro disco duro

`git rm --cached [name-file]`

Elimina los archivos de Git y del disco duro

`git rm [name-file]`

Es lo mismo que:

`git rm --force [name-file]`

Quita un archivo del staging sin perder los cambios

`git restore --staged [name-file]`

Descarta los cambios del archivo

`git restore [name-file]`
