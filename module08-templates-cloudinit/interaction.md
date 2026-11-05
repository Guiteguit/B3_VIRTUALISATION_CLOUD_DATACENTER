# M08 — Défi interactif NovaCorp

**Brief client (10 min) :** NovaCorp demande une deuxième VM Debian identique, déployable en quelques minutes.

**Question de départ / prédiction :** Estimer le temps d'installation manuelle et l'intérêt du modèle ; distinguer clone complet / lié.

**Revue croisée (10 min) :** L'auditeur vérifie identité de la VM, IP, cloud-init status et absence de secrets en clair.

**Variante du second sprint :** Le client veut 3 VM identiques demain : argumenter une stratégie templates/cloud-init sans Terraform.

**Rendu du module :** Template 9000, clone 102, commandes de vérification et mini retour d'expérience.

## Comment faire la revue sans perdre son autonomie
- Chaque étudiant configure **son propre** environnement.
- Le pair demande une preuve non destructive, ne change pas l'environnement à la place du propriétaire.
- Une personne explique son hypothèse, l'autre la teste. On inverse les casquettes au module suivant.
- On dépose la conclusion dans le [modèle de rendu](../docs/modele-rendu-interactif.md).

[TP technique](tp.md) · [Validation](validation.md) · [Rythme de séance](../docs/pedagogie-interactive.md)
