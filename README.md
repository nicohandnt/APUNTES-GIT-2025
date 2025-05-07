# ¿Que es git?

Git es un sistema de control de versiones, gratuito y de código abierto, diseñado por Linus Torvalds, el creador de Linux.

Git se convirtió en un sistema confiable a la hora de mantener versiones de aplicaciones con una gran base de código, así  se ha establecido como el sistema a de control de versiones mas usado en el mundo de la programación y el desarrollado software.

## CLASE 1

### ¿Cómo iniciar un proyecto de git?
Se crea un repositorio local con:

``git init <nombre-del-proyecto> ``

O iniciar en una carpeta ya existente , simplemente ir raíz del proyecto y poner.

`git init`

Con esto ya tendriamos una rama principal por defecto, suele llamarse master pero ya ha sido muy hablado el cambio de su nombre a main por el gusto de muchos usuarios, en un futuro podria llegar a ser ese nombre por defecto.

### Ayuda en git
Para resolver dudas de comandos de git, usamos:

`` git init -h``

si queremos información mas detallada podemos entrar a un articulo de git a través del navegador por medio de :

``git init --help``

### Estados de git
Cualquier archivo dentro de un directorio con git debe pasar por 3 estados:

+ **Modified**
+ **Staged**
+ **Commited**
------------------
**Modified**

Estado encargado de marcar todos los cambios que tiene un archivo sin confirmar.

Al crear un archivo dentro del directorio de git ya esta en un estado modified, también lo estará cuando lo eliminemos 

###### COMANDO PARA ELIMINAR ARCHIVO

``git rm <nombre-del-archivo>``

##### COMANDO PARA VER EL ESTADO DEL GIT

``git status``

##### COMANDO PARA RESTAURAR ARCHIVO
``git restore <nombre-del-archivo>``

**Staged**

Después de crear el archivo, debemos marcarlo para prepararlo para su confirmación en el repositorio 

##### COMANDO PARA CONFIRMAR
``
git add <nombre-del-archivo>
``

**Commited**

Este estado es para guardar los cambios de nuestro archivo, es decir es cuando nuestro archivo ya esta grabado en el repositorio local

##### COMANDO PARA GUARDAR CAMBIOS

``git commit <nombre-del-archivo>`` 

Para no tener que abrir el editor de codigo 

``git commit -m <el-mensaje-del-commit>”``

##### COMANDO PARA VER HISTORIAL DE COMMITS

``git log``

Para solo ver los títulos de los commits, sin autor ni fecha se usa

``git log --oneline``

para ver los commits como graficos utiilzamos

``git log –graph`` 

se puede combinar en un solo comando

``git log –graph –oneline``

## CLASE 2
### ¿Que es una rama?
Una rama es simplemente una versión de la colección de
directorios y archivos del repositorio. Cada vez que se crea
una nueva rama, se crea una copia de la colección de los archivos actuales.

##### COMANDO PARA CREAR UNA RAMA

``git Branch <mi-primera-rama>
``
##### COMANDOS PARA CAMBIAR DE RAMA

``git switch <mi-primera-rama>``

``git checkout <mi-primera-rama>``

para crear una rama y cambiar a ella con un solo comando se usa:

``git switch -c <mi-primera-rama>``

##### COMANDO PARA VER  LAS RAMAS

Para ver las ramas locales

``git branch``

Pare ver todas las ramas, locales y remotas 

``git Branch -a``

##### COMANDO PARA FUSIONAR RAMAS

Sirve para unir los cambios de una rama a la rama en la que nos situamos

``git merge``

##### COMANDO PARA ELIMINAR RAMAS

Se eliminan ramas para mantener el lugar de trabajo más organizado

``git Branch –d <mi-primera-rama>``

Para borrar una rama sin importar si esta fusionada o no

``git Branch -D <mi-primera-rama>``

### Conflictos

Se produce conflictos cuando git no es capaz de determinar que cambio es el que tiene que quedarse cuando fusionen las ramas, por lo que el usuario tiene que resolver

Para arreglarlo podemos elegir los cambios de que rama mantenemos o también personalizarlo para mantener los cambios de ambos pero en distintas líneas.

## CLASE 3

### ¿Que es Github?
Es un servicio de alojamiento en la nube de código fuente basado en el control de versiones de git para manejar repositorios.

Todo esto nace por que el mantenimiento que un servidor de este tipo requiere puede ser muy costoso y, en raras ocasiones, puede valer la pena.

### ¿Que son los repositorios remotos?
Los repositorios remotos son repositorios que están hospedados en un servidor
y que servirá de punto de sincronización entre diferentes repositorios locales.

***ORIGIN.-***
Este será el nombre de la rama remota, es predeterminado pero cuando trabajemos con mas ramas remotas podrán tener otros nombres.

##### COMANDO PARA ENLAZAR REPOSITORIO LOCAL AL REMOTO

``git remote add origin <url-de-repositorio-remoto>”``

La url puede ser la https o ssh

###### COMANDO PARA VER SI SE CONECTO EL REMOTO CON EL LOCAL 

``git remote -v``

##### COMANDO PARA SINCRONIZAR EL LOCAL CON EL REMOTO

``git push origin main``


##### COMANDO QUE NO SE DEBE HACER

``git push -f origin main``

Esto eliminaría archivos del repo remoto, muy peligroso si trabajamos en equipo

##### COMANDO PARA CLONAR REPOSITORIO
Se clonan todos los archivos y ramas del repositorio remoto con:

``git clone <url-de-repositorio-remoto>``

###### COMANDO PARA CREAR RAMA REMOTA

``git push origin <nombre de-la-rama-creada>``

###### COMANDO PARA ACTUALIZAR RAMAS

``git fetch``

##### COMANDO PARA ELIMINAR RAMAS DEL REPOSITORIO REMOTO EN MI REPOSITORIO LOCAL

``git remote prune origin``

#### GIT PUSH

Llevar modificaciones de mi repositorio local a uno remoto

#### GIT PULL

Traer modificaciones del repositorio remoto a mi repositorio local