# Informations Utiles VMware
## Diagnostics/Corrections Certificats vCenter
> [!WARNING]
> Bien penser à faire un snap à froid avant toute modification

[vSphere Diagnostic Tool](https://flings.vmware.com/vsphere-diagnostic-tool)

[Check du certificat STS seul](https://kb.vmware.com/s/article/79248?lang=en_us)

[Si erreur pour le certificat SSL](https://kb.vmware.com/s/article/80469)

[Si certificat STS expiré](https://kb.vmware.com/s/article/76719?lang=en_US)

[Régénérer les certificats (Option 4)](https://kb.vmware.com/s/article/2112283)

## Compte root vCenter
[Unlock/Reset compte root](https://pchawda.wordpress.com/2019/08/28/unlock-reset-password-of-root-account-on-vcenter-appliance-6-x/)

## Lister certificats vROPS
`for store in $(/usr/lib/vmware-vmafd/bin/vecs-cli store list | grep -v TRUSTED_ROOT_CRLS); do echo "[*] Store :" $store; /usr/lib/vmware-vmafd/bin/vecs-cli entry list --store $store --text | grep -ie "Alias" -ie "Not After";done`

## Passer en bash 
`chsh -s "/bin/bash" root`

## HP iLO
[Reset compte administrator via ESXi](https://www.virtualease.fr/vmware-configurer-hp-ilo-esxi/)

## Liens Utiles
[Correspondance VMware Tools](https://kb.vmware.com/s/article/86165)

[Liste versions Vcenter](https://kb.vmware.com/s/article/2143838)
[Liste versions VMware Tools](https://kb.vmware.com/s/article/86165)
[Liste Compatibilité VM Hardware (VM version)](https://docs.vmware.com/en/VMware-vSphere/7.0/com.vmware.vsphere.vm_admin.doc/GUID-64D4B1C9-CD5D-4C68-8B50-585F6A87EBA0.html)
[Interopérabilité Matrice VMware](https://interopmatrix.vmware.com/Interoperability)

[Lab VMware](https://labs.hol.vmware.com/HOL/catalogs/catalog/1936)
