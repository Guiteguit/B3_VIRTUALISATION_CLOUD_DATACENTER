# M08 — Atelier interactif : Templates, clonage et Cloud-Init

**90 minutes · Travail individuel sur son propre Proxmox · Revue en binôme (ou trinôme à 7 étudiants).**  
**Client :** NovaCorp doit multiplier les serveurs Debian identiques sans réinstaller manuellement le système à chaque demande.

## Mission et hypothèse
**Question à résoudre :** Quel bénéfice attendez-vous d'une image cloud et d'un template, et quel est le rôle de Cloud-Init au premier démarrage ?

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
1. Arrêter les invités inutiles et contrôler RAM/disque disponibles.
2. Préparer une image Debian genericcloud officielle et créer la VM modèle 9000 (disque importé puis attaché).
3. Ajouter le lecteur Cloud-Init, vérifier réseau `vmbr0` et les paramètres de premier démarrage.

### Revue croisée (10 min)
L'auditeur demande la configuration du modèle (`qm config 9000`) et vérifie présence du disque de boot, lecteur Cloud-Init et absence de secrets partagés.

**Trace de la revue :** question posée, commande/test non destructif, résultat attendu, résultat constaté, correction éventuelle. La configuration reste sous le contrôle du propriétaire ; aucun mot de passe échangé.

### Nouvelle demande du client (Sprint 2)
> La direction commande trois serveurs identiques demain : proposer une procédure fiable et expliquer ce qui reste manuel.

4. Convertir le modèle éteint en template ; créer un clone complet ID 102, si cet ID est libre.
5. Définir une identité d'hôte distincte et une clé SSH de laboratoire ; privilégier DHCP sur le NAT VMware.
6. Démarrer le clone, valider `hostnamectl`, `ip -br addr`, `cloud-init status --long` et formuler deux limites de cette approche.

## Preuves de validation
- [ ] Template 9000 identifié et configuration conservée
- [ ] Clone 102 démarre avec identité distincte
- [ ] Cloud-Init terminé et une IP fonctionnelle présente

## Parcours de repli
Si KVM nested ou la capacité disque bloque, le formateur effectue la démonstration et l'étudiant produit un schéma de la chaîne image→template→clone→Cloud-Init, avec les preuves attendues et les causes possibles d'échec.

## Rendu individuel : `M08.md`
Utiliser [le modèle de compte rendu](../docs/modele-rendu-interactif.md) et produire **1 à 2 pages hors captures utiles** : hypothèse, manipulations, preuve, retour de revue croisée, décision NovaCorp, rollback et apprentissage.

**Ressources :** [TP](tp.md) · [Commandes](commands.md) · [Troubleshooting](troubleshooting.md) · [Validation](validation.md) · [Revue croisée rapide](../docs/revue-croisee-rapide.md).
