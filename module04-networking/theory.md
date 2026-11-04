# M04 — Cours et notions à comprendre

## 1. Notion essentielle
vmbr0 est un bridge Linux, l'équivalent conceptuel d'un commutateur virtuel ; il peut être relié à une interface physique ou virtuelle.

## 2. Notion essentielle
Dans un laboratoire imbriqué, la carte Proxmox est elle-même une carte virtuelle de VMware ; le NAT VMware ne doit pas être confondu avec un bridge Proxmox.

## 3. Notion essentielle
Un bridge isolé sans port physique permet une communication interne mais n'apporte ni DHCP, ni NAT ni routage automatiquement.

## 4. Notion essentielle
Adressage IPv4 statique, routes, ARP/voisinage, test DNS et écoute du service constituent une méthode de diagnostic progressive.

## Questions de compréhension
1. Quels composants de l'architecture NovaCorp sont concernés par ce module ?
2. Quelle est la différence entre l'état attendu et une configuration dégradée ?
3. Quelle preuve technique démontre que la manipulation a réussi ?

## Pour aller plus loin
- [Documentation officielle Proxmox VE](https://pve.proxmox.com/pve-docs/)
- [Documentation Debian](https://www.debian.org/doc/)
