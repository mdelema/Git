# CURSOS - GitHub & GitLab

# Crear repositorio desde la linea de comandos
$ mkdir "Test_Repo"
$ cd "Test_Repo"
$ git init
$ echo "texto cualquiera para" > README.md

# Añadir archivos al repositorio: git add / git commit
$ git add README.md
$ git status
$ git commit -m "first-commit" --> "-m" para especificar el msj de los cambios

# Crear repositorio Remoto
$ git remote add origin https://github.com/mdelema/......git --> con https
$ git remote add origin git@github.com:mdelema/..........git --> con ssh
<En caso de ya estar creado>
$ git remote add origin https://github.com/mdelema/"Test_Repo".git --> con https
$ git remote add origin git@github.com:mdelema/"Test_Repo".git ------> con ssh. Para ello debemos configurar ssh en github

# Crear un repositorio local a partir del repo remoto.
$ git clone https://github.com/mdelema/"Test_Repo".git --> con https
$ git clone git@github.com:mdelema/"Test_Repo".git ------> con ssh

# Subir cambios al repositorio remoto: git push 
$ git push -u origin <rama> --> sea main(principal) o cualquiera secundaria
$ git push --set-upstream origin <rama> 

# Bajar cambios del repositorio remoto: git pull
"Estando dentro de la carpeta"
$ git pull
"Si da error"
$ git branch --set-upstream-to=origin/main main
$ git log

# Bajar los cambios y fusionarlos manualmente: git fetch y git merge
$ git fetch
$ git merge origin/main

# RAMAS 

>> Crear nueva rama  
$ git branch "Nueva_Rama"

>> Cerar nueva rama y saltar a ella 
$ git checkout -b "Nueva_Rama"

>> Ver las Ramas
$ git branch

>> Cambiar de rama 
$ git checkout "Nueva_Rama

>> Subir rama al repositorio  
$ git push origin "Nueva_Rama"
$ echo "Vamos a ver que sale" > Prueba.txt
$ git add Prueba.txt
$ git commit -m 'Añadimos archivo de prueba a la Nueva Rama'
$ git push origin "Nueva_Rama"

>> Fusionar las Ramas: git merge
$ git checkout main
$ git merge "Nueva_Rama"

>> Eliminar una rama
$ git brunch -d "Nueva_Rama" --> comprueba si no hay commit's pendientes y de lo contrario no la borra 
$ git brunch -D "Nueva_Rama" --> Fuerza el borrazo de la rama
> Para elimiar del repositorio remoto tambièn"
$ git push origin :"Nueva_Rama"

>> Ver el historial de las ramas
$ git log --graph --decorate --online --all

