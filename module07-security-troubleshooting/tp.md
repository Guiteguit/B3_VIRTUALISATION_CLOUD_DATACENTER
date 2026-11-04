# M07 — TP individuel

## Mission
Le support NovaCorp traite des tickets liés à des services et à la connectivité.

**Objectif :** Appliquer des mesures élémentaires de sécurité et résoudre deux incidents simples sans compromettre l'hôte.

## Étapes (environ 60 min)
1. Identifier la différence entre utilisateur root@pam et un compte dédié ; décrire un rôle minimal en lecture seule, sans distribuer le mot de passe root.
2. Observer les permissions et politiques de sécurité existantes ; créer un compte de laboratoire si autorisé.
3. Dans app01, arrêter nginx volontairement, constater l'incident par curl puis analyser systemctl et journalctl.
4. Redémarrer nginx et documenter la validation du service.
5. Dans la NIC secondaire de web01, provoquer un mauvais masque de sous-réseau ; constater l'échec de communication puis rétablir le bon masque.
6. Rédiger deux tickets d'incident avec cause racine, corrections et rollback.

## Journal des opérations
Dans votre rendu, consignez pour chaque étape : **commande ou action**, **résultat constaté**, **preuve**, **erreur éventuelle et correction**.

## En cas de blocage
Consultez [commands.md](commands.md) puis [troubleshooting.md](troubleshooting.md), revenez à votre dernier état stable et documentez l'échec. N'improvisez pas de modification sur la carte de management ou un disque système.

## Rendu
Vérifiez tous les éléments de [validation.md](validation.md). Répondez aux questions : quel risque opérationnel avez-vous rencontré ? Comment éviteriez-vous ce risque en entreprise ?
