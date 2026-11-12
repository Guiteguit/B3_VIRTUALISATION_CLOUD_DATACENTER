# NovaCorp — Contrôle de compréhension (Jour 2)

**Format :** 7–8 B3, en individuel, 90 minutes, sur votre laboratoire Proxmox si disponible. **IA autorisée** ; ce sont vos **hypothèses, preuves et explications** qui seront évaluées.

**Objectif :** valider les acquis des modules M01–M04 avant d'aller plus loin sur le stockage, la sauvegarde et Cloud-Init. Aucun classement entre étudiants.

## Déroulement
| Temps | Défi | Production |
|---|---|---|
| 0–5 min | Brief | Reprendre l'état de votre lab et les règles de sécurité |
| 5–25 min | [Défi 1 : Ping ≠ application](defi01-http.md) | Diagnostic argumenté |
| 25–45 min | [Défi 2 : KVM / ressources](defi02-kvm.md) | Raisonnement, commandes, interprétation |
| 45–65 min | [Défi 3 : réseau virtuel](defi03-reseau.md) | Trajet réseau et procédure de correction |
| 65–80 min | [Défi 4 : choix d'architecture](defi04-architecture.md) | Décision et risques |
| 80–90 min | Soutenance flash | Une question orale + dépôt de la fiche |

## Règles d'engagement
1. **Avant de demander à l'IA**, écrire une hypothèse et le résultat attendu d'un test. Vous pouvez ensuite comparer avec les réponses de ChatGPT/Claude.
2. Ne pas exécuter de commande que vous ne savez pas expliquer ; noter les conseils de l'IA que vous avez rejetés et pourquoi.
3. Pour chaque défi, fournir **une preuve**, **une explication**, **une correction minimale ou un plan de vérification**, **un rollback**.
4. Si votre environnement n'est pas prêt, les traces fournies suffisent : pas besoin de casser une VM pour réussir.
5. Ne jamais modifier le réseau de management `vmbr0`, désactiver les protections Windows ou formater un disque système pour ces exercices.

## Rendu unique
Rendre `defis-jour2-MON-PRENOM.md` ou une copie du [modèle](modele-rendu.md), sans identifiant sensible, mot de passe ou clé privée.
