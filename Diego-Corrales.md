# Diferencias entre git merge y git merge --no-ff

## ¿Que es git merge?

En git el comando **git merge** se utiliza para integrar o fusionar los cambios realizados
de una rama con otra.
Una ves realizada esta union se pueden presentar 2 situaciones:

1. Fast-forward merge (merge de avance rápido)
2. Un 3-way merge (merge a tres bandas).

En esta ocacion nos interesara lo que es Fast-forward merge (merge de avance rapido).

Un Fast-forward merge se da cuando al realizar un merge entre 2 ramas (en nuestro ejemplo "master" y "feature") en la rama master no se haya realizado ningun commit luego de la creacion de la rama feature, en este caso el **HEAD** de master es antepasado de la rama feature, entonces al realizar el merge no se crea un commit merge adicional, sino que el **HEAD** de master se junta al **HEAD** de feature.

Un ejemplo visual: 

![Duck](https://bit.ly/2xYriSE)

El problema de hacer esto es que no se deja constancia de que se hizo una union de otra rama con la rama master, lo que impite tener una documentacion del desarrollo del proyecto.

## ¿Que es git merge --no--ff?

Es el comando que se utiliza para realizar un merge sin *fast forward*, es decir, si en la rama master no se a realizado ningun commit luego de la creacion de la rama feature y se ejecuta este comando especificando que no se realice un *fast forward* entonces se realizara un commit adicional (commit merge) y de esta forma dejar constancia de la existencia de la rama feature ya que el **HEAD** de master pasa a estar en el nuevo commit merge.

Ejemplo grafico: 
![Duck](https://bit.ly/2VLZsCc)

## Conclusiones

La diferencia entre *git merge* y *git merge --no--ff* es dejar constancia de las ramas que se crearon durante el proyecto y de esta forma ver cuando se unio los cambios de distintas ramas.
git merge realiza un *fast forward*, en cambio con git merge --no--ff se especifica que no se realice dicha accion y de esta forma se deja constancia de la existencia de una rama.
