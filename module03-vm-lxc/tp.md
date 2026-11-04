# M03 — TP individuel

## Mission
NovaCorp héberge un serveur web et un service interne sur son hôte unique.

**Objectif :** Déployer un serveur Debian virtualisé et un conteneur pour comparer cycle de vie et ressources.

## Étapes (environ 60 min)
1. Importer une ISO Debian netinstall dans le stockage local, créer une VM web01 (ID 100, 1 vCPU, 1 Go RAM, 12 Go disque), installer Debian minimal sans interface graphique.
2. Télécharger un template LXC Debian et créer app01 (ID 200, 1 vCPU, 512 Mo RAM, 4 Go disque), de préférence non privilégié.
3. Démarrer, arrêter et redémarrer les deux invités depuis l'interface puis depuis la CLI.
4. Installer nginx dans app01, vérifier son statut et récupérer une réponse HTTP depuis le conteneur.
5. Comparer usage mémoire et démarrage, puis expliquer dans quels cas préférer VM ou LXC.
6. Si KVM est impossible, réaliser le parcours LXC et documenter la démonstration VM faite par le formateur.

## Journal des opérations
Dans votre rendu, consignez pour chaque étape : **commande ou action**, **résultat constaté**, **preuve**, **erreur éventuelle et correction**.

## En cas de blocage
Consultez [commands.md](commands.md) puis [troubleshooting.md](troubleshooting.md), revenez à votre dernier état stable et documentez l'échec. N'improvisez pas de modification sur la carte de management ou un disque système.

## Rendu
Vérifiez tous les éléments de [validation.md](validation.md). Répondez aux questions : quel risque opérationnel avez-vous rencontré ? Comment éviteriez-vous ce risque en entreprise ?
