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

# Crear una nueva rama
%% Ver en que rama estamos %%
$ git brunch "Nueva_Rama"

%% Crear nueva rama y saltar a ella %%
$ git checkuot -b "Nueva_Rama"

%% Para eliminar una rama %%
$ git brunch -d "Nueva_Rama"

%% Hacer merge desde la master %%
$ git checkout master
$ git merge "Nueva_Rama"

%% Saber si hay conflictos %% 
$ git status

