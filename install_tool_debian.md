#!/bin/bash

# Fonction pour installer les outils requis
install_tools() {
    echo "Installation des outils requis..."
    sudo apt-get update

    # Liste des outils à installer
    tools=("sudo" "date" "update" "upgrade" "apache2" "mysql-server" "php" "nfs-common" "openssh-server" "nmap" "zip" "dnsutils" "net-tools" "tzdata" "lynx" "git" "screen" "locate" "ncdu">

    for tool in "${tools[@]}"
    do
        echo "Installation de $tool..."
        sudo apt-get install $tool -y
        echo "$tool installé avec succès."
    done

    echo "Tous les outils ont été installés avec succès."
}

# Appel de la fonction pour installer les outils
install_tools


