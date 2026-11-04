# Plan réseau du laboratoire

| Élément | Réseau | Adressage |
|---|---|---|
| VMware NAT / management Proxmox | vmbr0 | Via paramètres locaux VMware ; IP PVE fixe adaptée au NAT |
| Réseau privé NovaCorp | vmbr1 | 10.10.10.0/24, pas de passerelle |
| web01 (2e NIC) | vmbr1 | 10.10.10.10/24 |
| app01 (2e NIC) | vmbr1 | 10.10.10.20/24 |

**Pourquoi pas d'IP de management universelle ?** Le sous-réseau VMware NAT dépend de chaque poste. Le relever plutôt que copier une valeur qui provoquerait des conflits.

**Tests en ordre :** lien de l'interface → adresse/masque → route → ping → port/service → DNS. Ne pas modifier la carte de management pour tester vmbr1.
