## Q.3.1
**Quel est le matériel réseau A ?**
**Quel est son rôle sur ce schéma vis-à-vis des ordinateurs ?**

Le matériel réseau A est un switch de niveau 2. Son rôle est de relier les ordinateurs entre eux pour qu'ils puissent communiquer via leurs adresses MAC. 
Il relie également les ordinateurs au routeur B.

## Q.3.2
**Quel est le matériel réseau B ?**
**Quel est son rôle pour le réseau 10.10.0.0/16 ?**

Le matériel réseau B est un routeur. Il permet au réseau 10.10.0.0/16 de communiquer avec d'autres réseaux grâce aux adresses IP, notamment le réseau Internet.

## Q.3.3
**Que signifie f0/0 et g1/0 sur l’élément B ?**

f0/0 correspond à la première interface "FastEthernet" du routeur sur laquelle on branche des câbles RJ45. g1/0 correspond à la première interface GigaEthernet du routeur sur laquelle on branche des câbles fibre.

## Q.3.4
**Pour l'ordinateur PC2, que représente /16 dans son adresse IP ?**

Il représente le CIDR. Il signifie que les 16 premiers bits de l'adresse IP correspondent à l'adresse du réseau.

## Q.3.5
**Pour ce même ordinateur, que représente l'adresse 10.10.255.254 ?**

L'adresse 10.10.255.254 est la passerelle de l'ordinateur PC2. Elle correspond à l'interface du routeur qui communique avec le même réseau que l'ordinateur. Lorsqu'un protocole IP va être effectué avec une IP différente du réseau, il s'adressera directement à la passerelle.

## Q.3.6
**Pour les ordinateurs PC1, PC2, et PC5 donne :**
- L'adresse de réseau
- La première adresse disponible
- La dernière adresse disponible
- L'adresse de diffusion

**PC1 :**
- Adresse réseau : 10.10.0.0/16
- Première adresse disponible : 10.10.0.1/16
- Dernière adresse disponible : 10.10.255.254/16
- Adresse de diffusion : 10.10.255.255/16

**PC2 :**
- Adresse réseau : 10.11.0.0/16
- Première adresse disponible : 10.11.0.1/16
- Dernière adresse disponible : 10.11.255.254/16
- Adresse de diffusion : 10.11.255.255/16

**PC5 :**
- Adresse réseau : 10.10.0.0/15
- Première adresse disponible : 10.10.0.1/15
- Dernière adresse disponible : 10.11.255.254/15
- Adresse de diffusion : 10.11.255.255/15

## Q.3.7
**En t'aidant des informations que tu as fournies à la question 3.6, et à l'aide de tes connaissances, indique parmi tous les ordinateurs du schéma, lesquels vont pouvoir communiquer entre eux.**

Le PC1, 3 et 4 peuvent communiquer entre eux car ils sont sur le même réseau. 

## Q.3.8
**De même, indique ceux qui vont pouvoir atteindre le réseau 172.16.5.0/24.**

Seuls les PC appartenant au même réseau que l'interface f0/0 du routeur pourront communiquer avec le réseau 172.16.5.0/24. Ce sont donc les PC1, 3 et 4.

## Q.3.9
**Quelle incidence y a-t-il pour les ordinateurs PC2 et PC3 si on intervertit leurs ports de connexion sur le matériel A ?**

Il n'y aura aucune incidence pour les ordinateurs PC2 et PC3.

## Q.3.10
**On souhaite mettre la configuration IP des ordinateurs en dynamique. Quelles sont les modifications possibles ?**

Il faut intégrer un rôle DHCP relié au switch de niveau 2, soit par un serveur, soit sur un ordinateur directement.

# Fichier 1

## Q.3.11
**Sur le paquet N°5, quelle est l'adresse MAC du matériel qui initialise la communication ? Déduis-en le nom du matériel.**

00:50:79:66:68:00 - PC1

## Q.3.12
**Est-ce que la communication enregistrée dans cette capture a réussi ? Si oui, indique entre quels matériels, si non indique pourquoi cela n'a pas fonctionné.**

Oui, entre le matériel 00:50:79:66:68:00 et 00:50:79:66:68:03 (Request, Reply)

## Q.3.13
**Dans cette capture, à quel matériel correspond le request et le reply ? Donne le nom, l'adresse IP, et l'adresse MAC de chaque matériel.**

Request : PC1 - 00:50:79:66:68:00 - 10.10.4.1
Reply : PC4 - 00:50:79:66:68:03 - 10.10.4.2

## Q.3.14
**Dans le paquet N°2, quel est le protocole encapsulé ? Quel est son rôle ?**

Dans le paquet numéro deux, le protocole encapsulé est l'ARP, il sert à collecter les adresses MAC du réseau et à associer des adresses IP à des adresses MAC.

## Q.3.15
**Quels ont été les rôles des matériels A et B dans cette communication ?**

Le matériel A permet d'effectuer toute la communication entre le PC1 et le PC4. Le matériel B n'a pas grande utilité dans cette communication.

# Fichier 2

## Q.3.16
**Dans cette trame, qui initialise la communication ? Donne l'adresse IP ainsi que le nom du matériel.**

PC3 - 10.10.80.3/16

## Q.3.17
**Quel est le protocole encapsulé ? Quel est son rôle ?**

ICMP - son rôle est d'effectuer/vérifier une connexion entre deux machines.

## Q.3.18
**Est-ce que cette communication a réussi ? Si oui, indique entre quels matériels, si non indique pourquoi cela n'a pas fonctionné.**

Non, car les deux machines n'appartiennent pas au même réseau et PC2 ne peut pas communiquer avec le routeur.

## Q.3.19
**Explique la ligne du paquet N° 2**

Le paquet 2 indique que la requête ICMP n'a pas fonctionné. L'interface du routeur (passerelle) répond au PC3 que la requête n'a pas abouti.

## Q.3.20
**Quels ont été les rôles des matériels A et B ?**

Le matériel A a transmis la requête au matériel B qui a vérifié s'il avait accès au réseau demandé. Puis, il a envoyé la réponse d'erreur au matériel A qui l'a renvoyée au PC de destination.

# Fichier 3

## Q.3.21
**Dans cette trame, donne les noms et les adresses IP des matériels sources et destination.**

Source = PC4 - 10.10.4.2
Destination = 172.16.5.253

## Q.3.22
**Quelles sont les adresses MAC source et destination ? Qu'en déduis-tu ?**

Source = ca:01:da:d2:00:1c
Destination = ca:03:9e:ef:00:38

## Q.3.23
**À quel emplacement du réseau a été enregistrée cette communication ?**

Entre les deux routeurs (car le premier paquet est encapsulé par le protocole IPV4 fourni par le routeur).
