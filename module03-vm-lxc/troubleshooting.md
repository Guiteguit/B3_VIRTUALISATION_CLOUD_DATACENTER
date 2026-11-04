# M03 — Troubleshooting

Suivre : **symptôme → hypothèse → test ciblé → correction minimale → vérification → rollback si échec**.

| Symptôme | Hypothèse | Démarche / correction |
|---|---|---|
| VM KVM refuse de démarrer | KVM non exposé à Proxmox | Vérifier /dev/kvm ; utiliser le parcours LXC si problème structurel. |
| LXC ne démarre pas | Template, espace disque, paramètres ou stockage | Consulter pct start 200 et journalctl -xe ; confirmer pvesm status. |
| Nginx ne répond pas | Service arrêté ou paquet absent | Contrôler systemctl status nginx, ss -lntp et curl localhost dans app01. |

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
