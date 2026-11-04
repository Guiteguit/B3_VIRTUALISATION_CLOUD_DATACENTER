# M04 — Troubleshooting

Suivre : **symptôme → hypothèse → test ciblé → correction minimale → vérification → rollback si échec**.

| Symptôme | Hypothèse | Démarche / correction |
|---|---|---|
| Ping impossible | Bridge incorrect, NIC désactivée ou mauvais masque | Examiner chaque niveau : interface guest, IP, bridge associé, ARP puis pare-feu. |
| HTTP inaccessible mais ping OK | Service absent ou port filtré | Contrôler ss -lntp, systemctl status nginx et curl localhost. |
| Perte d'accès à Proxmox | vmbr0 de management modifié par erreur | Revenir via la console VMware et restaurer la configuration sauvegardée. |

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
