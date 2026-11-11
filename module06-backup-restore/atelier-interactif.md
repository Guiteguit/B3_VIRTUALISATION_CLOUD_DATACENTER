# M06 — Atelier interactif : Sauvegarde, snapshots et restauration

**90 minutes · Travail individuel sur son propre Proxmox · Revue en binôme (ou trinôme à 7 étudiants).**  
**Client :** Une erreur de manipulation supprime un fichier important. NovaCorp veut une démonstration de récupération, pas seulement une promesse de sauvegarde.

## Mission et hypothèse
**Question à résoudre :** Un snapshot local et une sauvegarde locale protègent-ils d'une panne totale du serveur physique ?

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
1. Créer `/srv/novacorp/preuve.txt` dans `app01` et noter son contenu avant tout changement.
2. Vérifier espace et type de contenu backup autorisé sur le stockage choisi.
3. Sauvegarder le CT 200 (`vzdump 200 --storage local --mode stop`) et identifier l'archive et l'horodatage.

### Revue croisée (10 min)
L'auditeur examine le fichier témoin **avant** l'incident et l'archive produite. Il demande : « Quelles données seront réellement restaurables ? »

**Trace de la revue :** question posée, commande/test non destructif, résultat attendu, résultat constaté, correction éventuelle. La configuration reste sous le contrôle du propriétaire ; aucun mot de passe échangé.

### Nouvelle demande du client (Sprint 2)
> NovaCorp découvre qu'un backup conservé uniquement sur `pve01` disparaîtra avec son disque : quelle stratégie proposez-vous pour une PME ?

4. Supprimer **uniquement le fichier témoin** du CT 200, en conservant le CT d'origine.
5. Restaurer l'archive sous un ID distinct, par convention 201, après vérification de disponibilité.
6. Contrôler `pct exec 201 -- cat /srv/novacorp/preuve.txt` et mesurer le RTO observé.

## Preuves de validation
- [ ] Archive VZDump identifiable
- [ ] CT 201 en cours d'exécution après restauration
- [ ] Contenu de `preuve.txt` récupéré et RPO/RTO expliqués

## Parcours de repli
Si la capacité disque est insuffisante, réduire la taille du CT ou utiliser un emplacement autorisé avec assez d'espace avant de lancer le backup ; ne jamais effacer l'original pour « faire de la place ». Le snapshot est une comparaison théorique si le stockage ne le permet pas.

## Rendu individuel : `M06.md`
Utiliser [le modèle de compte rendu](../docs/modele-rendu-interactif.md) et produire **1 à 2 pages hors captures utiles** : hypothèse, manipulations, preuve, retour de revue croisée, décision NovaCorp, rollback et apprentissage.

**Ressources :** [TP](tp.md) · [Commandes](commands.md) · [Troubleshooting](troubleshooting.md) · [Validation](validation.md) · [Revue croisée rapide](../docs/revue-croisee-rapide.md).
