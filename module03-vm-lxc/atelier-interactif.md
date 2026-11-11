# M03 — Atelier interactif : VM Debian et conteneur LXC

**90 minutes · Travail individuel sur son propre Proxmox · Revue en binôme (ou trinôme à 7 étudiants).**  
**Client :** NovaCorp doit héberger un serveur web et un petit service interne avec seulement 8 Go de RAM alloués à l'hôte Proxmox.

## Mission et hypothèse
**Question à résoudre :** Pour chaque service, choisiriez-vous une VM KVM ou un conteneur LXC ? Pourquoi ?

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
1. Vérifier l'état de KVM (`ls -l /dev/kvm`) et l'espace disponible (`pvesm status`).
2. Créer ou terminer `web01` (VM ID 100, Debian minimal, 1 vCPU/1 Go/12 Go) si KVM est opérationnel.
3. Importer le template LXC Debian et créer `app01` (CT 200, 1 vCPU/512 Mo/4 Go, non privilégié si possible).

### Revue croisée (10 min)
Le binôme demande une preuve du type d'invité, de sa configuration CPU/RAM et de son statut de démarrage (`qm config 100`, `pct config 200`). Le propriétaire exécute les commandes.

**Trace de la revue :** question posée, commande/test non destructif, résultat attendu, résultat constaté, correction éventuelle. La configuration reste sous le contrôle du propriétaire ; aucun mot de passe échangé.

### Nouvelle demande du client (Sprint 2)
> Le responsable infrastructure demande de réduire la RAM : justifiez quel service peut rester en LXC et quels compromis d'isolation cela implique.

4. Installer Nginx dans `app01`, contrôler `systemctl is-active nginx` puis `curl -I http://127.0.0.1`.
5. Arrêter et redémarrer séparément VM et CT ; noter les différences observables.
6. Remplir une comparaison KVM/LXC et proposer une répartition des services NovaCorp.

## Preuves de validation
- [ ] `pct status 200` : CT actif
- [ ] `pct exec 200 -- curl -I http://127.0.0.1` : code HTTP
- [ ] `qm status 100` : VM active, ou impossibilité KVM justifiée

## Parcours de repli
Si KVM nested est indisponible, l'étudiant réalise le CT et renseigne une fiche d'observation de la démonstration VM. Si l'installation Debian dépasse le créneau, utiliser une VM Debian minimale préinstallée fournie pour le laboratoire.

## Rendu individuel : `M03.md`
Utiliser [le modèle de compte rendu](../docs/modele-rendu-interactif.md) et produire **1 à 2 pages hors captures utiles** : hypothèse, manipulations, preuve, retour de revue croisée, décision NovaCorp, rollback et apprentissage.

**Ressources :** [TP](tp.md) · [Commandes](commands.md) · [Troubleshooting](troubleshooting.md) · [Validation](validation.md) · [Revue croisée rapide](../docs/revue-croisee-rapide.md).
