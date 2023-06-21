## Ce script est pour installer :
- SUDO
- DATE
- UPDATE
- UPGRADE
- APACHE
- MySQL
- PHP
- NFS
- SSH
- NMAP
- ZIP
- DNSUTILS
- NET-TOOLS
- TZDATA
- LYNX
- GIT
- SCREEN
- LOCATE
- NCDU
- WEBMIN

#SCRIPT

#!/bin/bash

  #Fonction d'installation de SUDO
install_sudo() {
    echo "Installation de SUDO..."
    apt-get install -y sudo
}

#Fonction d'installation de DATE
install_date() {
    echo "Installation de DATE..."
    date
}

#Fonction d'installation d'Apache
install_apache() {
    echo "Installation d'Apache..."
    apt-get install -y apache2
}

#Fonction d'installation de MySQL
install_mysql() {
    echo "Installation de MySQL..."
    apt-get install -y mysql-server
}

#Fonction d'installation de PHP
install_php() {
    echo "Installation de PHP..."
    apt-get install -y php libapache2-mod-php php-mysql
}

#Fonction d'installation de NFS
install_nfs() {
    echo "Installation de NFS..."
    apt-get install -y nfs-kernel-server
}

#Fonction d'installation de SSH
install_ssh() {
    echo "Installation de ssh..."
    apt-get install -y ssh
}


#Fonction d'installation de UPDATE
install_update() {
    echo "Installation de UPDATE..."
    apt-get update
}

#Fonction d'installation de UPGRADE
install_upgrade() {
    echo "Installation de UPGRADE..."
    apt-get upgrade -y
}

#Fonction d'installation de NMAP
install_nmap() {
    echo "Installation de NMAP..."
    apt-get install -y nmap
}

#Fonction d'installation de ZIP
install_zip() {
    echo "Installation de ZIP..."
    apt-get install -y zip
}

#Fonction d'installation de DNSUTILS
install_dnsutils() {
    echo "Installation de DNSUTILS..."
    apt-get install -y dnsutils
}

#Fonction d'installation de NET-TOOLS
install_net_tools() {
    echo "Installation de NET-TOOLS..."
    apt-get install -y net-tools
}

#Fonction d'installation de TZDATA
install_tzdata() {
    echo "Installation de TZDATA..."
    apt-get install -y tzdata
}

#Fonction d'installation de LYNX
install_lynx() {
    echo "Installation de LYNX..."
    apt-get install -y lynx
}

#Fonction d'installation de GIT
install_git() {
    echo "Installation de GIT..."
    apt-get install -y git
}

#Fonction d'installation de SCREEN
install_screen() {
    echo "Installation de SCREEN..."
    apt-get install -y screen
}

#Fonction d'installation de LOCATE
install_locate() {
    echo "Installation de LOCATE..."
    apt-get install -y locate
}

#Fonction d'installation de NCDU
install_ncdu() {
    echo "Installation de NCDU..."
    apt-get install -y ncdu
}

#Fonction d'installation de WEBMIN
install_webmin() {
    echo "Installation de WEBMIN..."
    wget http://prdownloads.sourceforge.net/webadmin/webmin_1.981_all.deb
    dpkg -i webmin_1.981_all.deb
    apt-get install -y -f
    apt-get install -y winbind samba
}

#Fonction pour afficher le menu
afficher_menu() {
    echo "Veuillez sélectionner les services à installer :"
    echo "1. SUDO"
    echo "2. DATE"
    echo "3. update"
    echo "4. upgrade"
    echo "5. Apache"
    echo "6. MySQL"
    echo "7. PHP"
    echo "8. NFS"
    echo "9. SSH"
    echo "10. NMAP"
    echo "11. ZIP"
    echo "12. DNSUTILS"
    echo "13. NET-TOOLS"
    echo "14. TZDATA"
    echo "15. LYNX"
    echo "16. GIT"
    echo "17. SCREEN"
    echo "18. LOCATE"
    echo "19. NCDU"
    echo "20. WEBMIN"
    echo "21. Quitter"
}

#Fonction pour vérifier si le menu doit être réaffiché
verifier_reaffichage_menu() {
    echo "Voulez-vous revenir au menu ? (o/n)"
    read choix
    if [ "$choix" = "o" ] || [ "$choix" = "O" ]; then
        afficher_menu
        lire_choix
    else
        echo "Sortie du script."
        exit
    fi
}

#Fonction pour lire le choix de l'utilisateur
lire_choix() {
    read -ra choices
    for choice in "${choices[@]}"; do
        case $choice in
            1) install_sudo ;;
            2) install_date ;;
            3) install_update ;;
            4) install_upgrade ;;
            5) install_apache ;;
            6) install_mysql ;;
            7) install_php ;;
            8) install_nfs ;;
            9) install_ssh ;;
            10) install_nmap ;;
            11) install_zip ;;
            12) install_dnsutils ;;
            13) install_net_tools ;;
            14) install_tzdata ;;
            15) install_lynx ;;
            16) install_git ;;
            17) install_screen ;;
            18) install_locate ;;
            19) install_ncdu ;;
            20) install_webmin ;;
            21) echo "Sortie du script." ; exit ;;
            *) echo "Option invalide : $choice" ;;
        esac
    done

    echo "L'installation est terminée."
    verifier_reaffichage_menu
}

#Affichage initial du menu
afficher_menu
lire_choix
