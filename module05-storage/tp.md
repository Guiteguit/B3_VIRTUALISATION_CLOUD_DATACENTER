# M05 — TP individuel

## Mission
NovaCorp doit augmenter la capacité de son serveur web sans réinstaller son système.

**Objectif :** Identifier les stockages Proxmox et attacher un volume supplémentaire à un invité.

## Étapes (environ 60 min)
1. Inventorier les stockages Proxmox, leurs types, espaces libres et types de contenu autorisés.
2. Identifier le disque de web01 et sa taille ; créer un second disque virtuel de 2 Go sur le stockage disponible.
3. Dans web01, repérer le nouveau disque avec lsblk ; vérifier soigneusement son nom avant partitionnement.
4. Créer une partition et un système de fichiers ext4 sur le NOUVEAU disque, puis le monter sur /srv/data.
5. Configurer un montage persistant par UUID dans /etc/fstab et tester après redémarrage.
6. Rédiger une note expliquant le risque de manque d'espace disque sur l'hôte.

## Journal des opérations
Dans votre rendu, consignez pour chaque étape : **commande ou action**, **résultat constaté**, **preuve**, **erreur éventuelle et correction**.

## En cas de blocage
Consultez [commands.md](commands.md) puis [troubleshooting.md](troubleshooting.md), revenez à votre dernier état stable et documentez l'échec. N'improvisez pas de modification sur la carte de management ou un disque système.

## Rendu
Vérifiez tous les éléments de [validation.md](validation.md). Répondez aux questions : quel risque opérationnel avez-vous rencontré ? Comment éviteriez-vous ce risque en entreprise ?
