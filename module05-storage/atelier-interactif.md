# M05 — Atelier interactif : Stockage et gestion des ressources

**90 minutes · Travail individuel sur son propre Proxmox · Revue en binôme (ou trinôme à 7 étudiants).**  
**Client :** Le serveur web NovaCorp manque d'espace pour les données, mais doit conserver son disque système intact.

## Mission et hypothèse
**Question à résoudre :** Comment différencier le disque virtuel vu par Debian de l'espace réellement disponible sur le stockage Proxmox ?

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
1. Contrôler `pvesm status`, l'espace disponible et le type de contenu des stockages.
2. Examiner `qm config 100` ; ajouter un disque VIRTUEL distinct de 2 Go à `web01`.
3. Dans Debian, relever `lsblk -o NAME,SIZE,FSTYPE,MOUNTPOINTS` avant et après ajout.

### Revue croisée (10 min)
L'auditeur demande au propriétaire de **prouver** quel disque est nouveau avant tout formatage. Arrêter la manipulation si le disque système n'est pas distingué avec certitude.

**Trace de la revue :** question posée, commande/test non destructif, résultat attendu, résultat constaté, correction éventuelle. La configuration reste sous le contrôle du propriétaire ; aucun mot de passe échangé.

### Nouvelle demande du client (Sprint 2)
> L'équipe exploitation impose que le répertoire de données soit toujours monté après un redémarrage. Comment le prouver ?

4. Partitionner/formater **uniquement** le disque supplémentaire identifié, puis le monter sur `/srv/data`.
5. Définir une entrée `/etc/fstab` par UUID, tester `mount -a`, puis redémarrer l'invité.
6. Contrôler `findmnt /srv/data`, `df -hT` et documenter les risques de saturation.

## Preuves de validation
- [ ] `lsblk -f` : le disque supplémentaire et sa partition
- [ ] `findmnt /srv/data` : point de montage présent
- [ ] Après redémarrage : les données du volume sont encore visibles

## Parcours de repli
Si VM KVM indisponible, réaliser la démonstration du disque VM côté formateur, puis donner au binôme une étude de cas sur stockage et capacité ; la partie manipulation peut être faite sur un CT avec un mount point configuré **dans l'interface Proxmox** et sans formatage de disque hôte.

## Rendu individuel : `M05.md`
Utiliser [le modèle de compte rendu](../docs/modele-rendu-interactif.md) et produire **1 à 2 pages hors captures utiles** : hypothèse, manipulations, preuve, retour de revue croisée, décision NovaCorp, rollback et apprentissage.

**Ressources :** [TP](tp.md) · [Commandes](commands.md) · [Troubleshooting](troubleshooting.md) · [Validation](validation.md) · [Revue croisée rapide](../docs/revue-croisee-rapide.md).
