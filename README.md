# roger_skyline

## Installation de la VM
-> dans sgoinfre car manque de place
-> telechargement des paquets sudo et mise dans le groupe sudo de edbaudou
-> ajout du path /usr/sbin a $PATH

## Configuration du reseau
-> creation d'un reseau avec la machine hote sans DHCP puis activation d'une deuxieme carte reseau logique
-> config de la carte dans /etc/network/interfaces
auto enp0s8
iface enp0s8 inet static
adress 192.168.0.2
netmask 255.255.255.252

## Configuration SSH
-> Fichier de configuration dans /etc/ssh/sshd_confg:
Port attribue, identification par PK seulement

## Configuration du firewall
3 types de tables : filter (defaut), nat(pour paquets creant nvl connexion), mangle (pour alteration de paquets) et raw (pour paquets ne devants pas être vérifiés par le systeme de filtrage)
#### Concernant filter, il y a 3 types de CHAINES (INPUT, FORWARD, OUT)
-> Mise en place des regles:
Creer un script de configuration d'iptables a mettre dans /etc/network/if-pre-u-p.d
1/ Flush de toutes les regles existantes (iptables -F puis -X)
2/ Bloquer toutes les connections des 3 chaines de filter
3/ ouvrir pour les ports ssh, http et https
4/ ouvrir pour interface locale
5/ activer le LOG pour INPUT
6/ limiter le nombre de connection parallele pour une meme IP et limiter le nombre d'IP connectees totales
