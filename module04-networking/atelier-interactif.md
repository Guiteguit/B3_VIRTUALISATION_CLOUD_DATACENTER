# M04 — Atelier interactif : Réseau virtuel et segmentation

**90 minutes · Travail individuel sur son propre Proxmox · Revue en binôme (ou trinôme à 7 étudiants).**  
**Client :** L'entreprise exige une communication web–app sur un réseau privé, distinct du management Proxmox.

## Mission et hypothèse
**Question à résoudre :** Dans notre chaîne Windows → VMware NAT → Proxmox, qui fournit l'accès au réseau externe et que fait un bridge interne sans port physique ?

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
1. Documenter `vmbr0` et le réseau VMware NAT (sans les modifier).
2. Créer `vmbr1` sans port physique et sans IP de management.
3. Attacher les secondes interfaces de `web01` et `app01` à `vmbr1`.

### Revue croisée (10 min)
Un pair demande « Montre-moi que `vmbr1` est distinct de `vmbr0` et que l'adresse du réseau interne n'a pas de passerelle par défaut ». Le propriétaire montre sa configuration.

**Trace de la revue :** question posée, commande/test non destructif, résultat attendu, résultat constaté, correction éventuelle. La configuration reste sous le contrôle du propriétaire ; aucun mot de passe échangé.

### Nouvelle demande du client (Sprint 2)
> NovaCorp interdit toute passerelle sur le réseau interne ; prouvez que vos tests passent uniquement par le bridge privé.

4. Configurer `web01` en `10.10.10.10/24`, `app01` en `10.10.10.20/24`, sans passerelle sur la seconde NIC.
5. Tester ping et HTTP sur l'IP interne ; noter route, IP et résultats.
6. Désactiver puis réactiver une interface **interne uniquement** pour pratiquer le diagnostic et le retour arrière.

## Preuves de validation
- [ ] `ip -br addr` dans chaque invité : IP correctes
- [ ] `ip route` : pas de nouvelle route par défaut
- [ ] `curl -I http://10.10.10.20` depuis web01 : réponse attendue

## Parcours de repli
Si `web01` KVM ne fonctionne pas, utiliser deux CT LXC distincts sur `vmbr1` et comparer la topologie à la démonstration VM. Ne jamais toucher `vmbr0` pour les tests.

## Rendu individuel : `M04.md`
Utiliser [le modèle de compte rendu](../docs/modele-rendu-interactif.md) et produire **1 à 2 pages hors captures utiles** : hypothèse, manipulations, preuve, retour de revue croisée, décision NovaCorp, rollback et apprentissage.

**Ressources :** [TP](tp.md) · [Commandes](commands.md) · [Troubleshooting](troubleshooting.md) · [Validation](validation.md) · [Revue croisée rapide](../docs/revue-croisee-rapide.md).
