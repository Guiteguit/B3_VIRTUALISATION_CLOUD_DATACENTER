# M01 — Atelier interactif : décider avant de virtualiser

**Durée : 90 min · Mode : TP individuel + revues courtes par binômes**  
**Mission NovaCorp :** « Nous avons trois serveurs vieillissants. Proposez une première architecture virtualisée adaptée à notre budget et vérifiez que votre poste pourra servir de laboratoire. »

## Livrables à conserver
1. `M01.md` fondé sur [le modèle individuel](../docs/modele-rendu-interactif.md).
2. Schéma : PC Windows → VMware Workstation → Proxmox → VM Debian / LXC.
3. Fiche de compatibilité : **GO / RISQUE / BLOQUÉ**, avec deux preuves et un plan B.

## Déroulement pour les étudiants

| Minute | Activité | Travail personnel / interaction | Preuve attendue |
|---|---|---|---|
| 00–10 | Brief NovaCorp | Noter les 3 besoins de l'entreprise et **choisir** entre VM et conteneur pour un service web | Décision en 2 phrases |
| 10–25 | Défi de compréhension | Répondre d'abord seul aux questions : « Proxmox = cloud ? », « Workstation = ESXi ? », « VM = LXC ? ». Comparer ensuite 2 réponses | Trois distinctions justifiées |
| 25–45 | Sprint A : préflight | Vérifier CPU, RAM, stockage, édition VMware, VT-x/AMD-V et paramètres Hyper-V/VBS **sans rien désactiver** | Captures/sorties annotées |
| 45–55 | Revue croisée | Le binôme contrôle les 2 preuves du voisin et pose une question non destructive | Une remarque actionnable |
| 55–75 | Sprint B : conception | Dessiner les couches et allouer CPU/RAM/disques ; réviser le plan pour 16 Go RAM au total | Schéma + budget ressources |
| 75–85 | Décision d'architecture | Chaque étudiant conclut GO / RISQUE / BLOQUÉ ; 2 volontaires défendent leur choix en 60 s | Fiche préflight complétée |
| 85–90 | Dépôt / sortie | Compléter le rendu court et écrire une question pour M02 | `M01.md` |

### Variante métier : « Le budget ne permet pas de changer les PC »
Vous disposez de **16 Go de RAM** par poste, dont Windows et VMware Workstation consomment une partie. Décrivez ce que vous devrez **arrêter** ou réduire au cours des prochains modules et pourquoi vous ne pourrez pas lancer sans limite de nouvelles VM.

### En cas de blocage matériel
- État KVM inconnu : statut **RISQUE**, pas « GO ».
- Proxmox pas encore installé : **ne pas prétendre avoir vérifié /dev/kvm**. Le M02 confirmera.
- Ne jamais désactiver Hyper-V, VBS ou un contrôle de sécurité du poste sans autorisation.
- La fiche de compatibilité reste un **diagnostic préliminaire**, à confirmer en M02.

### Questions finales
- Quels sont les points de défaillance de cette architecture monocœur/hôte ?
- Qu'est-ce qu'un hyperviseur virtualise que ne virtualise pas un conteneur LXC ?
- Quelle preuve technique te manque encore pour conclure que KVM imbriqué fonctionnera ?

[Consignes TP classiques](tp.md) · [Commandes](commands.md) · [Troubleshooting](troubleshooting.md)
