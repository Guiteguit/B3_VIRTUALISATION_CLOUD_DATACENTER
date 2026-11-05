# M04 — Défi interactif NovaCorp

**Brief client (10 min) :** Isoler le trafic applicatif de l'administration tout en gardant la communication web↔app.

**Question de départ / prédiction :** Dessiner la topologie NAT VMware / vmbr0 / vmbr1, sans toucher au clavier.

**Revue croisée (10 min) :** Le NOC utilise ping, ip route et curl pour tester les interfaces secondaires sur l'environnement d'un pair.

**Variante du second sprint :** Le client interdit une passerelle sur le réseau interne : prouver que vmbr1 est isolé.

**Rendu du module :** Schéma annoté + matrice de tests réseau et preuves de séparation.

## Comment faire la revue sans perdre son autonomie
- Chaque étudiant configure **son propre** environnement.
- Le pair demande une preuve non destructive, ne change pas l'environnement à la place du propriétaire.
- Une personne explique son hypothèse, l'autre la teste. On inverse les casquettes au module suivant.
- On dépose la conclusion dans le [modèle de rendu](../docs/modele-rendu-interactif.md).

[TP technique](tp.md) · [Validation](validation.md) · [Rythme de séance](../docs/pedagogie-interactive.md)
