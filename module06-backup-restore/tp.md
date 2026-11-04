# M06 — TP individuel

## Mission
Une modification applicative NovaCorp supprime des fichiers : l'équipe doit les récupérer.

**Objectif :** Sauvegarder un conteneur, provoquer une perte logique et valider une restauration isolée.

## Étapes (environ 60 min)
1. Dans app01, créer /srv/novacorp/preuve.txt contenant la date, un identifiant de laboratoire et un message témoin.
2. Vérifier que local autorise VZDump backup files et que le disque dispose d'assez d'espace.
3. Créer une sauvegarde de app01 avec mode stop depuis l'interface ou vzdump 200 --storage local --mode stop.
4. Supprimer volontairement preuve.txt dans app01 ; ne pas détruire l'original.
5. Restaurer la sauvegarde sous un nouvel ID 201, puis vérifier l'existence et le contenu du fichier témoin.
6. Mesurer le temps de récupération et expliquer pourquoi la sauvegarde locale ne constitue pas une stratégie PRA complète.

## Journal des opérations
Dans votre rendu, consignez pour chaque étape : **commande ou action**, **résultat constaté**, **preuve**, **erreur éventuelle et correction**.

## En cas de blocage
Consultez [commands.md](commands.md) puis [troubleshooting.md](troubleshooting.md), revenez à votre dernier état stable et documentez l'échec. N'improvisez pas de modification sur la carte de management ou un disque système.

## Rendu
Vérifiez tous les éléments de [validation.md](validation.md). Répondez aux questions : quel risque opérationnel avez-vous rencontré ? Comment éviteriez-vous ce risque en entreprise ?
