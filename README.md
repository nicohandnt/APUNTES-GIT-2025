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

##### COMANDO PARA ACORTAR EL GIT PUSH
Para solo poner git push en vez de repetir siempre el git push origin“nombre de rama”, tenemos que usar este comando

``git push -u origin <nombre-de-rama>``

##### COMANDO PARA ACORTAR EL GIT PULL

``git push –set-upstream origin “nombre de rama”``

Para pull no hay forma abreviada con -u

##### COMANDO PARA SUBIR TODAS LAS RAMAS AL REPOSITORIO REMOTO

``git push  --all``

##### COMANDO PARA BAJAR TODAS LAS RAMAS A MI REPOSITORIO LOCAL

``git pull --all`

### Pull request

Petición de cambios que se envía al repositorio local
Para hacer una buena pull request debemos enfocar nuestro código en una sola cosa y explicarla

### ¿Como hacer una buena PR?
- Enfocate en hacer tu codigo solo para una cosa, es mejor revisar y aceptar una PR que hace una cosa a otra que hace varias
- Explica tu PR, usar imagenes o videos que enseñen de forma interactiva la funcion del codigo añadido

### Revisar una PR
- Proporciona una retroalimentacion positiva.
- Se concreto y claro
- Comprende el contexto adecuado para arreglar o parchear codigo para que cumpla su cometido

## CLASE 4
### Git Flow

**Main .-** contiene el codigo de producción

**Develop.-** código de preproducción que debe ser probado y evaluado

**Feature.-** características nuevas para el proyecto

**Release.-** cambios de ultimo momento

**Hotfix.-** parches o arreglar bugs pequeños

### Github Flow

Es una estrategia creada por la propia GitHub y pensada especialmente para
equipos y proyectos que hacen despliegues de forma regular. Se basa en la
creación de Pull Requests que serán discutidas para que se integren en la rama
principal que siempre está actualizada con los cambios más recientes y preparada
para ser desplegada.

### Trunk Base Development
Es una estrategia que se basa en que el mayor tiempo de desarrollo se concentra
en una sola rama llamada trunk (tronco) que normalmente corresponderá con
main. Esto quiere decir que se evita la creación de ramas auxiliares y, sólo en
algunos casos que se requieran, se crean con un tiempo de vida muy limitado
(máximo un par de días).

Así que esta estrategia la podríamos resumir en: haz commit a main y hazlo lo
más frecuentemente posible con pequeños cambios. Y crea PRs pequeñas y
rápidas sólo cuando sea necesario.
¿Qué puede salir mal? Pues menos de lo que esperas si cuentas con un buen
sistema
de Integración y Despliegue Continuo (CI/CD).

### SHIP/SHOW/ASK

**Ship.-** se fusiona en la rama principal sin revisión previa

**Show.-** abre una petición de cambios para ser revisados y cuando son aceptados se fusionan inmediatamente

**Ask.-** abre una pull request para discutir cambios antes de fusionarlos

**Reglas de SHIP/SHOW/ASK**
- Tenemos un buen sistema de CI/CD, fiable y rápido, que hace que la rama
principal siempre sea desplegable y que evite que lleguen errores no
deseados a producción.

- Confiamos en el equipo y existen buenas prácticas de desarrollo. Pair
programming, mob programming, seniority... y, sobretodo, existe
responsabilidad. La persona se responsabiliza de decidir la categoría de su
cambio. Un gran poder, poder hacer merge de tus propias Pull Request,
conlleva una gran responsabilidad (no romper producción).
- Las revisiones de código no son requerimientos para que las PRs sean
fusionadas.

- Las ramas son lo más pequeñas posibles, tienen un tiempo de vida corto y
siempre salen directamente desde la rama principal.

- El equipo ha sabido lidiar con el ego individual, las personas confían en el
resto del equipo y las pruebas automáticas pasan. El equipo entiende que la
rama principal puede contener código sin terminar detrás de Feature Flags u
otros mecanismos similares.

## CLASE 5

**Buenas practicas**

Es un estándar manejado en la mayoría de equipos de desarrollo ara resolver conflictos durante su desarrollo

Hacer commits a menudo, agrupando pequeñas mejoras, no significa hacer commits sin sentido, hacer buenos commits, que sean claros y con buena semántica. Unos buenos commits no contienen puntos finales ni suspensivos, como máximo 50 caracteres para escribir el commit

También es bueno escribir un buen nombre de rama, preferible si el nombre de la rama es dado por la acción que realiza
