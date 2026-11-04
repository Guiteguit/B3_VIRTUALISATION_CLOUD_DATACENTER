# M02 — Troubleshooting

Suivre : **symptôme → hypothèse → test ciblé → correction minimale → vérification → rollback si échec**.

| Symptôme | Hypothèse | Démarche / correction |
|---|---|---|
| Interface web inaccessible | Mauvaise IP, réseau VMware, service pveproxy ou filtrage | Vérifier IP, route, ping puis systemctl status pveproxy ; conserver un accès console VMware. |
| /dev/kvm absent | Virtualisation imbriquée indisponible | Contrôler firmware et paramètres CPU VMware ; choisir le parcours alternatif LXC si besoin. |
| Aucun accès Internet | NAT/DNS mal configuré | Tester passerelle puis IP publique puis résolution DNS ; ne modifier qu'un paramètre à la fois. |

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
