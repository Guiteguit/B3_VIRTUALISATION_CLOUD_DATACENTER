# M01 — Commandes et diagnostic

> Exécuter chaque commande dans le **bon contexte** : PowerShell Windows, shell Proxmox, VM Debian ou conteneur. Les commandes ne sont pas toutes destinées au même système.

```powershell
Get-ComputerInfo | Select-Object CsName,OsName,CsTotalPhysicalMemory,CsProcessors
Get-CimInstance Win32_Processor | Select-Object Name,NumberOfCores,NumberOfLogicalProcessors,VirtualizationFirmwareEnabled
Get-WindowsOptionalFeature -Online -FeatureName Microsoft-Hyper-V-Hypervisor
systeminfo
```

## Méthode d'utilisation
1. Lire les paramètres et identifier la machine concernée.
2. Exécuter une commande de **lecture** avant toute modification.
3. Copier la sortie pertinente dans le compte rendu (sans secret).
4. Confronter la sortie à l'état attendu de [validation.md](validation.md).

**Références :** [Proxmox VE Administrator Guide](https://pve.proxmox.com/pve-docs/), pages man Linux (`man ip`, `man systemctl`, `man lsblk`).
