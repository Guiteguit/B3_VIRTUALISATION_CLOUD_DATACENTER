# M04 — TP individuel

## Mission
Le serveur web NovaCorp et le service applicatif doivent échanger sur un réseau interne isolé.

**Objectif :** Distinguer NAT VMware, bridge Linux Proxmox et réseau interne ; faire communiquer des workloads.

## Étapes (environ 60 min)
1. Noter le plan IP du NAT VMware et l'adresse de management pve01 : ne pas changer vmbr0 pendant l'exercice.
2. Créer dans l'interface Proxmox un bridge vmbr1 sans port physique, sans adresse IP hôte et sans VLAN requis.
3. Ajouter une seconde NIC sur web01 et app01, connectée à vmbr1 ; garder les interfaces de management existantes.
4. Configurer 10.10.10.10/24 sur web01 et 10.10.10.20/24 sur app01, sans passerelle sur ce réseau isolé.
5. Tester ping et HTTP entre web01 et app01 sur les IP internes ; relever interfaces et routes.
6. Couper temporairement une NIC secondaire et observer la panne, puis effectuer le rollback.

## Journal des opérations
Dans votre rendu, consignez pour chaque étape : **commande ou action**, **résultat constaté**, **preuve**, **erreur éventuelle et correction**.

## En cas de blocage
Consultez [commands.md](commands.md) puis [troubleshooting.md](troubleshooting.md), revenez à votre dernier état stable et documentez l'échec. N'improvisez pas de modification sur la carte de management ou un disque système.

## Rendu
Vérifiez tous les éléments de [validation.md](validation.md). Répondez aux questions : quel risque opérationnel avez-vous rencontré ? Comment éviteriez-vous ce risque en entreprise ?
