# M08 — TP individuel

## Mission
NovaCorp veut déployer des serveurs Linux homogènes sans réinstaller manuellement chaque machine.

**Objectif :** Déployer une VM Debian depuis une image cloud et un template réutilisable.

## Étapes (environ 60 min)
1. Arrêter les VM non nécessaires ; vérifier les ressources CPU, RAM et disque de l'hôte.
2. Télécharger l'image Debian genericcloud qcow2 officielle compatible avec la version cible.
3. Créer une VM ID 9000, 1 vCPU, 1 Go RAM et importer le disque image, puis le rattacher en scsi0 ; activer le boot sur scsi0.
4. Ajouter un disque Cloud-Init, configurer un utilisateur et une clé publique SSH de laboratoire ; conserver DHCP sur vmbr0.
5. Convertir la VM éteinte en template et créer un clone complet ID 102 nommé srv02.
6. Démarrer srv02, vérifier hostname, IP, statut cloud-init et connectivité SSH lorsque configurée.
7. Comparer ce déploiement au TP03 et exposer deux avantages et deux limites.

## Journal des opérations
Dans votre rendu, consignez pour chaque étape : **commande ou action**, **résultat constaté**, **preuve**, **erreur éventuelle et correction**.

## En cas de blocage
Consultez [commands.md](commands.md) puis [troubleshooting.md](troubleshooting.md), revenez à votre dernier état stable et documentez l'échec. N'improvisez pas de modification sur la carte de management ou un disque système.

## Rendu
Vérifiez tous les éléments de [validation.md](validation.md). Répondez aux questions : quel risque opérationnel avez-vous rencontré ? Comment éviteriez-vous ce risque en entreprise ?
