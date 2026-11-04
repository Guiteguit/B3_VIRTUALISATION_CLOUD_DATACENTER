# M07 — Troubleshooting

Suivre : **symptôme → hypothèse → test ciblé → correction minimale → vérification → rollback si échec**.

| Symptôme | Hypothèse | Démarche / correction |
|---|---|---|
| Erreur 401/403 sur l'interface | Mauvaises informations d'authentification ou rôle sans droits | Vérifier domaine d'authentification PAM/PVE et permissions sans escalade automatique. |
| Web indisponible | Nginx arrêté | Procéder DNS/IP/port/service, puis démarrer nginx et tester curl. |
| Impossible de joindre 10.10.10.20 | Mauvais masque ou NIC secondaire | Comparer adresse/masque sur les deux invités et restaurer l'état de départ. |

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
