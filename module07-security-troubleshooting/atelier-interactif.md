# M07 — Atelier interactif : Sécurité et troubleshooting

**90 minutes · Travail individuel sur son propre Proxmox · Revue en binôme (ou trinôme à 7 étudiants).**  
**Client :** Le service applicatif NovaCorp n'est plus accessible. Le support doit trouver la cause sans modifier au hasard les paramètres Proxmox.

## Mission et hypothèse
**Question à résoudre :** Un client indique « le site est inaccessible » : dans quel ordre vérifiez-vous IP, port, service et configuration ?

Avant toute commande, écrire son hypothèse et un résultat observable qui permettrait de la vérifier.

## Déroulement de la séance

| Minute | Phase | Action / preuve |
|---|---|---|
| 00–10 | Brief du client | Reformuler la demande et donner une première décision en 2 phrases. |
| 10–25 | Théorie dialoguée | Lire les notions de [theory.md](theory.md), répondre à la question de départ, anticiper un test. |
| 25–50 | Sprint 1 — Construire | Suivre les étapes 1–3 ci-dessous et conserver une preuve intermédiaire. |
| 50–60 | Revue croisée | Présenter son écran et réaliser un test de lecture proposé par son pair. |
| 60–80 | Sprint 2 — Adapter et valider | Appliquer la variante NovaCorp puis les étapes 4–6. |
| 80–90 | Débrief et rendu | Un ou deux étudiants présentent 60 secondes de preuve ; chaque étudiant remet sa fiche. |

### Sprint 1 — travail individuel
1. Observer utilisateurs, rôles et état des services de management (lecture uniquement).
2. Décrire un accès de moindre privilège et les risques d'exposer le port 8006.
3. Provoquer **sur app01 seulement** l'arrêt de Nginx, puis constater HTTP KO par `curl`.

### Revue croisée (10 min)
Le pair joue le NOC : il propose UNE hypothèse et UNE commande de lecture discriminante ; le propriétaire montre le résultat et note la cause identifiée.

**Trace de la revue :** question posée, commande/test non destructif, résultat attendu, résultat constaté, correction éventuelle. La configuration reste sous le contrôle du propriétaire ; aucun mot de passe échangé.

### Nouvelle demande du client (Sprint 2)
> Le DSI refuse une correction « au hasard » : chaque changement doit comporter hypothèse, preuve avant, test après et retour arrière.

4. Corriger l'incident Nginx et valider HTTP OK.
5. Sur l'interface du **réseau privé** uniquement, simuler une mauvaise configuration d'adresse/masque puis diagnostiquer et restaurer.
6. Rendre deux mini-tickets : symptôme, hypothèse, commande, résultat, correction, rollback.

## Preuves de validation
- [ ] `systemctl is-active nginx` : actif après correction
- [ ] HTTP OK localement et depuis l'autre invité si le réseau est opérationnel
- [ ] Les IP/masques du réseau privé sont revenus à l'état attendu

## Parcours de repli
Si la manipulation réseau est risquée ou si l'environnement est instable, fournir une sortie `ip route` erronée à analyser sans la reproduire. Ne jamais casser le bridge de management ni activer un firewall bloquant pour ce TP.

## Rendu individuel : `M07.md`
Utiliser [le modèle de compte rendu](../docs/modele-rendu-interactif.md) et produire **1 à 2 pages hors captures utiles** : hypothèse, manipulations, preuve, retour de revue croisée, décision NovaCorp, rollback et apprentissage.

**Ressources :** [TP](tp.md) · [Commandes](commands.md) · [Troubleshooting](troubleshooting.md) · [Validation](validation.md) · [Revue croisée rapide](../docs/revue-croisee-rapide.md).
