# M07 — Cours et notions à comprendre

## 1. Notion essentielle
L'interface d'administration sur 8006 doit être protégée : moindre privilège, authentification robuste, mises à jour contrôlées et accès réseau restreint.

## 2. Notion essentielle
La méthode symptomatique → hypothèses → preuves → correction → validation → rollback réduit les modifications hasardeuses.

## 3. Notion essentielle
Séparer état du service, port à l'écoute, connectivité IP et résolution DNS pour isoler une panne.

## 4. Notion essentielle
Un pare-feu Proxmox mal activé peut couper l'accès de gestion : n'activer aucune règle bloquante sans accès console et procédure de retour arrière.

## Questions de compréhension
1. Quels composants de l'architecture NovaCorp sont concernés par ce module ?
2. Quelle est la différence entre l'état attendu et une configuration dégradée ?
3. Quelle preuve technique démontre que la manipulation a réussi ?

## Pour aller plus loin
- [Documentation officielle Proxmox VE](https://pve.proxmox.com/pve-docs/)
- [Documentation Debian](https://www.debian.org/doc/)
