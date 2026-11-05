# Cartes missions NovaCorp — 8 modules

Les cartes sont faites pour des échanges **courts** et non pour ajouter un deuxième TP. Le formateur annonce la mission au début et introduit une variante simple au second sprint.

## M01 — module01-foundations
**Brief client :** Le client souhaite réduire son parc physique : quels services virtualiser et avec quel type d'hyperviseur ?

**Question de départ :** Avant la réponse, faire comparer VM, LXC et cloud avec 3 hypothèses motivées.

**Revue croisée :** Auditer en binôme l'inventaire matériel et la conclusion GO/RISQUE/BLOQUÉ d'un camarade.

**Changement de besoin :** La direction impose 16 Go RAM par poste : revoir les tailles de VM et les risques de surallocation.

**Rendu spécifique :** Fiche de compatibilité + schéma, puis décision d'architecture en 3 phrases.

## M02 — module02-proxmox-install
**Brief client :** Votre équipe doit installer PVE01 sur le matériel fourni et garantir son accès d'administration.

**Question de départ :** Chaque étudiant donne le plan IP qu'il pense employer et pourquoi, avant installation.

**Revue croisée :** Un pair vérifie l'accès 8006, l'IP, les services et l'état /dev/kvm sans demander le mot de passe.

**Changement de besoin :** Le client annonce que l'accès réseau n'est pas standardisé : comment trouver la passerelle du NAT VMware ?

**Rendu spécifique :** Preuve d'accès 8006 + fiche préflight signée par vérification croisée.

## M03 — module03-vm-lxc
**Brief client :** NovaCorp veut héberger un site web et un petit service Linux, sans gaspiller la mémoire.

**Question de départ :** Voter VM ou LXC pour chaque workload, et défendre le choix en 30 secondes.

**Revue croisée :** L'auditeur mesure le CPU/RAM et vérifie le service HTTP sur le laboratoire du camarade.

**Changement de besoin :** Le client veut réduire la RAM consommée : justifier si un service peut passer en LXC.

**Rendu spécifique :** Tableau VM/LXC avec mesures, HTTP validé et justification de placement.

## M04 — module04-networking
**Brief client :** Isoler le trafic applicatif de l'administration tout en gardant la communication web↔app.

**Question de départ :** Dessiner la topologie NAT VMware / vmbr0 / vmbr1, sans toucher au clavier.

**Revue croisée :** Le NOC utilise ping, ip route et curl pour tester les interfaces secondaires sur l'environnement d'un pair.

**Changement de besoin :** Le client interdit une passerelle sur le réseau interne : prouver que vmbr1 est isolé.

**Rendu spécifique :** Schéma annoté + matrice de tests réseau et preuves de séparation.

## M05 — module05-storage
**Brief client :** Le serveur web manque d'espace pour ses fichiers applicatifs.

**Question de départ :** Faire identifier à la classe disque logique, disque physique et thin provisioning.

**Revue croisée :** Un pair contrôle la sortie lsblk AVANT partitionnement et vérifie que le disque système ne sera pas écrasé.

**Changement de besoin :** Le client impose un redémarrage : le volume doit remonter automatiquement.

**Rendu spécifique :** Sorties lsblk/findmnt, fstab par UUID et test après redémarrage.

## M06 — module06-backup-restore
**Brief client :** Une erreur applicative efface un fichier critique : la direction demande une preuve de reprise.

**Question de départ :** Comparer snapshot et backup ; anticiper RPO/RTO à l'oral.

**Revue croisée :** Un pair joue l'auditeur et demande la preuve du fichier récupéré sur un CT distinct.

**Changement de besoin :** Le client annonce une panne de l'hôte entier : expliquer pourquoi le backup local est insuffisant.

**Rendu spécifique :** Journal d'horodatage + sauvegarde, restauration ID 201, données récupérées, RTO mesuré.

## M07 — module07-security-troubleshooting
**Brief client :** Deux tickets de production arrivent au support : HTTP KO et communication réseau dégradée.

**Question de départ :** Classer les hypothèses par couche avant toute commande.

**Revue croisée :** Le NOC d'un autre binôme fournit un symptôme ; l'étudiant doit annoncer son prochain test et la preuve attendue.

**Changement de besoin :** Le client exige un compte rendu sans commandes au hasard, cause racine et rollback inclus.

**Rendu spécifique :** Deux tickets d'incident courts avec diagnostic, correction et test après changement.

## M08 — module08-templates-cloudinit
**Brief client :** NovaCorp demande une deuxième VM Debian identique, déployable en quelques minutes.

**Question de départ :** Estimer le temps d'installation manuelle et l'intérêt du modèle ; distinguer clone complet / lié.

**Revue croisée :** L'auditeur vérifie identité de la VM, IP, cloud-init status et absence de secrets en clair.

**Changement de besoin :** Le client veut 3 VM identiques demain : argumenter une stratégie templates/cloud-init sans Terraform.

**Rendu spécifique :** Template 9000, clone 102, commandes de vérification et mini retour d'expérience.

