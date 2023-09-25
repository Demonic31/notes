# Augmentation FS LVM RHEL
## Augmentation de la partition

Vérifier que le sda a bien la taille du disque physique

`lsblk`

Refaire le partitionnement du volume

`fdisk /dev/sda`

`m` : afficher les commande

`p` : identifier la partition a supprimer

`d` : supprimer la partition (3 pour sda3)

`p` : vérifier que la partition a été supprimée

`n` : recréation de la partition
1. **Numéro de partition** : ici 3
2. **Premier secteur** : laisser tel quel il retrouve le début de l'ancienne partition
3. **Dernier secteur** : entrer le volume désiré (ou laissez tel quel pour la totalité). Vous pouvez utiliser des raccourcis du type +100G pour définir une taille de partition à 100 Go par exemple.
4. **!!! NE PAS SUPPRIMER LA SIGNATURE !!!**

`w` : ecrire la nouvelle table de partition

Vérifier l'état de la nouvelle partition

`lsblk`

[Source](https://lecrabeinfo.net/redimensionner-agrandir-reduire-une-partition-sur-linux.html#avec-fdisk)

## Augmentation du volume physique (PV)

Lister le volume physique

`pvdisplay /dev/sda3`

Agrandir le volume physique selon la nouvelle table de partition

`pvresize /dev/sda3`

Vérifier la bonne augmentation du volume physique

`pvdisplay /dev/sda3`

## Vérification du volume group (VG)

Lister les VG

`vgs`

Afficher les caractéristiques du VG 

`vgdisplay root_vg`

On peut voir dans Free PE et VG Size le bon dimensionnement du volume

## Augmentation du volume logique (LV)

Récupérer le chemin complet du volume logique que vous souhaitez agrandir (ex: /dev/mapper/root_vg-lv_perso)

`df -h`

Une fois le LV identifié, utiliser la commande suivante pour agrandir le LV :

`lvextend -l +100%FREE /dev/mapper/root_vg-lv_perso`

Passer ensuite la commande suivante pour appliquer la taille

`xfs_growfs /var/`
ou
`resize2fs /var/`

Revérifier la taille du FS 

`df -h`

[Source](https://access.redhat.com/documentation/fr-fr/red_hat_enterprise_linux/6/html/logical_volume_manager_administration/lv_extend)
