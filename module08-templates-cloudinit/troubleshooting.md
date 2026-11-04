# M08 — Troubleshooting

Suivre : **symptôme → hypothèse → test ciblé → correction minimale → vérification → rollback si échec**.

| Symptôme | Hypothèse | Démarche / correction |
|---|---|---|
| Cloud-Init n'applique rien | Disque cloud-init absent, image inadaptée ou paramètres définis trop tard | Vérifier qm config 9000 et la présence de cloud-init dans l'image ; recréer le clone après correction. |
| Clone sans IP | DHCP indisponible ou mauvaise interface vmbr0 | Contrôler ip -br a, réseau VMware NAT, passerelle et configuration Cloud-Init. |
| Clone ne démarre pas | Ordre de boot ou contrôleur disque erroné | Vérifier qm config 102, boot order et console du clone. |
| Aucune VM KVM possible | Nested virtualization indisponible | Lire la démarche de démonstration et rendre le rapport d'analyse en précisant la limitation matérielle. |

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
