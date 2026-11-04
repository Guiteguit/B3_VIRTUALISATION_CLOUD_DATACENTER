# M05 — Troubleshooting

Suivre : **symptôme → hypothèse → test ciblé → correction minimale → vérification → rollback si échec**.

| Symptôme | Hypothèse | Démarche / correction |
|---|---|---|
| Disque absent dans Debian | Disque non attaché, contrôleur ou rescannage | Contrôler qm config 100 et lsblk avant toute opération d'écriture. |
| Montage absent après reboot | Entrée fstab erronée | Tester mount -a et journalctl -b, revenir à l'entrée précédente si nécessaire. |
| Plus d'espace sur l'hôte | Stockage local saturé | Identifier usage via pvesm status, df -h, sauvegarder avant nettoyage ; ne pas supprimer les disques invités. |

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
