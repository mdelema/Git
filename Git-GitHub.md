## Configuración Inicial

```ssh
	$ git config --global user.name [ej: "Nom_User"] --> Nombre de los Commits
	$ git config --global user.email [ej: "Nom_User"@gmail.com] --> Configurar Email
	$ git config --global color.ui true --> Marco de colores para los comando
```

## Crear e Iniciar Repositorio

```ssh
	$ mkdir "Test_Repo" -----> Crea un directorio local, para alojar el proyecto.
	$ cd "Test_Repo" --------> Muevete hasta él
	$ git init --------------> Para iniciar GIT en el directorio.
	$ echo "cualquier texto" > README.md ---> Crea el 1er Archivo para alojar.
```

## Crear, Cambiar o Eliminar 1 Repositorio Remoto: git remote

```ssh
	$ git remote add origin [ej: https://github.com/user/"Test_Repo".git] --> Agrega 1 repo remoto (con https)
	$ git remote add origin [ej: git@github.com:user/"Test_Repo".git] ------> Agrega 1 repos remoto (con ssh) Para ello debemos configurar ssh en github
	$ git remote add upstream [ej: https://github.com/user/"Test_Repo".git]-> Agregar el repositorio original como un repositorio upstream

	$ git remote set-url origin <url> --> Cambiar de Repo remoto
	$ git remote rm <name/origin> ------> Elimina el Repo remoto
	$ git remote rm upstream -----------> Eliminar el repositorio upstream
	$ git remote -v --------------------> Muestra lista repositorios
	$ git remote show origin -----------> Muestra los branches remotos
	$ git remote prune origin ----------> Limpiar todos los branches eliminados
```

## Crear Repositorio local a partir de un Repo Remoto: git clone

```ssh
	$ git clone [ej: https://github.com/user/"Test_Repo".git] --> con https
	$ git clone [ej: git@github.com:user/"Test_Repo".git] ------> con ssh
```

## Subir archivos o cambios al repositorio: git add / git commit / git push

```ssh
	$ git add . ------------> Añade todos los archivos al commit
	$ git add "Archivo" ----> Añade solo ese "Archivo" al commit
	$ git add --all --------> Añade todos los archivos para el commit omitiendo los nuevos
	$ git add *.txt --------> Añade todos los archivos con la extensión especificada
	$ git add docs/*.txt ---> Añade todos los archivos dentro de un directorio y de una extensión especifica
	$ git add docs/ --------> Añade todos los archivos dentro de un directorios
	$ git add -p "Archivo" -> Commit por Partes. Te mostrará los cambios que hiciste. Con "y" aceptas, con "n" cancelas, con "?" ves info y con "q" salis.

	$ git commit -m "Nombre_Commit" -----> "-m" para especificar el msj de los cambios
	$ git commit -a -m "Nombre_Commit" --> Agrega y Carga en el HEAD los cambios realizados
	$ git commit -a ---------------------> De haber conflictos los muestra
	$ git commit --amend -m -------------> Agregar al ultimo commit, este no se muestra como un nuevo commit en los logs. Se puede especificar un nuevo mensaje

	$ git push -------------------------------> Envía los cambios al repo.
	$ git push -u origin <rama> --------------> Si tu rama fue creada recientemente.
	$ git push --set-upstream origin <rama> --> Puede que la tengas que cargar
	$ git push --tags ------------------------> Subimos un tag
```

## Bajar cambios del repositorio remoto: git pull

```ssh
	$ git pull --> Estando dentro del directorio
	$ git pull origin <nameBranch> --> Busca los cambios nuevos y actualiza el repositorio
	$ git branch --set-upstream-to=origin/main main --> Si da error
```

## Bajar cambios y fusionarlos manualmente: git fetch / git merge

```ssh
	$ git fetch ---------------> Verifica cambios en el repositorio online con el local
	$ git fetch upstream ------> Buscar el repositorio

	$ git merge origin/main --->
	$ git merge upstream/main -> Fusionar enviar cambios. Luego git push origin main
```

## Para ver Cambios: git diff

```ssh
	$ git diff ----------> Muestra los cambios realizados a un archivo
	$ git diff --staged -> 
```

## Ver los LOGs y Errores: git log

```ssh
	$ git log -------------------> Muestra los logs de los commits
	$ git log --oneline --stat --> Muestras los cambios en los commits
	$ git log --oneline --graph -> Muestra graficos de los commits
```

## Ver los TAGs: git tag

```ssh
	$ git tag ---> Muestra una lista de todos los tags
	$ git tag -a <verison> - m "esta es la versión x" --> Crea un nuevo tags

```

## Deshacer commit´s: git reset HEAD

```ssh
	$ git reset HEAD <archivo> ------> Saca un archivo del commit
	$ git reset --soft HEAD^ --------> Devuelve el ultimo commit que se hizo y pone los cambios en staging
	$ git reset --hard HEAD^ --------> Devuelve el ultimo commit y todos los cambios
	$ git reset --hard HEAD^^ -------> Devuelve los 2 ultimo commit y todos los cambios
	$ git reset --hard <commit_sha> -> Rollback merge/commit
```


# RAMAS: git branch / git checkout 

```ssh
	$ git branch -M main
	$ git branch "Nueva_Rama" ------> Crear nueva rama
	$ git branch -------------------> Ver las Ramas
	$ git branch -d "Nueva_Rama" ---> Elimina la rama lo une al master. Comprueba si no hay commit's pendientes y de lo contrario no la borra 
	$ git branch -D "Nueva_Rama" ---> Fuerza el eliminado de la rama
	
	$ git checkout -b "Nueva_Rama" -> Cerar nueva rama y saltar a ella 
	$ git checkout "Nueva_Rama_2" --> Cambiar de rama
	$ git checkout <file> --> Quita del HEAD un archivo y le pone el estado de no trabajado
	$ git checkout -b newlocalbranchname origin/branch-name --> Crea un branch en base a uno online
	
	$ git merge "Nueva_Rama" -------> Fusiona las Ramas. Desde a la rama master(o main)

	$ git push origin "Nueva_Rama" -> Subir la rama al repositorio  
	$ git push origin :"Nueva_Rama"-> Para elimiar del repositorio remoto también

	$ git log --graph --decorate --online --all --> Ver el historial de las ramas
```

## Hacer que las ramas se pongan al día con el master sin afectar al mismo: git rebase

```ssh
	git rebase --------------> Une la rama actual con el mastar, esto no se puede ver como un merge	
	git rebase --continue ---> cuando resolvemos los conflictos --continue continua la secuencia del rebase donde se pauso
	git rebase --skip -------> Omite el conflicto y sigue su camino
	git reabse --abort ------> Devuelve todo al principio del rebase
	git rebase <nameBranch> -> Para hacer un rebase a un branch en especifico
```

## Referenciar Issues desde un Commit

```ssh	
	$ git add .
	$ git commit -a  --> Dentro del commit indicar el número de Issues al que queremos hacer referencia, ej: Prueba #1.
	> Con eso, tendremos el Issues #1, un link al commit asociado.
	$ git push origin "main"
```

## Cerrar Issues desde un Commit

```ssh
	$ git add .
	$ git commit -a  --> Dentro del commit, luego del comentario de edición, indicar el Issues a cerrar, colocando Closes
	> ej: Closes #1.
	$ git push origin "main"
```


## OTROS COMANDOS

```ssh
	$ git gc -----------> Recolector de basura. Obliga a git a borrar toda la basura que nos halla quedado
	$ git status -------> Lista un estado actual del repositorio con lista de archivos modificados o agregados
	$ git rm <archivo> -> Borrar un archivo del repositorio	 
	$ git remote add upstream <url> --> Descargar remote de un fork
	$ git fetch upstream -------------> Merge con master de un fork
	$ git merge upstream/master 
```

