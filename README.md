![](https://git-scm.com/images/logos/downloads/Git-Logo-White.svg)

Comandos Basicos de Git
=============

> Estos son algunos comandos basicos sacados del curso de Git y GitHub de Platzi.

![](https://img.shields.io/github/stars/pandao/editor.md.svg) ![](https://img.shields.io/github/forks/pandao/editor.md.svg) ![](https://img.shields.io/github/tag/pandao/editor.md.svg) ![](https://img.shields.io/github/release/pandao/editor.md.svg) ![](https://img.shields.io/bower/v/editor.md.svg)

## ------ Shorcuts Basicos de Git Bash ------

- `Ctrl + L` : <left>***Realiza un clean en la consola***</left>

- `Ctrl + Insert` : <left>***Realiza una copia de lo seleccionado en la consola***</left>

- `Shift + Insert` : <left>***Pega lo copiado previamente en la consola***</left>

## ------ Comandos Basicos de Git Bash ------

Mostrar la configuracion general que tenemos en Git:

````shell
git config
````

Mostrar más detalladamente la configuracion que tenemos en nuestro Git:

````shell
git config --list
````

Indica la carpeta en la cual estás ubicado en el bash:

````shell
pwd
````

Cambiar de directorio (si se coloca vacio, te posiciona en el home):

````shell
cd
````

Cambiar a un directorio especificado:

````shell
cd 'ubicacion_de_directorio'
````

Listar a todos los archivos visibles:

````shell
ls
````

Listar a todos los archivos tanto visibles como los ocultos:

````shell
ls -a
````

Listar a todos los archivos tanto visibles como los ocultos con datos mas especificos:

````shell
ls -al
````

Abrir una interfaz (git kraken), una de las funcionalidades es mostrar la historia de todas
las ramas:

````shell
gitk
````

Crea una carpeta con el nombre indicado:

````shell
mkdir 'nombre_de_la_carpeta'
````

Crear un archivo con el nombre y la extension indicada:

````shell
touch 'nombre_del_archivo'.'extension_del_archivo'
````

Mostrar el contenido del archivo indicado:

````shell
cat 'nombre_del_archivo'
````

Para mostrar una lista numerada con los comandos usados, se utiliza el siguiente comando:

````shell
history
````

Repetir comando de la lista de history (Sin espacios):

````shell
!'numero_de_comando'
````

Borra el archivo ¡CUIDADO PORQUE SE PUEDE BORRAR EL DISCO! (en lo posible no usar):

````shell
rm 'nombre_del_archivo'
````

Muestra las instrucciones de cada comando:

````shell
rm --help
````

Abrir Visual Studio Code (de tenerlo instalado en el equipo):

````shell
code
````

## ------ Manejo de Repositorios con Git ------

Crear el repositorio local en la carpeta en donde se está parado:

````shell
git init
````

Mostrar el status de los archivos:

````shell
git status
````

Pone el archivo preparado para commitear:

````shell
git add 'nombre_del_archivo'
````

Colocar a todos los archivos preparados para commitear:

````shell
git add .
````

En caso de querer agregar solo archivos especificos:

````shell
git add 'nombre_del_archivo'
````

Saca el archivo para ser commiteado:

````shell
git rm 'nombre_del_archivo'
````

Sacar el cache de un archivo:

````shell
git rm --cached 'nombre_del_archivo'
````

Muestra los cambios que se realizaron sobre una rama:

````shell
git show
````

Muestra las diferencias entre 2 commits:

````shell
git diff 'numero_de_commit1' 'numero_de_commit2'
````

Volver a una version anterior (es el más comun entre el hard y el soft):

````shell
git reset 'numero_de_commit' --hard
````

Muestra los cambios especificos que se hicieron en cada commit:

````shell
git log --stat
````

Agregar y commitear los cambios hechos a archivos que tienen un commit previamente:

````shell
git commit -am
````

Crear una rama a partir de la rama en la que estoy parado:

````shell
git branch -v 'nombre_de_la_rama'
````

Podemos ver las ramas disponibles que tenemos:

````shell
git branch 
````

Posicionarse en una rama específica:

````shell
git checkout 'nombre_de_la_rama'
````

Agregar un repositorio remoto:

````shell
git remote add origin 'link_del_repositorio'
````

## -------------- SSH KEY --------------

Crear una SSH Key:

````shell
ssh-keygen -t rsa -b 4096 -C 'youremail@example.com'
````

Ejecutar una llave:

````shell
eval $(ssh-agent -s)
````

AGREGAR LA LLAVE PRIVADA!, NO LA QUE ES .pub !!!!`:

````shell
ssh-add ~/.ssh/id_rsa
````

Cambiar la url del repositorio:

````shell
git remote set-url origin
````

***Desp en GitHub / GitLab agregar la SSH Key***

## ------ Comandos de Reportes --------

Muestra todos los commits que hicimos en nuestra historia:

````shell
git log --all
````

Muestra una ramificación con los logs más gráfica:

````shell
git log --all --graph
````

Muestra toda la historia del proyecto desde que arranco más comprimida:

````shell
git log --all --graph --oneline
````

Poner un alias para un comando en específico:

````shell
alias 'nombre_del_alias'= git log --all --graph --oneline
````

Mostrar una lista de todos los tags:

````shell
git tag
````

Crea un tag con el -a y se lo asignamos a un commit en específico:

````shell
git tag -a v0.1 -m "'comentario'" 'numero_de_commit'
````

Muestra cuáles son los tags y aclara a que commit están enlazados específicamente:

````shell
git show-ref --tags
````

Enviar al repositorio los tags creados:

````shell
git push origin --tags
````

Eliminar el tag localmente:

````shell
git tag -d 'nombre del tag'
````

Elimina el tag de manera remota:

````shell
git push origin :refs/tags/'nombre_del_tag'
````

Nos muestra las ramas que existen y su historia también puede ser especificado con un --all:

````shell
git show-branch
````

Eliminar las copias exactas de archivos que tenemos:

````shell
git clean --dry--run
````

O bien también podemos usar:

````shell
git clean -f
````

Trae un commit de una rama a otra (recordar que cada commit tiene como un "ID" unico):

````shell
git cherry-pick 'numero_de_commit'
````

Mostrar todos los cambios a lo largo de la historia del git:

````shell
git reflog
````

Los cambios que esten en staging van al último commit:

````shell
git commit --amend
````

Buscar en la rama la palabra clave:

````shell
git grep 'busqueda'
````

Busca en la rama la palabra clave y da la ubicación exacta:

````shell
git grep -n 'busqueda'
````

Hacer el conteo de cuantas veces se usa la palabra clave:

````shell
git grep -c 'busqueda'
````

Busca entre los commits hechos la palabra clave:

````shell
git log -S 'busqueda'
````

Mostrar un conteo de los commits hechos en la rama:

````shell
git shortlog -sn
````

O también podemos tener más datos con:

````shell
git shortlog -sn --all
````

Mostrar un conteo de los commits hechos en la rama sin merges:

````shell
git shortlog -sn --all --no-merges
````

Crea un comando específico se usaria 'git stats' en este caso:

````shell
git config --global alias.stats "shortlog -sn --all --no-merges"
````

Mostrar quien hizo los cambios en un archivo específico:

````shell
git blame 'nombre_del_archivo'
````

Mostrar quien hizo los cambios en un archivo específico más detalladamente:

````shell
git blame -c 'nombre_del_archivo'
````

Mostrar quien hizo los cambios en un archivo específico entre ese rango de líneas específicas:

````shell
git blame 'nombre_del_archivo' -L 'nro1,nro2'
````
