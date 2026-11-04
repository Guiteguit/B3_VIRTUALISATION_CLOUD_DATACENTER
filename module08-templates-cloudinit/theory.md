# M08 — Cours et notions à comprendre

## 1. Notion essentielle
Un template est une base non démarrée à cloner ; clone complet vs clone lié selon les capacités du stockage.

## 2. Notion essentielle
Cloud-Init applique des paramètres de premier démarrage (compte, clé SSH, réseau, hostname) à des images compatibles.

## 3. Notion essentielle
Une image cloud Debian peut être importée dans Proxmox avec qm importdisk ; vérifier modèle de disque, contrôleur et cloud-init drive.

## 4. Notion essentielle
Pour un laboratoire, utiliser DHCP sur le réseau NAT initial si disponible et des clés SSH de démonstration, jamais des identifiants réels.

## Questions de compréhension
1. Quels composants de l'architecture NovaCorp sont concernés par ce module ?
2. Quelle est la différence entre l'état attendu et une configuration dégradée ?
3. Quelle preuve technique démontre que la manipulation a réussi ?

## Pour aller plus loin
- [Documentation officielle Proxmox VE](https://pve.proxmox.com/pve-docs/)
- [Documentation Debian](https://www.debian.org/doc/)
