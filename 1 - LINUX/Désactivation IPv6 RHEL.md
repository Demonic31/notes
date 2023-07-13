# Désactivation IPv6 RHEL
## Méthode 1:

Édition du  /etc/sysctl.conf.

`vi /etc/sysctl.conf`

Rajouter la ligne suivante pour la désactivation d’IPv6 pour toutes les cartes réseaux.

`net.ipv6.conf.all.disable_ipv6 = 1`

Rajouter la ligne suivante pour désactiver IPv6 pour une carte réseau donnée par exemple ( eno16777736).

`net.ipv6.conf.eno16777736.disable_ipv6 = 1`

pour activer les modifications exécuter la commande suivante:

`sysctl -p`

## Méthode 2:

Création d’un fichier nommé  disableipv6.conf dans  /etc/sysctl.d.

`vi /etc/sysctl.d/disableipv6.conf`

Rajouter la ligne suivante pour la désactivation d’IPv6 pour toutes les cartes réseaux.

`net.ipv6.conf.all.disable_ipv6 = 1`

Rajouter la ligne suivante pour désactiver IPv6 pour une carte réseau donnée par exemple ( eno16777736).

`net.ipv6.conf.eno16777736.disable_ipv6 = 1`

Enfin vous devez rebooter la machine afin d’activer les modifications

`reboot`

[Source](https://ahmedkasmi.wordpress.com/2015/12/26/desactiver-ipv6-sur-centos-7-rhel-7/)