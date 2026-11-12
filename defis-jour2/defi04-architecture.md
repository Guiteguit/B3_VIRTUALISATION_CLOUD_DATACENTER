# Défi 4 — « Le meilleur choix n'est pas toujours Proxmox » (15 minutes)

NovaCorp veut héberger :

- un serveur web Linux léger ;
- une application interne Linux ;
- une base de données dont la perte de données serait coûteuse ;
- une machine Windows nécessitant son propre noyau ;
- le tout sur **un seul hôte physique** avec une sauvegarde locale.

Un consultant propose : « Mettez tout en LXC, créez un snapshot avant chaque mise à jour et vous avez de la haute disponibilité. »

## À produire
1. Relevez au moins **trois affirmations trompeuses ou risques** dans sa proposition.
2. Proposez où placer chaque service (VM / conteneur), avec une justification succincte.
3. Expliquez pourquoi un hôte unique ne fournit pas une vraie haute disponibilité.
4. Quelles deux mesures simples amélioreront la protection des données sans créer de cluster ?
5. Préparez une **défense orale de 45 secondes** de vos choix, compréhensible par un responsable non technique.

Il n'existe pas une seule architecture parfaite. On évalue la cohérence, les risques identifiés et la justification.
