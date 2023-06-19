# Basch

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

`#!/bin/bash``echo -n "Quel est votre prénom : "``read chaine``echo "Bonjour $chaine comment allez-vous ? "`

![lengend] photo

## Les condistions

le `if`

`if [[ $SAISI == "yes" ]]; then`

`echo "C'est un grand oui !!" `

`else` `echo "C'est non.. :( "`

`fi`

## Comparaison de nombre

[[ ]] (( ))

|  | |  |
| --- | --- | --- |
| -eg | == | est égal |
| -ne | !=  | n'est pas égal à |
| -gt | >   | est plus grand que |
| -ge | >=  | est plus grand ou égal à |
| -lt | <   | est plus petit que |
| -le | <=  | est plus petit ou égal à |
