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

---

## Flujos de trabajo remoto

Para clonar un repositorio remoto

`git clone [url]`

El proceso es:

`git add .`

`git commit -m "Mensaje"`

Para enviar al repositorio remoto

`git push`

Para traer una actualización del repositorio remoto a mi local

`git fetch`

Para que se vean los cambios en mis archivos es necesario hacer merge del origin

`git merge origin/[master ó main]`

Para hacer los dos al mismo tiempo fetch y merge

`git pull`

---

### Ramas

master ---> c1 ---> c2 (HEAD)

Si nos movemos a un commit anterior se muestra asi

master ---> c1(Detached HEAD) -> c2

Creamos una rama

`git branch resume`

Para ver el ultimo commit y donde esta apuntando el HEAD

`git show`

Para moverme a la nueva rama

`git checkout resume`

Modificamos el archivo y agregamos los cambios

`git add -am 'Mensaje'`

Para ver los ultimos cambios

`git log`

Vemos que el HEAD esta ahora en nuestro nuevo commit pero master esta debajo.

Hacemos 2 cambios en la rama nueva y hacer commit

Hacemos 2 cambios en la rama de master o main y hacer commit

Nos cambiamos a la rama master

`git checkout [master o main]`

Hacemos merge

`git merge [rama nueva]`

Si hay conflictos se solucionan y se hace un commit nuevamente.

Nota: Surgen conflictos cuando dos personas escriben codigo en la misma linea. Entonces hay que decidir que código se va quedar al final.

Para ver la fusion y los cambios en la rama master

`git log`

Cuando quieres hacer un git push de una rama que creaste en local y mandarlo al repositorio remoto

`git push --set-upstream origin [name-branch]`

---

## Uso de Github

### Importante: Github cambio el nombre de la rama principal de `master` a `main` por cuestiones de racismo y discriminación.

1.- Crear una cuenta en github

2.- Crear un nuevo repositorio

Readme es buena practica ponerlo para explicar el repositorio

-Raw muestra el texto plano
-Blame quien hizo el commit
-History la historia del archivo

3.- Clone or download para clonar o descargar

---

Para agregar un origen remoto a nuestro proyecto en local

`git remote add origin [URL]`

Para ver los remotos

`git remote`

Para ver los remotos verbal

`git remote -v`

Para quitar un remote

`git remote remove [name-or-origin]`

Para enviarlo al remoto

`git push origin main`

Si el repositorio remoto tiene archivos primero hay que traer los datos y luego hacer push.

`git pull origin main`

Para forzar la fusion del repo remoto y local si no se permite por las historias que son diferentes

`git pull origin main --allow-unrelated-histories`

`git push origin main`

Ya se guardo todo en remoto!

Para traer los cambios del remoto

`git pull origin main`

---

## Llaves publicas y privadas

- Las llaves públicas son llaves que permiten cifrar un mensaje. Estas llaves se pueden compartir con cualquier persona y no importa ya que solo sirven para cifrar.

- Las llaves privadas son llaves que permiten descifrar mensajes cifrados con la llave pública. Esta llave tiene que guardarse en un lugar seguro ya que permitiría abrir cualquier mensaje cifrado. Está llave no debe compartirse con nadie.

### Para configurar el SSH

Primero recordamos nuestra configuración actual

`git config -l`

Para cambiar el email

`git config --global user.email "tuemail@gmail.com"`

Para crear nuestra llave SSH

Hay que estar en el home de tu maquina

`ssh-keygen -t rsa -b 4096 -C "your_email@example.com"`

Y damos enter para guardarse y ya tenemos las 2 llaves. Sin frases

Para agregar las key al ssh-agent

`eval "$(ssh-agent -s)"`

Si el archivo config no existe ~/.ssh/config los creamos

`touch ~/.ssh/config`

Para abrir y editar

`open ~/.ssh/config`

Y agregamos el contenido

`Host * `

`AddKeysToAgent yes`

`IdentityFile ~/.ssh/id_rsa`

Para añadir la identidad privada

`ssh-add [direccion/.ssh/id_rsa]`

NOTA: Ahora vamos a github en settings y agregamos nuestra llave publica

Ahora vamos a cambiar nuestro repositorio remoto origin

Para ver la lista de repositorios remotos

`git remote -v`

Para sobrescribir el origin

`git remote set-url origin [MI-URL-SSH-DESDE-GITHUB]`

Luego hacemos un cambio en algun archivo y subimos. Ya esta conectado.

## Tags y versiones

Para visualizar mejor los merge

`git log --all --graph`

`git log --all --graph --decorate --oneline`

Crear un alias temporal para mejorar la legibilidad

`alias arbolito="git log --all --graph --decorate --oneline"`

Formato

`alias shortName="your custom command here"`

Si deseas quitar el alias

`alias [name-alias]`

Crear un tag

`git tag -a v0.1 -m "Resultado de las primeras clases" [hash_commit]`

Ver los tags que tenemos

`git tag`

Para ver que commit esta conectado un tag

`git show-ref --tags`

Los tags son utiles en github para referencia interna

Para enviar los tags

`git push origin --tags`

Si creamos un tag que no nos gusta

`git tag -a dormido -m "Lo que sea" [hash-commit]`

`git push origin --tags`

Si quiero borrar el tag dormido

`git tag -d dormido`

Para actualizar en github

`git push origin --tags`

Para ver si se borro

`git tag`

Pero si gue ahi y hay que borrarlo de una manera especial

`git push origin :refs/tags/dormido`

Y ya se borro por completo

## Ramas en Github

Para cambiar de rama

`git checkout [nombre-rama]`

Cuales son las ramas e historias

`git show-branch --all`

Para ver de manera visual las ramas, pero ya no funciona :(

`gitk`

Para ver ramas y en cual estamos

`git branch`

### Crear ramas

Para crear ramas

`git branch [nombre-rama]`

`git push origin [nombre-rama]`

Para cambiar de rama

`git checkout [nombre-rama]`

### Proceso de trabajo

Para clonar un proyecto de Github

`git clone [URL-project]`

Hacemos un cambio al proyecto y commit

`git commit -am "Mi primer commit"`

`git pull origin master`

`git push origin master`

NOTA: Es importante que hay que agregar al colaborador al repositorio para que pueda realizar cambios.

### Flujo de trabajo profesional

- Rama Master -> Producción versión final

- Rama Staging develop -> Server de prueba similar a producción. El lider del equipo debe siempre tener actualizado el develop desde master.

- Cuando creamos un feature en una nueva rama y hacemos los cambios -> Enviamos los cambios a la rama develop -> Por medio de un Pull Request para que lo revisen -> Si es aprobado se aprueba y se hace merge en la rama develop.

Si todo paso bien en staging. Procedemos a hacer pull request a la rama master.

- Pull request -> Estado intermedio entre un merge. Esto es una caracteristica exclusiva de Github.

- Merge request -> Asi se llama en Gitlab

- Push request -> Asi se llama en Bitbucket

La persona encargada de esto es el DevOps o lider de equipo.

### El flujo cuando es parte del equipo

1. Cambios en la rama X
2. Cuando vamos a fusionar los cambios terminados de la rama X vamos a movernos a la rama principal master o main.

- `git checkout [master-o-main]`

  3.Luego hacemos merge

- `git merge [ramaX]`

Y listo.

### Flujo cuando alguien no es parte del equipo

1. Hacemos cambios en una rama X
2. El admin del repositorio va a Github y mirá que hay cambios nuevos en la otra rama. Se mueve a master y desde master le da click en Crear Pull Request.
3. Una vez creado se agregan los comentarios y se asignan revisores.
4. El revisor puede aprobar o solicitar cambios a la rama para poder aceptar el pull request.
5. Una vez aceptado el pull request se fusiona la rama X con la rama master.
6. Al final podemos eliminar la rama X ya que no será de utilidad.

### Flujo cuando alguien está fuera de la empresa. Opensource

Nota: NO es coloborador y es un repositorio público.

Watch: Me llegan notificaciones del proyecto
Star: Agregamos el repositorio a nuestros favoritos y como si fuera me gusta.
Fork: Se crea una copia en nuestro repositorio

Los pasos son:

0. Vamos al repositorio open source

1. Fork(Bifurcación) : Creamos una copia del estado actual

2. Traemos el proyecto a nuestro local

`git clone [URL-REPO-FORKEADO]`

3. Abrimos un archivo y lo modificamos

`git commit -am "Cambios que hicimos"`

4. Subimos al repo en Github

`git push`

5. Verificamos nuestro repositorio en Github y tenemos los cambios arriba.

6. Github sabe que tenemos forkeado el proyecto y sabe que hay una diferencia. Damos click en `New pull re quest`

7. Me abre una interfaz donde podemos comparar los 2 repositorios para ver que cambio. Podemos elegir las ramas a comparar. Damos click en `Create pull request`

8. Es como hacer un commit, titulo y mensaje de contribución. Click en `Crear pull request`. Y el pull request ha sido creado.

9. Hay que esperar que se apruebe o se rechaze.

### Otro proceso es parte del dueño del proyecto

1. Me llega una notifiación de pull request.

2. Se ve la pantalla que una persona quiere agregar cambios al proyecto con titulo y mensaje. Además podemos ver los commits y archivos que cambiaron.

Si vemos que los cambios son correctos podemos aprobar los cambios.

Click en `review changes` y `Approve` y `OK`

3. Damos click en `Merge pull request`

4. Ya se realizo los cambios

### Si el open source tiene cambios adelante del fork

Desde la consola

1. Checamos nuestros remote

`git remote -v`

Vamos que origin apunta nuestro repositorio forkeado

2. Asi que tenemos que tener un link directo al proyecto original

`git remote add upstream [URL-REPO-ORIGINAL]`

Vemos que existe una nueva fuente de datos

`git remote -v`

3. Hacemos un git pull desde el master o main

`git pull upstream main`

Asi traemos todos los cambios

4. Ahora hacemos un commit

`git commit -am "Fusion"`

5. Ahora enviamos a nuestro repo forkeado en Github

`git push origin main`

6. Verificamos que tenemos todos los cambios de repositorio original.

## Deploy en el servidor

1. Entrar al servidor

2. Instalamos git

3. Traemos nuestro repositorio

`git clone [URL]`

4. Listo
