# Prérequis techniques

- PC Windows avec droits administrateur, **16 Go RAM minimum** et idéalement 8 processeurs logiques ; prévoir de l'espace libre suffisant (viser 120 Go si possible).
- VMware Workstation Pro et accès à une ISO Proxmox VE officielle.
- La virtualisation imbriquée **nécessite** prise en charge VT-x/AMD-V, configuration du BIOS et compatibilité avec la configuration Windows/VMware.
- Proxmox imbriqué : **4 vCPU, 8 Go RAM, 80 Go disque virtuel, réseau VMware NAT**. Ces valeurs sont pédagogiques, pas un dimensionnement de production.
- VM Debian : 1 vCPU, 1 Go RAM et 12 Go disque ; LXC Debian : 1 vCPU, 512 Mo RAM et 4 Go disque.
- Sous Windows, Hyper-V et VBS peuvent rendre l'exposition directe VT-x/AMD-V indisponible selon les versions et réglages ; **ne pas désactiver ces protections sans autorisation**.
- Si l'accès réseau de l'école bloque les téléchargements, les ISO/templates seront fournis par le formateur.

[Retour à l'accueil](../README.md)
