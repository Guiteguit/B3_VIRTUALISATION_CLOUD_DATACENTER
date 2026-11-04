# M02 — TP individuel

## Mission
NovaCorp réceptionne son premier hôte de virtualisation pve01.

**Objectif :** Créer une VM Proxmox imbriquée, installer l'hôte et vérifier l'interface et les services.

## Étapes (environ 60 min)
1. Télécharger l'ISO Proxmox VE depuis le site officiel et vérifier la somme SHA256 publiée pour la version choisie.
2. Créer sous VMware Workstation une VM Linux 64 bits : 4 vCPU, 8 Go RAM, disque virtuel 80 Go, réseau NAT ; activer l'exposition de la virtualisation matérielle.
3. Démarrer l'ISO et installer Proxmox sur le DISQUE VIRTUEL de cette VM, en choisissant un mot de passe de laboratoire non réutilisé.
4. Configurer nom pve01.novacorp.test, adresse IP compatible avec le réseau NAT de VMware et DNS fonctionnel.
5. Accéder depuis le poste à https://IP_DE_PVE:8006 ; accepter le certificat auto-signé uniquement dans ce laboratoire.
6. Contrôler version, services, accès réseau et stockage local ; renseigner lab-preflight.md.

## Journal des opérations
Dans votre rendu, consignez pour chaque étape : **commande ou action**, **résultat constaté**, **preuve**, **erreur éventuelle et correction**.

## En cas de blocage
Consultez [commands.md](commands.md) puis [troubleshooting.md](troubleshooting.md), revenez à votre dernier état stable et documentez l'échec. N'improvisez pas de modification sur la carte de management ou un disque système.

## Rendu
Vérifiez tous les éléments de [validation.md](validation.md). Répondez aux questions : quel risque opérationnel avez-vous rencontré ? Comment éviteriez-vous ce risque en entreprise ?
