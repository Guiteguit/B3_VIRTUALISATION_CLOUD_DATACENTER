# Défi 3 — « Même sous-réseau, aucun ping » (20 minutes)

NovaCorp dispose de deux workloads avec les paramètres suivants :

| Machine | IP / masque | Carte | Bridge Proxmox |
|---|---|---|---|
| web01 | 10.10.10.10/24 | net1 | vmbr1 |
| app01 | 10.10.10.20/24 | net1 | vmbr2 |

Les deux bridges `vmbr1` et `vmbr2` sont isolés et **n'ont pas de port physique**. Le réseau de management `vmbr0` ne doit pas être modifié.

Le client dit : « Les IP sont dans le même /24, il doit suffire d'ajouter une gateway ! »

## À produire
1. Dessinez le chemin attendu d'un paquet entre les deux machines.
2. Expliquez pourquoi le raisonnement « même /24 = forcément joignable » est incomplet.
3. Proposez **une seule modification minimale** pour rétablir les communications sans casser le management.
4. Donnez **deux commandes de validation** et leurs résultats attendus.
5. Quel est votre rollback si la modification ne donne pas le résultat souhaité ?

**Variante orale :** « Dans quel cas un routeur serait-il réellement nécessaire ? »

**Ne modifiez pas `vmbr0` ; le cas fourni est suffisant pour raisonner sans manipulation risquée.**
