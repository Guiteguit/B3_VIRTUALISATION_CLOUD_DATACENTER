# Défi 2 — « 8 Go libres, mais la VM ne démarre pas » (20 minutes)

Un administrateur junior affirme : « Proxmox voit 8 Go de RAM, donc on peut obligatoirement lancer une VM KVM. »

Voici les observations sur un hôte Proxmox **imbriqué dans VMware Workstation** :

```text
root@pve01:~# free -h
               total        used        free
Mem:           7.7Gi       1.2Gi       5.4Gi

root@pve01:~# ls -l /dev/kvm
ls: cannot access '/dev/kvm': No such file or directory

root@pve01:~# grep -Ec '(vmx|svm)' /proc/cpuinfo
0

root@pve01:~# pct list
VMID  Status   Name
200   running  app01
```

## À produire
1. Expliquez pourquoi la mémoire libre n'est **pas** le critère décisif.
2. Pourquoi le conteneur `app01` peut-il fonctionner dans cette situation ?
3. Proposez **trois vérifications** dans l'ordre (Windows/firmware, VMware, Proxmox), en indiquant quelle information chacune fournit.
4. Indiquez ce qu'il serait **interdit ou imprudent** de modifier sur un PC géré par l'école pour « forcer » la virtualisation.
5. Proposez un **plan B pédagogique** permettant tout de même de travailler en autonomie.

**Variante orale :** « Et si `/dev/kvm` existait, cela suffirait-il à garantir que tout invité démarre ? »
