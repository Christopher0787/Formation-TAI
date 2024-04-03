# **SERVEUR WDS ET DHCP :**

# **Créer une VM :**

configuration , réseau , mode accéder réseau (Réseau interne)
environnement bureau
périphérique , lecteur optique , choisir iso 



# **Installer le serveur DHCP**

# **Créer une partition de disque:**

- Clic droit sur Windows
- Gestion des disque
- Clic droit sur le disque c
- Réduire le volume
- Réduire
- 38,64 Go non alloué
- Nouveau volume simple
- suivant
- suivant
- Suivant
- Système du fichier (NTFS)
- Taille d'unité d'allocation (par défaut)
- Non du disque E (suivant)
- Non du volume (WDS)
- Cocher la case (Effectuer un formatage rapide) 
- suivant
- Terminer

# **Configurer WDS:**

- Outil 
- Service de déploiement Windows
- Déroule
- clic droit sur le non de mon serveur
- Configurer le serveur
- suivant
- Serveur autonome
- Suivant
- parcourir
- Ce PC
- Sélectionner la partition que l'on vient de créé 
- Créer un nouveau dossier
- Dossier RemoteInstall
- Suivant
- Suivant
- Répondre à tous les ordinateurs client (connus et inconnus)
- suivant
- Terminer
- Clic droit sur mon serveur
- Toute les tâches
- Démarrer
- CTRL + F
- Périphérique
- Lecteur optique
- Choisir un ISO
- Vérifier que l'iso a bien été sélectionner
- service de déploiement 
- clic droit sur image de démarrage
- Enplacement du fichier (parcourir)
- lecteur de CD 
- source
- boot.wim
- Ouvrir
- Suivant
- Suivant
- Suivant
- Terminer

# **image d'installation**

- Clique droit Ajouter une image d'installation
- Créer un groupe d'image nommé (parcourir)
- Install.wim
- Sélectionner Windows 10 pro
- Suivant
- Terminer

# **Service de d'eploiment**

- Mon serveur
- Clique droit
- Toute les taches

## **DHCP**

- Mon serveur
- clique droit 
- Toute les taches


- Mettre une IPv4 
- Renonomer le serveur 
- Outil
- DHCP
- Développer ipv4 