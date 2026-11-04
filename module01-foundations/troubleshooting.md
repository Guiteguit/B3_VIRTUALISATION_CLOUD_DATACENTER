# M01 — Troubleshooting

Suivre : **symptôme → hypothèse → test ciblé → correction minimale → vérification → rollback si échec**.

| Symptôme | Hypothèse | Démarche / correction |
|---|---|---|
| VirtualizationFirmwareEnabled=False | Virtualisation désactivée dans le firmware | Faire vérifier VT-x/AMD-V dans le BIOS/UEFI par l'administrateur du poste. |
| VMware ne propose pas l'option VT-x/AMD-V | Conflit possible avec Hyper-V/VBS ou machine non compatible | Noter l'obstacle, ne pas désactiver la sécurité du poste sans autorisation ; utiliser le profil LXC/démonstration. |

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
