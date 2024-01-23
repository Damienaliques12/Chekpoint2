## Q.1.1 Pourquoi le ping avec les adresses IP des machines ne fonctionnent pas ?

Les machines n'appartiennent pas au même réseau, elles ne peuvent donc pas se ping sans l'aide d'un routeur.

## Q.1.2 Le ping avec le nom des machines ne fonctionne pas.

Le ping avec le nom des machines ne fonctionne pas car les machines ne sont pas renseignées dans la configuration du serveur DNS. Pour les ajouter, on crée une zone de recherche directe. Une fois créée, on ajoute des hôtes en renseignant le nom des machines et en les associant à leur adresse IP respective. Une fois terminé, on ajoute aussi les machines dans la zone de recherche inversée en associant l'IP au nom de la machine.

## Q.1.3 Modifie la configuration réseau du client pour qu'il soit en DHCP.

Il faut se rendre dans les paramètres réseau, puis "changer les paramètres de la carte réseau". On modifie les propriétés en double-cliquant sur IPv4 et on définit l'adressage en DHCP. Il y a une exclusion de la plage 1 à 19.

## Q.1.4 Est-ce que ce client peut avoir l'adresse IP 172.16.10.15 en DHCP ?

Il faut faire une réservation de l'adresse IP 172.16.10.15 avec l'adresse MAC du client :
- Ouvrir le Gestionnaire de serveur.
- Cliquez sur Outils, puis sélectionnez DHCP.
- Sélectionner l'étendue.
- Cliquez droit sur "Réservations".
- Nouvelle Réservation.
- Saisir l'adresse IP qu'on souhaite réserver.
- Saisissez l'adresse MAC du client pour lequel on veut créer la réservation.
- Cliquez sur Ajouter, puis Fermer pour terminer la création de la réservation.
