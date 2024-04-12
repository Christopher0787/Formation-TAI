# **CISCO Packet Tracer**

- Fondée en 1984

- Leader de solution réseau et de cybersécurité

- Router -> Commutateur -> Par-Feu

- Packet Tracer pour simulation réseau

## **Etape 1 :**

    - Google

    - Télécharger packet tracer
    
## **Etape 2 :**

    - Cliquer sur le premier lien cisco
    
## **Etape 3 :**

    - Cliquer sur Afficher le cours

## **Etape 4 :**

    - Cliquer sur Skills For All
    
## **Etape 5 :**

    - Cliquer sur Démarrer
    
## **Etape 6 :**

    - Cliquer sur Google
    
## **Zone 1 :**

    - Les différents menus de l'outil
    
## **Zone 2 :**

    - Les équipements qu'on peut simuler
    
## **Zone 3 :**

    - Zone de création de la topologie
    
- Cliquer sur "End Devive"

- Vous pouvez maintenant choisir différent type d'appareils.

- Séléctionner "PC"

- Placer DEUX "PC"

- Cliquer sur : "Network devices"

- Puis sur : "Switches"

- Sélectionnez : "2960"

- Cliquer sur : "Connections"

- Connectez les deux PC ensemble en passant par le commutateur (Switch)

- Ajouter une adresse IP à chaque PC.

- 1: Clique gauche sur le PC

- 2: Aller dans le menu "Config"

- 3: Cliquer sur "FastEthernet0"

- 4: Mettre une IP statique

- 5: Valider en cliquant sur la croix
 

- Ajouter une étiquette à chaque PC

- Cliquer sur "Place note" ou sur la touche "N"
 

- Testez La connexion :

- 1: Cliquer sur le "PC1"

- 2: Cliquer sur "Desktop"

- 3: Cliquer sur "Command Prompt"

- Remplacez le Switch 2960 par un Routeur 4431

## **Etape 1 :**

    - Cliquer sur "Delete" puis faire un clique gauche sur le Switch 2960

## **Etape 2 :**

    - Rétablir la connexion en cliquant sur "Connections"

## **Etape 3 :**

    - Activez l'affichage des ports sur la topologie.

- 1: Allez dans "Option"

- 2: Allez dans "Préférances"

- Cliquer sur : Always Show Port Labels In Logical Workspace

- Régler le problème de connexion

## **Etape 1 :**

    - Changer l'adresse du second PC.

## **Etape 2 :**

    - Activer les ports du routeur.


- Aller dans l'onglet "CLI" du Routeur.

- 1: Clic gauche sur le routeur.

- 2: Cliquer sur l'onglet "CLI"

- Entrez la commandes :

- No # appuyez sur entrer

- Enable

- Interface gigabitEthernet 0/0/0

- Ip address 192.168.0.254 255.255.255.0

- No shut

---

- Entrez la commandes :

- No # appuyez sur entrer

- Enable

- Interface gigabitEthernet 0/0/1

- Ip address 192.168.1.254 255.255.255.0

- No shut


- Tous nos ports sont vert !


- Testez la connexion

- Configurez la passerelle

## **Etape :**

    - 1: Cliquer sur le "PC0"

    - 2: Aller sur l'onglet "Desktop"

    - 3: Cliquer sur "IP Configuration"

    - 4: Dans "Default Gateway" entrez 192.168.0.254

---

    - 1: Cliquer sur le "PC1"

    - 2: Aller sur l'onglet "Desktop"

    - 3: Cliquer sur "IP Configuration"

    - 4: Dans "Default Gateway" entrez 192.168.1.254

---

# **Prise en main du CLI :**

## **Configuration du VLAN sur un commutateur (CISCO) :**

## - Cliquer sur l'appareil cisco aller dans CLI taper enable, ensuite taper conf terminal Crée une vlan en tapent vlan 10

## - Exploration des mode d'exécution sur un commutateur cisco :

## - Enable pour etre en mode privilégier, Disable pour désactiver le mode privilégier, Exit pour quitter aussi

## - Configuration de accesse console sur un routeur cisco : Line console 0

## - Configuration d'une interface réseau sur un routeur cisco :

- Interface gigabitEthernet 0/0/0

- Ip address 192.168.1.1 255.255.255.0

- No shutdown

- Exit

---

- Utilisation des commande abreger sur un routeur cisco :

- En = enable

- Conf t = configure terminal

- Int F0/1 = interface FastEthernet0/1

- End = exit

---

- Configuration de l'interface SVI (Switched Virtual Interface)sur un commutateur réseau :


- conf t 

- int Gig0/1

- switchport mode trunk

- switchport trink native vlan 10

- exit exit

- show interface trunk

---

- vlan 20

- name Gestion

- int Gig0/1

- switchport mode access

---

- switchport access vlan 20

- exit

- int vlan 20

- no shut

- exit deux fois

- show vlan 

---

- exercice 5 création d’un vlan voiP

- conf t 

- vlan 30

- name Voix

- exit

- int Gig0/2

- switchport mode access

- switchport access vlan 30

---

- pour que la qualité soit optimale option à configurer le QOS

- mls qos

- auto qos voip cisco-phone

- exit

- précisément c'est le mode switchport mode Access mais faut configurer d'autres trucs avant comme dans l'exemple

---