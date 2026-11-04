# M01 — TP individuel

## Mission
NovaCorp souhaite consolider trois serveurs physiques sur une plateforme virtualisée.

**Objectif :** Distinguer virtualisation, conteneurisation et modèles de service cloud, puis vérifier les capacités du poste de travail.

## Étapes (environ 60 min)
1. Relever CPU, processeurs logiques, RAM, espace disque libre et édition Windows ; noter les versions VMware et BIOS/UEFI.
2. Sous Windows, exécuter les commandes d'inventaire indiquées dans commands.md et capturer les résultats pertinents.
3. Dans VMware Workstation, repérer le NAT, le bridge et le host-only ; expliquer les conséquences de chacun en salle de cours.
4. Dessiner l'architecture : Windows → VMware Workstation → VM Proxmox → VM Debian + conteneur LXC.
5. Comparer VMware Workstation, VMware ESXi et Proxmox VE selon cible, hyperviseur, administration, prix/licence et contraintes.
6. Rédiger un verdict GO / RISQUE / BLOQUÉ pour la virtualisation imbriquée et proposer une solution de repli.

## Journal des opérations
Dans votre rendu, consignez pour chaque étape : **commande ou action**, **résultat constaté**, **preuve**, **erreur éventuelle et correction**.

## En cas de blocage
Consultez [commands.md](commands.md) puis [troubleshooting.md](troubleshooting.md), revenez à votre dernier état stable et documentez l'échec. N'improvisez pas de modification sur la carte de management ou un disque système.

## Rendu
Vérifiez tous les éléments de [validation.md](validation.md). Répondez aux questions : quel risque opérationnel avez-vous rencontré ? Comment éviteriez-vous ce risque en entreprise ?
