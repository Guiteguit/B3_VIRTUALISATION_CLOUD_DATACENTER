# M02 — Cours et notions à comprendre

## 1. Notion essentielle
Proxmox VE utilise Debian, KVM/QEMU pour les VM, LXC pour les conteneurs et une console web sur TCP 8006.

## 2. Notion essentielle
En laboratoire imbriqué, l'exposition VT-x/AMD-V dans VMware est indispensable pour KVM ; LXC reste une alternative pédagogique selon les restrictions.

## 3. Notion essentielle
Le choix NAT VMware simplifie l'accès Internet du laboratoire ; une IP stable et le nom d'hôte doivent être cohérents.

## 4. Notion essentielle
L'installation requiert un disque dédié à la VM hôte. Ne jamais installer l'ISO Proxmox directement sur le PC étudiant.

## Questions de compréhension
1. Quels composants de l'architecture NovaCorp sont concernés par ce module ?
2. Quelle est la différence entre l'état attendu et une configuration dégradée ?
3. Quelle preuve technique démontre que la manipulation a réussi ?

## Pour aller plus loin
- [Documentation officielle Proxmox VE](https://pve.proxmox.com/pve-docs/)
- [Documentation Debian](https://www.debian.org/doc/)
