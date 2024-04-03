# **Serveur DHCP**

- Cliquer sur Nouvelle
- Ouvre un Fichier (Crée une Machine Virtuelle)

-Etape 1:

    - Nom (Nommer le nom de votre machine)
    - ISO (Récupérer l'iso de "Windows 10/11 ou linux")
    - Cocher la case (Skip Unattended Installation)
    - Faite Suivant

-Etape 2:

    - Configuration 
    - Réseau (Réseau interne)
    - Advanced (Allow All)
    - OK démarrer la VM

-Etape 3:

    - Install Windows server 2022 (Expérience de bureau) Suivant
    - accepte l'installation
    - Choisir le lieux de l'installation (Personnelle)
    - installation du système d'exploitation
    - Redémarrage automatique de la VM

-Etape 4:

    - Crée un mot de passe
    - Entré le mot de passe qui Vien d'être crée

-Etape 5: 
    
    - Serveur local
    - Cliquer sur l'adresse IPv4
    - Ouvre la fenêtre connexion réseau 
    - Clique sur Ethernet 
    - Propriété
    - Protocole internet version 4 (TCP/IPv4)
    - Utiliser l'adresse IP suivante ; 192.168.1.2
    - Masque de sous réseau ; 255.255.255.0
    - Passerelle par défaut ; 192.168.1.14
    - OK
    - Renommer le serveur
    
-Etape 6: 

    - Tableau de bord
    - Ajouter des rôle et des fonctionnalités
    - suivant
    - Suivant
    - Suivant
    - Serveur DHCP
    - suivant
    - suivant
    - installer
    
    
-Etape 7:

    - Gestionnaire du serveur DHCP
    - Outil
    - DHCP
    - Dérouler le serveur
    - Clique droit sur IPv4
    - Nouvelle étendue
    - Suivant
    - Nom de de l'étendue 
    - Suivant
    - Adresse IP de début ; 192.168.1.1
    - Adresse IP de Fin ; 192.168.1.15
    - Longueur ; 24/
    - Masque de sous-réseau ; 255.255.255.0
    - Suivant
    - Suivant
    - Suivant
    - Cocher la case (Non , je configurerai ces option ultérieurement)
    - suivant
    - Terminer

# **Serveur WDS :**

-Etape 1:

    - Gérer
    - Ajouter des rôle et des fonctionnalité
    - suivant
    - suivant
    - Suivant
    - Cocher la case (Windows Déploiement Service)
    - Suivant
    - Suivant
    - Suivant
    - cocher la case (Redémarrage automatiquement)
    - installer
    
-Etape 2:

- Configuration du client PXE

-Etape 1:

    - Nom (Nommer le nom de votre machine)
    - Faite Suivant
-Etape 2:

    - Système
    - Ordre d'amorçage
    - Mètre le réseau en premier
    - Réseau
    - Name (Interne)
    - Advanced (Allow ALL)
    - OK
    - Démarrer