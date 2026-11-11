# M02 — Atelier interactif : mettre PVE01 en service

**Durée : 90 min, à condition de préparer les médias avant le cours.**  
**Mission NovaCorp :** « Installez le premier hyperviseur et apportez une preuve qu'il est administrable. L'IP varie d'un poste à l'autre : pas de copier-coller d'un adressage voisin. »

## Préparation indispensable AVANT la séance
- ISO Proxmox VE officielle, somme SHA256 et VMware Workstation Pro disponibles.
- Espace disque libre vérifié ; réseau VMware NAT identifié.
- **Installer Proxmox sur le disque virtuel de la VM**, pas sur Windows.
- 4 vCPU, 8 Go RAM, ~80 Go disque virtuel ; exposer VT-x/AMD-V **si la plateforme l'autorise**.
- Le formateur a testé la même version ISO sur un PC comparable.

## Déroulement pour les étudiants

| Minute | Activité | Travail personnel / interaction | Preuve attendue |
|---|---|---|---|
| 00–10 | Brief de mise en production | Formuler une hypothèse : de quelles preuves a-t-on besoin pour considérer l'hyperviseur opérationnel ? | Liste de 3 tests |
| 10–20 | Micro-démo | Regarder 1 installation guidée : disque **virtuel**, carte NAT, hostname, console | Paramètres de la VM notés |
| 20–50 | Sprint A : installation | Créer la VM, installer Proxmox, identifier IP de management et gateway VMware NAT | Écran de console Proxmox |
| 50–58 | Revue binôme | Le pair vérifie **le plan IP**, le nom et les ressources en **observant** l'écran (sans mot de passe partagé) | Une vérification documentée |
| 58–75 | Sprint B : mise en service | Ouvrir `https://IP_PVE:8006`, puis vérifier version, services, routes et KVM sur console | 3 preuves : 8006, version, réseau |
| 75–85 | Incident client | Si 8006 échoue, isoler URL/IP/NAT/service ; si tout fonctionne, expliquer comment retrouver la passerelle | Ticket diagnostic très court |
| 85–90 | Rendu | Déposer `M02.md` et statut KVM **confirmé / bloqué / non vérifié** | Check-list + issue éventuelle |

## Plan de rattrapage si les installations sont lentes
La priorité absolue est **installer Proxmox et atteindre 8006**. Si plus de 2 étudiants sont encore sur l'installateur à la minute 55 :
1. Supprimer la variante client et réduire la revue à **2 min** ;
2. Afficher la procédure de console réseau au tableau ;
3. Conclure par la preuve des étapes atteintes ; programmer une remise à niveau avant M03, ou utiliser la VM de secours préinstallée par le formateur.

**Ne pas** accélérer en désactivant des protections Windows ni en demandant aux étudiants de recopier l'IP d'un voisin.

## Validation GO / RISQUE / BLOQUÉ
| État | Condition |
|---|---|
| GO pour KVM | PVE répond sur 8006 **et** /dev/kvm existe **et** une VM KVM de test démarre réellement (si cela a pu être vérifié) |
| RISQUE | PVE répond, mais lancement KVM non encore testé |
| BLOQUÉ KVM | PVE répond, mais KVM imbriqué absent ou incapable de démarrer |
| BLOQUÉ installation | PVE non accessible ou installation incomplète |

Un étudiant **bloqué KVM** continue les prochains TP sur LXC lorsque possible et documente la démonstration KVM.

[Consignes TP classiques](tp.md) · [Commandes](commands.md) · [Troubleshooting](troubleshooting.md)
