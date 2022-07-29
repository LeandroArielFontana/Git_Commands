Comandos Basicos de Git
=============

>Estos son algunos comandos basicos sacados del curso de Git y GitHub de Platzi.

![](https://img.shields.io/github/stars/pandao/editor.md.svg) ![](https://img.shields.io/github/forks/pandao/editor.md.svg) ![](https://img.shields.io/github/tag/pandao/editor.md.svg) ![](https://img.shields.io/github/release/pandao/editor.md.svg) ![](https://img.shields.io/bower/v/editor.md.svg)

## ------ Shorcuts Basicos de Git Bash ------


- `Ctrl + L` : <left>***Realiza un clean en la consola***</left>

- `Ctrl + Insert` : <left>***Realiza una copia de lo seleccionado en la consola***</left>

- `Shift + Insert` : <left>***Pega lo copiado previamente en la consola***</left>

## ------ Comandos Basicos de Git Bash ------

- `pwd` : <left>***Indica la carpeta en la cual estas ubicado en el bash***</left>

- `cd` : <left>***Cambiar de directorio (change directory)***</left>

- `cd 'ubicacion_de_directorio'`: <left>***Cambia al directorio especificado***</left>

- `ls` : <left>***Lista a todos los archivos***</left>

- `ls -al` : <left>***Lista los archivos ocultos***</left>

- `gitk` : <left>***Abre una interfaz y muestra la historia de todas las ramas`***</left>

- `mkdir 'nombre_de_la_carpeta'` : <left>***Crea una carpeta con el nombre indicado***</left>

- `touch 'nombre_del_archivo'.'extension_del_archivo'` : <left>***Crea un archivo con el nombre y la extension indicada***</left>

- `cat 'nombre_del_archivo'` : <left> ***Muestra el contenido del archivo indicado***</left>

- `history` : <left>***Muestra una lista numerada con los comandos usados***</left>

- `! 'numero_de_comando'` : <left>***Repite el comando de la lista de history (Sin espacios)`***</left>

- `rm 'nombre_del_archivo'` : <left>***Borra el archivo <i>CUIDADO PORQUE SE PUEDE BORRAR EL DISCO! (en lo posible no usar)</i>***</left>

- `rm --help` : <left>***Muestra las instrucciones de cada comando***</left>

- `code` : <left>***Abre el Visual Studio Code***</left>

- `git init` : <left>***Crea el repositorio local en la carpeta en donde se esta parado***</left>

- `git status` : <left>***Muestra el status de los archivos***</left>

- `git add 'nombre_del_archivo'` : <left>***Pone el archivo preparado para commitear***</left>

- `git add .` : <left>***Coloca a todos los archivos preparados para commitear***</left>

- `git rm 'nombre_del_archivo'` : <left>***Saca el archivo para ser commiteado***</left>

- `git rm --cached 'nombre_del_archivo'` : <left>***Saca el cache del archivo***</left>

- `git config` : <left>***Muestra la configuracion general que tenemos en Git***</left>

- `git config --list` : <left>***Muestra mas detalladamente la configuracion que tenemos en nuestro Git***</left>

- `git show` : <left>***Muestra los cambios que se realizaron sobre una rama***</left>

- `git diff 'numero_de_commit1' 'numero_de_commit2'` : <left>***Muestra las diferencias entre 2 commits***</left>

- `git reset 'numero_de_commit' --hard` : <left>***Nos permite volver a una version anterior (es el mas comun entre el hard y el soft)***</left>

- `git log --stat` : <left>***Muestra los cambios especificos que se hicieron en cada commit***</left>

- `git commit -am` :<left>***Agrega y commitea los cambios hechos a archivos que tienen un commit previamente***</left>

- `git branch 'nombre_de_la_rama'` : <left>***Crea una rama a partir de la rama en la que estoy parado / tambien podemos ver las ramas disponibles que tenemos***</left>

- `git checkout 'nombre_de_la_rama'` :  <left>***Se posiciona en una rama especifica***</left>

- `git remote add origin 'link_del_repositorio'` : <left>***Agrega el repositorio remoto***</left>

## -------------- SSH KEY --------------

- `ssh-keygen -t rsa -b 4096 -C "youremail@example.com"` : <left>***Crea una SSH Key***</left>

- `eval $(ssh-agent -s)` : <left>***Ejecuta una llave***</left>

- `ssh-add ~/.ssh/id_rsa` : <left>***AGREGAR LA LLAVE PRIVADA!, NO LA QUE ES .pub !!!!***</left>

- `git remote set-url origin` : <left>***Cambia la url del repositorio***</left>

 <center>***Desp en GitHub / GitLab agregar la SSH Key***</center>

## ------ Comandos de Reportes --------

- `git log --all` : <left>***Muestra todos los commits que hicimos en nuestra historia***</left>

- `git log --all --graph` : <left>***Muestra una ramificacion con los logs mas grafica***</left>

- `git log --all --graph --oneline` : <left>***Muestra toda la historia del proyecto desde que arranco mas comprimida***</left>

- `alias xNombre="git log --all --graph --oneline"` : <left>***Poner un alias para un comando en especifico***</left>

- `git tag` : <left>***Muestra la lista de todos los tags***</left>

- `git tag -a v0.1 -m "'comentario'" 'numero_de_commit' ` : <left>***Crea un tag con el -a y se lo asignamos a un commit en especifico***</left>

- `git show-ref --tags` : <left>***Muestra cuales son los tags y aclara a que commit estan enlazados especificamente***</left>

- `git push origin --tags` : <left>***Enviamos al repositorio los tags creados***</left>

- `git tag -d 'nombre del tag'` : <left>***Elimina el tag localmente***</left>

- `git push origin :refs/tags/'nombre del tag'` : <left>***Elimina el tag de manera remota***</left>

- `git show-branch` : <left>***Nos muestra las ramas que existen y su historia tambien puede ser especificado con un --all***</left>

- `git clean --dry--run` : <left>***Elimina las copias exactas de archivos que tenemos***</left> 

- `git clean -f` : <left>***Elimina las copias exactas de archivos que tenemos***</left> 

- `git cherry-pick 'nroCommit'` : <left>***Trae un commit de una rama a otra***</left>

- `git reflog` : <left>***Muestra todos los cambios a lo largo de la historia del git***</left>

- `git commit --amend` : <left>***Los cambios que esten en staggin van al ultimo commit***</left> 

- `git grep 'busqueda'` : <left>***Busca en la rama la palabra clave***</left>

- `git grep -n 'busqueda'` : <left>***Busca en la rama la palabra clave y da la ubicacion exacta***</left>

- `git grep -c 'busqueda'` : <left>***Hace el conteo de cuantas veces se usa la palabra clave***</left>

- `git log -S 'busqueda'` : <left>***Busca entre los commits hechos la palabra clave***</left>

- `git shortlog -sn` : <left>***Muestra un conteo de los commits hechos en la rama***</left>

- `git shortlog -sn --all` : <left>***Muestra un conteo de los commits hechos en las ramas***</left>

- `git shortlog -sn --all --no-merges` : <left>***Muestra un conteo de los commits hechos en la rama sin merges***</left>

- `git config --global alias.stats "shortlog -sn --all --no-merges"` : <left>***Crea un comando especifico se usaria git stats en este caso***</left>

- `git blame 'nombre_del_archivo"` : <left>***Muestra quien hizo los cambios en un archivo especifico***</left>

- `git blame -c 'nombre_del_archivo"`: <left>***Muestra quien hizo los cambios en un archivo especifico mas detalladamente***</left>

- `git blame 'nombre_del_archivo" -L'nro1,nro2'` : <left>***Muestra quien hizo los cambios en un archivo especifico entre ese rango de lineas especificas***</left>

