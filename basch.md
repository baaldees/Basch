# Bash

## Introduction

BASH est l'acronyme de Bourne-Again shell.

C'est un interpréteur en ligne de commande (implémentation de sh)

La première ligne du fichier ("Shebang"):

    `#!/bin/bash`

ou

    `#!/usr/bin/env bash`

L'extention de fichier est par convention `.sh`

* Pour rendre le fichier exécutable faite :

    `chmod +x le_nom_du_fichier.sh`

* Pour exécuter le fichier :

    `./le nom_du_fichier.sh`

## Un premier script

Créer un fichier<u> mon_premier_script.sh</u> contenant :

    `#!/bin/bash`

    `echo "Mon premier script Basch"`

puis faite

    `chmod +x mon_premier_script.sh`

pour exécuter le script

    `./mon_premier_script.sh`

## Les commentaires

`# ceci est une ligne de commentaire`

## Les variables

    `#!/bin/bash`

    `variable= "Une chaine de caractères !"`

    `echo "Ma chaine $variable`

## Les entrées utilisateur

### Invite

    `echo -n "une chaine`

    `read CHAINE`
  
    `echo "Votre chaine : $CHAINE"`

## TP1

### Créer un script qui demande à l'utilisateur de saisir son nom pour ensuite le saluer avec celui-ci.

    `#!/bin/bash`
    `echo -n "Quel est votre prénom : "`
    `read chaine``echo "Bonjour $chaine comment allez-vous ? "`

![lengend] photo

## Les condistions

##### Le `if`

    `if [[ $SAISI == "yes" ]]; then`

    `echo "C'est un grand oui !!" `

    `else` `echo "C'est non.. :( "`

    `fi`

### Opérateurs pratiques :

-f : tester l'existence d'un fichier

-d : tester l'existence d'un répertoire

-z : tester si une chaine est vide

-r / -w : tester si un fichier est accessible en lecture / écriture


## Comparaison de nombre

| [[ ]] | | (( )) |
| --- | --- | --- |
| -eg | == | est égal |
| -ne | !=  | n'est pas égal à |
| -gt | >   | est plus grand que |
| -ge | >=  | est plus grand ou égal à |
| -lt | <   | est plus petit que |
| -le | <=  | est plus petit ou égal à |

Exemple

![legen]

##### Le `fi`

En Bash, le mot-clé "fi" est utilisé pour marquer la fin d'une structure de contrôle "if".

"fi" est simplement "if" écrit à l'envers.

TP2

Créer un script BASH qui demande un nombre à l'utilisateur et indique si celui est inférieur à 10 ou pas.

    #!/bin/bash

    read -p "Veuillez saisir un nombre :" saisi

    if (( $saisi < 10 )); then echo "Le nombre saisi est inférieur à 10."
    
    else 
        echo "Le nombres saisi est superieur à 10"fi

PHOTO TP_2 ![legend]

Les opérateurs logiques

ET : &&

OU: ||

    `if [[ ( $1 == "mode" && $2 == "debug" ) ]]; then`

          `echo "en mode debug"`

    `fi`

Les parenthèses doubles `(( ))` pour une évaluation arithmétique :

    `sum=$(( $saisi + $var))`

## TP2 Bis

Ajuster le script du TP2 pour qu'il indique désormais si le nombre est compris entre 10 et 20.

    `#!/bin/bash`

    `read -p "Veuillez saisir un nombre :" saisi`

    `if (( $saisi >= 10 && $saisi <=20 )); then`

        `echo "Le nombre saisi est entre le nombre 10 et 20 ."`

    `else`

          `echo "Le nombres saisi n'est pas entre 10 et 20"`   

    `fi`

photo tp_2bis .
![legeng]

Les arguments

`echo "Nombre d'arguments : $#`

`echo "Premier arguments : $1`

`echo "deuxième arguments : $2`

$ ./arguments.sh "première chaine" "et l'autre"

## TP3

Créer un script qui a pour but la création d'un dossier. Le nom du dossier est passé en paramètre, le demander si ce n'est pas le cas. Indiquer si le dossier a bien été créé ou si ce dernier existait déjà.

    `#!/bin/bash`

    `if (( $# == 0 )); then`

        `read -p "Saisir le nom du dossier à créer : " dossier`

    `else`

        `dossier="$1"`
    `fi`

    `if [ -d "$dossier" ]; then`

         `echo "le dossie '$dossier' existe déja"`

    `else`

         `mkdir "$dossier"`

          `echo "le dossier '$dossier' est créé"`

    `fi`

photo tp_3
