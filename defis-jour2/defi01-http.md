# Défi 1 — « Ping OK, site KO » (20 minutes)

Le client NovaCorp appelle : « Je ping le serveur applicatif, mais le site web ne fonctionne pas. Il faut corriger le DNS ! »

Données connues :

```text
web01$ ping -c 2 10.10.10.20
2 packets transmitted, 2 received, 0% packet loss

web01$ curl -I --max-time 3 http://10.10.10.20
curl: (7) Failed to connect to 10.10.10.20 port 80: Connection refused

app01$ ip -br addr show eth1
eth1 UP 10.10.10.20/24

app01$ systemctl is-active nginx
inactive
```

## À produire
1. Précisez **ce que le ping prouve**, et ce qu'il ne prouve **pas**.
2. Le client a-t-il raison d'affirmer que c'est nécessairement DNS ? Expliquez à partir des preuves, sans supposer de faits invisibles.
3. Choisissez **deux commandes de lecture** à exécuter ensuite. Pour chacune, annoncez le résultat attendu et ce qu'il permettrait de conclure.
4. Proposez la **correction la plus petite et réversible**, puis une validation depuis web01.
5. Expliquez dans quel cas vous auriez plutôt cherché un problème de bridge Linux ou de routage.

**Variante orale :** le formateur peut demander « Et si `curl` renvoyait un timeout plutôt qu'un refus de connexion ? »

Aucune injection de panne requise : le cas peut être résolu sur papier ou à partir de vos propres commandes d'observation.
