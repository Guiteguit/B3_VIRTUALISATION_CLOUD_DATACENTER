# B3 ESGI Tours — Fondamentaux de la virtualisation Cloud & Datacenter

**3ESGI ALT — T1 — SRC — TOURS** | 8 × 1 h 30 = **12 heures** | Travail **individuel** | Fil rouge **NovaCorp**.

## Mission
Installer et exploiter une plateforme Proxmox VE dans VMware Workstation, développer de bons réflexes système/réseau/stockage et préparer l'approfondissement en M1 (clusters, HA, PBS, automatisation).

## Parcours

| Jour | Module | Sujet |
|---|---|---|
| 1 | [M01 — Fondamentaux VMware, Proxmox et cloud](module01-foundations/README.md) | [TP](module01-foundations/tp.md) · [Commandes](module01-foundations/commands.md) · [Dépannage](module01-foundations/troubleshooting.md) |
| 1 | [M02 — Installer et administrer Proxmox VE](module02-proxmox-install/README.md) | [TP](module02-proxmox-install/tp.md) · [Commandes](module02-proxmox-install/commands.md) · [Dépannage](module02-proxmox-install/troubleshooting.md) |
| 1 | [M03 — Administrer des VM KVM et des conteneurs LXC](module03-vm-lxc/README.md) | [TP](module03-vm-lxc/tp.md) · [Commandes](module03-vm-lxc/commands.md) · [Dépannage](module03-vm-lxc/troubleshooting.md) |
| 1 | [M04 — Réseau virtuel et connectivité](module04-networking/README.md) | [TP](module04-networking/tp.md) · [Commandes](module04-networking/commands.md) · [Dépannage](module04-networking/troubleshooting.md) |
| 2 | [M05 — Stockage, volumes et capacité](module05-storage/README.md) | [TP](module05-storage/tp.md) · [Commandes](module05-storage/commands.md) · [Dépannage](module05-storage/troubleshooting.md) |
| 2 | [M06 — Snapshots, sauvegardes et restauration](module06-backup-restore/README.md) | [TP](module06-backup-restore/tp.md) · [Commandes](module06-backup-restore/commands.md) · [Dépannage](module06-backup-restore/troubleshooting.md) |
| 2 | [M07 — Sécurité et méthode de troubleshooting](module07-security-troubleshooting/README.md) | [TP](module07-security-troubleshooting/tp.md) · [Commandes](module07-security-troubleshooting/commands.md) · [Dépannage](module07-security-troubleshooting/troubleshooting.md) |
| 2 | [M08 — Templates, clonage et Cloud-Init](module08-templates-cloudinit/README.md) | [TP](module08-templates-cloudinit/tp.md) · [Commandes](module08-templates-cloudinit/commands.md) · [Dépannage](module08-templates-cloudinit/troubleshooting.md) |

## Commencer
1. Lire [les prérequis](docs/prerequisites.md) et remplir [le préflight](docs/lab-preflight.md).
2. Lire [l'architecture](docs/architecture.md) et [le plan réseau](docs/network-plan.md).
3. Effectuer chaque module dans l'ordre. Garder sa configuration des modules précédents.
4. Rendre les preuves décrites dans [les livrables](docs/deliverables.md).

> ⚠️ Installer Proxmox **uniquement dans une VM VMware**, jamais sur le disque Windows du poste. Ne désactiver aucune protection Windows (Hyper-V/VBS) sans accord explicite de l'établissement. Le parcours LXC permet de continuer si KVM imbriqué n'est pas disponible.

## Documentation éditeur
- [Proxmox VE — documentation](https://pve.proxmox.com/pve-docs/)
- [Proxmox VE — téléchargement](https://www.proxmox.com/en/downloads)
- [Debian — images cloud](https://cloud.debian.org/images/cloud/)
- [Cloud-Init — documentation](https://cloudinit.readthedocs.io/)

**Règle du laboratoire :** on teste, on vérifie, on documente ; aucune commande destructive avant identification certaine du disque ou de l'interface visés.
