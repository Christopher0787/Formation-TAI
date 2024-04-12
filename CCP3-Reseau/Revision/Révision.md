# **Révision**

## **Classe IP :**

- A = 1.0.0.1 - 126.255.255.254       / Public  ------> 10.0.0.0 - 10.255.255.255    /8  |  16,7M  / Privé

- B = 128.1.0.1 - 191.255.255.254  /  Public  ------> 172.16.0.0 - 172.31.255.255    /16 | 1,04M  / Privé

- C = 192.0.1.1 - 223.255.254.254  / Public  -------> 192.168.0.0 - 192.168.255.255   /24 | 65,536 / Privé

- APIPA **(AUTOMATIQUE PRIVATE INTERNET PROTOCOL ADDRESSING )**= 169.254.0.0 - 169.254.255.255 /16  / Privé


- D = 224.0.0.0 - 239.255.255.255  /  Multicast -- Audio, Vidéo

- E =  240.0.0.0 -  255.255.255.255 / Militaire -- Future, Expérimentale

---

## **DHCP (DYNAMIC HOST CONFIGURATION PROTOCOL)**

- Client ---> Serveur / Protocol TCP/ UDP

- Serveur ---> Client / Protocol TCP / UDP

**Port -> DHCP**

- Client : 68 / UDP

- Serveur : 67 / UDP

---

## **DNS (DOMAIN NAME SYSTEM)**

- Port: 53 --> TCP / UDP

- Non de Domaine:

- TTL (TIME TO LIVE) duré de 30sec à 7j  --> 88.*.*.* - nathan.fr  89.*.*.*

---

## **Gérer les enregistrements DNS:**

- TTL = 14400 = 14400 4h

**Type :**

- **A** = Relier mon adresse IPv4 au nom de Domaine.

- **AAAA** = Relier mon adresse IPv6 au nom de Domaine.

- **CNAME (CANONICAL NAME)** = Permet de renseigner un nom canonique.

- **MX (MAIL EXCHANGE RECORD)** = Serveur de messagerie.

- **PTR (POINTER RECORD)** = Il permet la recherche inverser .

- **SRV (SERVICE LOCATOR RECORD)** = Spécifier l'emplacement d'un serveur VOIP (VOICE OVER INTERNET PROTOCOL).

- **NS (NAME SERVER)** = permet de changer le serveur DNS autoritaire sur le nom de domaine.

- **TXT**  = Texte qui contient des information indicatives.

- **SOA (START OF AUTHORITY)** = Information générales de la zone telles que son nom ou la date de dernière mise à jour.

- **NS (NAME SERVER)** = Informations sur le serveurs DNS du domaine.

- **ICANN (INTERNET CORPORATION for ASSIGNED NAME and NUMBERS)** --> Organisme qui gère les nom domaine 

- **AFNIC (ASSOCIATION FRANCAISE pour le NOMAGE INTERNET en COOP2RATION)**

- **Le FQDN (FULLY QUALIFIED DOMAIN NAME)** = WWW.Mon-site.fr 

**Arborescence DNS :**

- Racine -> TLD -> Domaine -> Hôte = FQDN

---

## **PING**

- Ping vérifier si les appareil communique

**ICMP (INTERNET CONTROL MESSAGE PROTOCOL)**

- ICMP ECHO --> Client envoi au SRV

- ICMP REPLY <-- SRV renvoi au Client

## **FICHER HOST**

- Explorateur de fichier -> disque C -> Windows -> System32 -> drivers -> etc

- Il consiste a mapper une adresse IP vers un nom d'hôte
Le nom convivial localhost tu mappe adresse IP vers un nom d'hôte convivial

- Bloquer des site

- Rediriger

- Personnaliser

## **CACHE ARP (ADDRESS RESOLUTION PROTOCOL)**

- Terminal cmd = Arp -a 

- Minimiser les temp de réponse

## **HUB / SWITCH**

- HUB = Il envoyer la requête a tous les PC

- SWITCH =  il envoi la requête au bon PC par apport a l'adresse MAC


## **OUVERTURE DES PORT ROUTEUR**

- DMZ (ZONE DEMILITARISEE)

- WAN -> FAI -> LAN -> DMZ 


## **UNICAST, MULTICAST,  BROADCAST**

- BROADCAST = t'envoi à tout le monde

- MULTICAST = t'envoi a un groupe

- UNICAST = t'envoi a une personne

## **TCP (TRANSMISSION CONTROL PROTOCOL)**

- La poigner de main en 3 temp 

- THREE-WAYS  HANDSHAKE

## **UDP (USER DATAGRAMME PROTOCOL)**

## **TYPE DE SERVEURS DNS :**

    1) - Résolveur récursif.

    2) - Serveur de noms racine.

    3) - Serveur de nom TLD (TOP LEVEL DOMAIN) / .com, .fr, .org . 

- Serveur de nom faisant autorité.

---