<div align="center">

<img src="https://git-scm.com/images/logos/downloads/Git-Logo-White.svg" width="180" alt="Git Logo">

# Referencia de Comandos Git

> Guía completa de comandos Git en español, para tener siempre a mano.

![Git](https://img.shields.io/badge/Git-2.x-orange?style=flat-square&logo=git&logoColor=white)
![Idioma](https://img.shields.io/badge/Idioma-Espa%C3%B1ol-blue?style=flat-square)
![Licencia](https://img.shields.io/badge/Licencia-MIT-green?style=flat-square)

</div>

---

## Índice

- [⌨️ Atajos de teclado](#️-atajos-de-teclado)
- [🖥️ Comandos de terminal](#️-comandos-de-terminal)
- [⚙️ Configuración de Git](#️-configuración-de-git)
- [📁 Repositorios locales](#-repositorios-locales)
- [🌿 Ramas](#-ramas)
- [☁️ Repositorios remotos](#️-repositorios-remotos)
- [🔐 Claves SSH](#-claves-ssh)
- [🏷️ Tags](#️-tags)
- [🔧 Herramientas avanzadas](#-herramientas-avanzadas)
- [📊 Reportes y estadísticas](#-reportes-y-estadísticas)

---

## ⌨️ Atajos de teclado

Atajos útiles para trabajar en **Git Bash**:

| Atajo | Descripción |
|-------|-------------|
| `Ctrl + L` | Limpia la consola |
| `Ctrl + Insert` | Copia lo seleccionado |
| `Shift + Insert` | Pega lo copiado |

---

## 🖥️ Comandos de terminal

Muestra el directorio en el que estás parado:

```shell
pwd
```

Cambiar de directorio (sin argumentos, va al directorio home):

```shell
cd
```

Cambiar a un directorio específico:

```shell
cd 'ubicacion_del_directorio'
```

*Ejemplo:*
```shell
cd Documentos/mi-proyecto
cd C:/Users/usuario/Desktop/proyecto
```

Listar archivos visibles:

```shell
ls
```

Listar todos los archivos incluyendo ocultos:

```shell
ls -a
```

Listar con todos los detalles (permisos, tamaño, fecha):

```shell
ls -al
```

Crear una carpeta:

```shell
mkdir 'nombre_de_la_carpeta'
```

*Ejemplo:*
```shell
mkdir mi-proyecto
mkdir src/components
```

Crear un archivo:

```shell
touch 'nombre_del_archivo.extension'
```

*Ejemplo:*
```shell
touch index.html
touch styles.css
touch src/app.js
```

Ver el contenido de un archivo:

```shell
cat 'nombre_del_archivo'
```

*Ejemplo:*
```shell
cat README.md
cat src/index.js
```

Ver el historial de comandos usados:

```shell
history
```

Repetir un comando del historial por su número:

```shell
!'numero_de_comando'
```

*Ejemplo:* Si en el historial el número 42 es `git push origin main`, escribir `!42` lo ejecuta de nuevo.

Eliminar un archivo (⚠️ **usar con precaución**):

```shell
rm 'nombre_del_archivo'
```

*Ejemplo:*
```shell
rm archivo-viejo.txt
```

Ver la ayuda de cualquier comando:

```shell
'comando' --help
```

*Ejemplo:*
```shell
git commit --help
rm --help
```

Abrir Visual Studio Code en la carpeta actual:

```shell
code .
```

---

## ⚙️ Configuración de Git

Ver toda la configuración activa de Git:

```shell
git config --list
```

Configurar el nombre de usuario global:

```shell
git config --global user.name "Tu Nombre"
```

*Ejemplo:*
```shell
git config --global user.name "Juan Perez"
```

Configurar el email global:

```shell
git config --global user.email "tuemail@ejemplo.com"
```

*Ejemplo:*
```shell
git config --global user.email "juan@gmail.com"
```

Crear un alias para un comando largo:

```shell
git config --global alias.'nombre_alias' "comando_git"
```

*Ejemplo:* Crear `git hist` para ver el historial gráfico compacto:
```shell
git config --global alias.hist "log --all --graph --oneline"
```
A partir de ahí se puede usar simplemente `git hist`.

---

## 📁 Repositorios locales

Inicializar un repositorio en la carpeta actual:

```shell
git init
```

Ver el estado de los archivos (modificados, staged, sin seguimiento):

```shell
git status
```

Agregar un archivo al staging area:

```shell
git add 'nombre_del_archivo'
```

*Ejemplo:*
```shell
git add index.html
git add src/login.js
```

Agregar todos los archivos al staging area:

```shell
git add .
```

Sacar un archivo del staging area sin perder los cambios:

```shell
git rm --cached 'nombre_del_archivo'
```

*Ejemplo:* Útil si agregaste por error un archivo que no debía ir en el commit:
```shell
git rm --cached passwords.txt
git rm --cached .env
```

Eliminar un archivo del repositorio:

```shell
git rm 'nombre_del_archivo'
```

*Ejemplo:*
```shell
git rm archivo-viejo.txt
```

Hacer un commit con mensaje:

```shell
git commit -m "descripcion de los cambios"
```

*Ejemplo:*
```shell
git commit -m "agrega formulario de contacto"
git commit -m "corrige error en la pantalla de login"
git commit -m "actualiza dependencias"
```

Agregar cambios y commitear en un solo paso (solo archivos con seguimiento):

```shell
git commit -am "descripcion de los cambios"
```

*Ejemplo:*
```shell
git commit -am "ajusta estilos del header"
```

Agregar cambios al último commit sin crear uno nuevo:

```shell
git commit --amend
```

Ver diferencias entre el working directory y el staging area:

```shell
git diff
```

Ver diferencias entre dos commits:

```shell
git diff 'numero_de_commit_1' 'numero_de_commit_2'
```

*Ejemplo:*
```shell
git diff a1b2c3d e4f5g6h
```

Ver los cambios del último commit:

```shell
git show
```

Ver historial de commits:

```shell
git log
```

Ver historial con detalle de archivos modificados:

```shell
git log --stat
```

Ver historial compacto en forma gráfica:

```shell
git log --all --graph --oneline
```

*Ejemplo de salida:*
```
* a1b2c3d (HEAD -> main) agrega formulario de contacto
* e4f5g6h corrige error en login
| * 9z8y7x6 (feature/nueva-pantalla) agrega pantalla de perfil
|/
* 1a2b3c4 primer commit
```

Volver al estado de un commit anterior (descarta todos los cambios posteriores):

```shell
git reset 'numero_de_commit' --hard
```

*Ejemplo:*
```shell
git reset a1b2c3d --hard
```

Volver al estado de un commit pero mantener los cambios en staging:

```shell
git reset 'numero_de_commit' --soft
```

*Ejemplo:*
```shell
git reset a1b2c3d --soft
```

Ver todo el historial incluyendo resets y cambios borrados:

```shell
git reflog
```

Guardar cambios temporalmente sin necesidad de hacer commit:

```shell
git stash
```

Recuperar los cambios guardados en el stash:

```shell
git stash pop
```

*Ejemplo de flujo típico del stash:*
```shell
# Estás trabajando en algo, pero tenés que cambiar de rama urgente
git stash              # guardás los cambios temporalmente
git checkout main      # cambiás de rama sin perder nada
# hacés lo que tenías que hacer...
git checkout feature/login
git stash pop          # recuperás tus cambios donde los dejaste
```

---

## 🌿 Ramas

Ver todas las ramas locales:

```shell
git branch
```

Crear una nueva rama:

```shell
git branch 'nombre_de_la_rama'
```

*Ejemplo:*
```shell
git branch feature/login
git branch fix/error-en-formulario
```

Crear una nueva rama y moverse a ella directamente:

```shell
git checkout -b 'nombre_de_la_rama'
```

*Ejemplo:*
```shell
git checkout -b feature/nueva-pantalla
```

Moverse a una rama existente:

```shell
git checkout 'nombre_de_la_rama'
```

*Ejemplo:*
```shell
git checkout main
git checkout feature/login
```

Fusionar una rama con la rama actual:

```shell
git merge 'nombre_de_la_rama'
```

*Ejemplo:* Para incorporar los cambios de `feature/login` a `main`:
```shell
git checkout main
git merge feature/login
```

Eliminar una rama (solo si ya fue fusionada):

```shell
git branch -d 'nombre_de_la_rama'
```

*Ejemplo:*
```shell
git branch -d feature/login
```

Ver el historial de ramas con sus commits:

```shell
git show-branch --all
```

Traer un commit específico de otra rama a la rama actual:

```shell
git cherry-pick 'numero_de_commit'
```

*Ejemplo:*
```shell
git cherry-pick a1b2c3d
```

Abrir interfaz visual de ramas:

```shell
gitk
```

---

## ☁️ Repositorios remotos

Clonar un repositorio remoto en tu máquina:

```shell
git clone 'url_del_repositorio'
```

*Ejemplo:*
```shell
git clone https://github.com/usuario/mi-repositorio.git
git clone git@github.com:usuario/mi-repositorio.git
```

Agregar un repositorio remoto:

```shell
git remote add origin 'url_del_repositorio'
```

*Ejemplo:*
```shell
git remote add origin https://github.com/usuario/mi-repo.git
```

Ver los repositorios remotos configurados:

```shell
git remote -v
```

Cambiar la URL del repositorio remoto:

```shell
git remote set-url origin 'nueva_url'
```

*Ejemplo:* Para cambiar de HTTPS a SSH:
```shell
git remote set-url origin git@github.com:usuario/mi-repo.git
```

Subir los cambios al repositorio remoto:

```shell
git push origin 'nombre_de_la_rama'
```

*Ejemplo:*
```shell
git push origin main
git push origin feature/login
```

Bajar los cambios del remoto y fusionarlos automáticamente:

```shell
git pull origin 'nombre_de_la_rama'
```

*Ejemplo:*
```shell
git pull origin main
```

Bajar los cambios del remoto sin fusionar (para revisarlos antes):

```shell
git fetch
```

---

## 🔐 Claves SSH

Generar una nueva clave SSH:

```shell
ssh-keygen -t rsa -b 4096 -C "tuemail@ejemplo.com"
```

*Ejemplo:*
```shell
ssh-keygen -t rsa -b 4096 -C "juan@gmail.com"
```

Iniciar el agente SSH:

```shell
eval $(ssh-agent -s)
```

Agregar la clave privada al agente (⚠️ agregar el archivo **sin** `.pub`):

```shell
ssh-add ~/.ssh/id_rsa
```

> **Paso final:** copiar el contenido del archivo `.pub` y pegarlo en GitHub o GitLab en **Settings → SSH and GPG Keys → New SSH Key**.

---

## 🏷️ Tags

Ver todos los tags del repositorio:

```shell
git tag
```

Crear un tag en un commit específico:

```shell
git tag -a v1.0 -m "descripcion del tag" 'numero_de_commit'
```

*Ejemplo:*
```shell
git tag -a v1.0 -m "primera version estable" a1b2c3d
git tag -a v2.0 -m "agrega sistema de usuarios" e4f5g6h
```

Ver a qué commit está asociado cada tag:

```shell
git show-ref --tags
```

Subir los tags al repositorio remoto:

```shell
git push origin --tags
```

Eliminar un tag localmente:

```shell
git tag -d 'nombre_del_tag'
```

*Ejemplo:*
```shell
git tag -d v0.1
```

Eliminar un tag del repositorio remoto:

```shell
git push origin :refs/tags/'nombre_del_tag'
```

*Ejemplo:*
```shell
git push origin :refs/tags/v0.1
```

---

## 🔧 Herramientas avanzadas

Ver quién modificó cada línea de un archivo:

```shell
git blame 'nombre_del_archivo'
```

*Ejemplo:*
```shell
git blame index.html
git blame src/login.js
```

Igual, con mejor formato visual:

```shell
git blame -c 'nombre_del_archivo'
```

Ver blame de un rango de líneas específico:

```shell
git blame 'nombre_del_archivo' -L 'linea_inicio,linea_fin'
```

*Ejemplo:* Ver quién escribió las líneas 10 a 25 de un archivo:
```shell
git blame index.html -L 10,25
```

Buscar una palabra clave en los archivos del repositorio:

```shell
git grep 'busqueda'
```

*Ejemplo:*
```shell
git grep "login"
git grep "TODO"
```

Buscar con el número de línea donde aparece:

```shell
git grep -n 'busqueda'
```

*Ejemplo:*
```shell
git grep -n "console.log"
```

Contar cuántas veces aparece la palabra clave:

```shell
git grep -c 'busqueda'
```

*Ejemplo:*
```shell
git grep -c "import"
```

Buscar una palabra en el historial de commits:

```shell
git log -S 'busqueda'
```

*Ejemplo:* Ver todos los commits donde se agregó o eliminó la palabra "password":
```shell
git log -S "password"
```

Simular qué archivos se eliminarían con `git clean` (sin borrar nada):

```shell
git clean --dry-run
```

Eliminar archivos sin seguimiento del repositorio:

```shell
git clean -f
```

---

## 📊 Reportes y estadísticas

Ver todos los commits del proyecto:

```shell
git log --all
```

Ver historial de commits con gráfico de ramas:

```shell
git log --all --graph
```

Ver historial compacto, una línea por commit:

```shell
git log --all --graph --oneline
```

Ver cuántos commits hizo cada persona:

```shell
git shortlog -sn
```

*Ejemplo de salida:*
```
    42  Juan Perez
    17  Maria Garcia
     5  Carlos Lopez
```

Igual, incluyendo todas las ramas:

```shell
git shortlog -sn --all
```

Sin contar los commits de merge:

```shell
git shortlog -sn --all --no-merges
```

---

<div align="center">

📄 También hay disponible una **[Guía Práctica en PDF](Guía%20Práctica%20De%20Uso%20De%20Git%20Con%20Github.pdf)** en este repositorio con más detalles.

<br>

*Basado en el curso de Git y GitHub de Platzi.*

</div>
