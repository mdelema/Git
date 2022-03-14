## Add your files

```ssh
    $ mkdir "Test_Repo"
    $ cd "Test_Repo"
    $ git remote add origin https://gitlab.com/user/"Test_Repo".git
    $ git branch -M main
    $ git push -uf origin main 
```

## Commit and execution

```ssh
    $ git add *                 # * para agregar todo
    $ git push                  # Actualiza los cambios y los deja prontos para cargar || si muestra este msj: "Everything up-to-date" hacer 2 veces "push y commit" (como aquí)
    $ git commit -m "comment"   # Realiza el commit, comenta sobre los cambios y pone a ejecutar la APP
    $ git push                  # Actualiza los cambios y los deja prontos para cargar
    $ git commit -m "comment"   # Realiza el commit, comenta sobre los cambios y pone a ejecutar la APP
```
