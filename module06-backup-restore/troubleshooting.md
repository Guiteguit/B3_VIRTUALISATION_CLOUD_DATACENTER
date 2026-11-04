# M06 — Troubleshooting

Suivre : **symptôme → hypothèse → test ciblé → correction minimale → vérification → rollback si échec**.

| Symptôme | Hypothèse | Démarche / correction |
|---|---|---|
| Backup impossible | Stockage sans contenu backup ou espace insuffisant | Vérifier Storage > Content et df -h puis choisir un stockage autorisant VZDump. |
| Restauration refuse ID 201 | Identifiant déjà utilisé | Choisir un nouvel ID libre et vérifier pct list. |
| Fichier témoin absent après restore | Mauvaise archive ou fichier créé après le backup | Vérifier horodatages et archive choisie ; rejouer l'exercice dans le bon ordre. |

## Retour arrière
- Conserver une copie des paramètres initiaux avant chaque changement.
- En cas de coupure réseau, reprendre depuis la **console VMware**, jamais depuis une session web perdue.
- Ne pas effacer une VM, un conteneur, un disque ou une archive de backup pour « essayer ».
- Rejouer le test de validation et noter la cause racine.

## Ticket d'incident (modèle)
- Symptôme / heure :
- Hypothèses classées :
- Commandes et sorties :
- Cause racine :
- Correction :
- Test après correction :
- Procédure de rollback :
