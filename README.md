# CURSOS - GitHub & GitLab

# Create a new repository on the command line
$ echo "# master" >> README.md
$ git init
$ git add README.md
$ git commit -m "first-commit"
$ git branch -M main
$ git remote add origin git@github.com:mdelema/master.git
$ git push -u origin main

# Push an existing repository from the command line
$ git remote add origin git@github.com:mdelema/master.git
$ git branch -M main
$ git push -u origin main

# RAMAS 
%% Ver en que rama estamos
$ git brunch "Nueva_Rama"

%% Crear nueva rama 
$ git branch "Nueva_Rama"

%% Cerar nueva rama y saltar a ella 
$ git checkout -b "Nueva_Rama"

%% Cambiar de rama 
$ git checkout "Nueva_Rama

%% Eliminar una rama
$ git brunch -d "Nueva_Rama"

%% Hacer merge desde la master %%
$ git checkout master
$ git merge "Nueva_Rama"

%% Saber si hay conflictos  
$ git status

%% Para eliminar el repositorio remoto
$ git push origin :"Nueva_Rama"

