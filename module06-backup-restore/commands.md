# M06 — Commandes et diagnostic

> Exécuter chaque commande dans le **bon contexte** : PowerShell Windows, shell Proxmox, VM Debian ou conteneur. Les commandes ne sont pas toutes destinées au même système.

```bash
pct exec 200 -- mkdir -p /srv/novacorp
pct exec 200 -- sh -c 'date -Iseconds > /srv/novacorp/preuve.txt'
vzdump 200 --storage local --mode stop
pvesm status
pct list
pct exec 201 -- cat /srv/novacorp/preuve.txt
```

## Méthode d'utilisation
1. Lire les paramètres et identifier la machine concernée.
2. Exécuter une commande de **lecture** avant toute modification.
3. Copier la sortie pertinente dans le compte rendu (sans secret).
4. Confronter la sortie à l'état attendu de [validation.md](validation.md).

**Références :** [Proxmox VE Administrator Guide](https://pve.proxmox.com/pve-docs/), pages man Linux (`man ip`, `man systemctl`, `man lsblk`).
