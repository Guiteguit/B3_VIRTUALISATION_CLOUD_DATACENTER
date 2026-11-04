# M02 — Commandes et diagnostic

> Exécuter chaque commande dans le **bon contexte** : PowerShell Windows, shell Proxmox, VM Debian ou conteneur. Les commandes ne sont pas toutes destinées au même système.

```bash
pveversion -v
hostnamectl
ip -br addr
ip route
systemctl is-active pveproxy pvedaemon
cat /etc/network/interfaces
ls -l /dev/kvm
```

## Méthode d'utilisation
1. Lire les paramètres et identifier la machine concernée.
2. Exécuter une commande de **lecture** avant toute modification.
3. Copier la sortie pertinente dans le compte rendu (sans secret).
4. Confronter la sortie à l'état attendu de [validation.md](validation.md).

**Références :** [Proxmox VE Administrator Guide](https://pve.proxmox.com/pve-docs/), pages man Linux (`man ip`, `man systemctl`, `man lsblk`).
