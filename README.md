# roger_skyline

## Installation de la VM
-> dans sgoinfre car manque de place
-> telechargement des paquets sudo et mise dans le groupe sudo de edbaudou
-> ajout du path /usr/sbin a $PATH

## Configuration SSH
-> Fichier de configuration dans /etc/ssh/sshd_confg:
Port attribue, identification par PK seulement

## Configuration du firewall
-> Telechargement de iptables-persistent pour rendre permanente les regles
-> Mise en place des regles:
1/ Flush de toutes les regles existantes (iptables -F puis -X)
2/ 
