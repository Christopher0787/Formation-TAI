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
---


* **Vous devez également connaître l'adresse Ipv4 OU Ipv6 de l'hôte distant :**

    "ifconfig"
---


**Cette commande permet d'afficher la configuration réseau. Il est possible qu'elle ne soit pas installé de base, il faut l'installer avec sudo apt install net-tools**
---


* **Une fois la commande if config exécutée, l'adresse ip se trouve ici :**

    "inet 192.168.1.42"
---


## **Connexion à un hôte distant**
---


* **Ouvrez un terminal de commande et tapez :**

    "ssh nomUtilisateur@adresseIp"
---


* **Il faut remplacer adresseIp par l'IP de l'hôte distant.**

    "ssh -p 22 nomUtilisateur@adresseIp"
---


**L'option -p 22 permet de définir le port de connexion SSH.**


**Une fois connecté, le shell de votre hôte distant apparaitra.**

---


## **Utilisation des clés SSH ( Serveur )**
---


* **Pour préparer la connexion par clés, vous devezpréparer votre hôte distant.**


    "mkdir ~/.ssh"
---


* **Créez un dossier nommé .ssh dans votre home directory.**


    "chmod 700 ~/.ssh"
---


**Modifiez les permissions du dossier, 700 corréspond à :**


* Utilisateur : Lecture (4) + Écriture (2) + Exécution (1) = 7.

* Groupe : Aucune permission (0).

* Autres : Aucune permission (0).
---


    "cd ~/.ssh"


**Entrez dans le dossier**

    "touch authorized_keys"


**Créez le fichier qui contiendra lesclés publiques autorisées à se connecter à l'hôte distant.**


    "chmod 600 authorized_keys"
---


**Pour terminer, modifiez les permissions du fichier, 600 corréspond à :**


* Utilisateur : Lecture (4) + Écriture (2) = 6.

* Groupe : Aucune permission (0).

* Autres : Aucune permission (0).   
---