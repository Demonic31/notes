# Changement IP RHEL

En root

Lister les interfaces réseaux et récupérer le nom de l'interface souhaitée

`ifconfig`

Modifier le fichier de configuration 

`nano /etc/sysconfig/network-scripts/ifcfg-<name>`

Enregistrer avec CTRL+X

Vérifier le bon addressage IP 

`ifconfig`
