# **Connexion SSH et Gestion des Clés**
---


## **Ce chapitre explique comment établir des connexions SSH sécurisées, gérer les clés SSH et effectuer des tâches liées à la gestion des connexions à distance.**
---


## **Introduction**
---


* SSH, acronyme de "Secure Shell", est un protocole de communication sécurisé largement utilisé pour établir desconnexions réseau chiffrées entre un client et un serveur. 

* Il offre une méthode fiable et sécurisée pour accéder à des systèmes distants, transférer des fichiers et exécuter des commandes à distance.

* Ce dernier a remplacé des protocoles plus anciens et moins sécurisés tels que Telnet, en fournissant un moyen de communication cryptée, ce qui signifie que les données échangées entre le client et le serveur ne peuvent pas être interceptées.
---


## **Installation du serveur SSH**
---


* **Pour pouvoir se connecter à un hôte distant, il faut que ce dernier possède un serveur ssh :**

    "sudo apt install openssh-server"


* Vous devez également connaître l'adresse Ipv4 OU Ipv6 de l'hôte distant :

    "ifconfig"


* Cette commande permet d'afficher la configuration réseau. Il est possible qu'elle ne soit pas installé de base, il faut l'installer avec sudo apt install net-tools

* Une fois la commande if config exécutée, l'adresse ip se trouve ici :

    "inet 192.168.1.42"
---