# Parcours interactif — Travail individuel, échanges courts

## Pourquoi ce format ?
Chaque étudiant garde **son propre laboratoire Proxmox** et ses propres livrables. Les échanges ne remplacent pas l'apprentissage technique : ils aident à expliquer les choix, détecter les erreurs et valider le fonctionnement. Pas de Final Boss.

## Rituel de 90 min
| Temps | Phase | Ce qu'on attend |
|---|---|---|
| 00–10 | Brief client NovaCorp | Besoin, risque, hypothèse formulée oralement |
| 10–25 | Théorie + démonstration dialoguée | Une prédiction avant la manipulation |
| 25–50 | Sprint individuel 1 | Installation/configuration avec preuve intermédiaire |
| 50–60 | Revue croisée en binôme | 1 test effectué par un pair, 1 question posée |
| 60–80 | Sprint individuel 2 | Validation, variante métier ou dépannage léger |
| 80–90 | Débrief et dépôt | 1–2 restitutions tournantes de 60 s, fiche courte |

## Composition des binômes
Avec 7 étudiants : 3 binômes et 1 trinôme (rôles adaptés). Avec 8 : 4 binômes. **Le binôme fait la revue**, mais chacun travaille sur ses propres VMs ; un étudiant n'est pas chargé de toute la configuration de l'autre.

## Casquettes tournantes pendant la revue (sans hiérarchie)
- **Administrateur :** montre ce qu'il a implémenté et explique ses choix.
- **Auditeur :** vérifie l'état attendu avec une commande de lecture et exige une preuve.
- **NOC/exploitant :** teste l'accessibilité du service et identifie une éventuelle panne.
- **Architecte :** challenge le dimensionnement et la segmentation, sans modifier l'environnement de l'autre.

En binôme, alterner deux casquettes à chaque revue ; au module suivant, changer de rôle. La manipulation et la notation restent **individuelles**.

## Règles de revue
1. Demander au propriétaire son contexte et son objectif.
2. Choisir **une commande non destructive** et annoncer le résultat attendu avant exécution.
3. Observer la preuve ensemble. Ne pas échanger de mot de passe ni de clé privée.
4. Écrire une suggestion courte, respectueuse et actionnable.
5. Le propriétaire conserve le contrôle de ses changements et documente le feedback.

## Ce qu'il faut rendre à chaque module
- 1 fiche technique de 1–2 pages : état initial, changements, preuve, problème éventuel, rollback.
- 1 **décision NovaCorp** en 2–4 phrases : choix et raison.
- 1 **preuve de revue croisée** : test demandé par le pair et résultat, sans son nom complet obligatoire.
- 1 mini rétrospective : ce que j'ai compris / ce que je vérifierais en production.

**Ne pas déposer de secrets, de dumps sensibles ou de mots de passe dans GitHub.**

## Barème de participation formative (non pénalisant)
La revue, l'explication et les preuves enrichissent les critères de documentation/troubleshooting existants, sans points supplémentaires imposés. Un incident matériel empêchant KVM donne lieu à un rendu d'analyse équivalent.
