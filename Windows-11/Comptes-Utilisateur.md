# **Comptes Utilisateur**

# **Identification et Authentification**

L'identification et l'authentification sont des processus essentiels pour accéder aux systèmes informatiques, notamment dans un environnement professionnel.

#  **Identification**

## **Accès Anonyme :** 
  - Permet un accès restreint aux ressources sans fournir d'identité spécifique.

## **Fourniture de l'Identité :**
  - Les identités peuvent être des numéros de client, des adresses e-mail ou des noms d'utilisateur, selon le contexte.

#  **Authentification**

## **Besoin d'Authentification :** 
  - Nécessaire pour prouver l'identité réelle de l'utilisateur.

## **Processus d'Authentification :** 
  - Implique la saisie d'une information unique connue de l'utilisateur, comme un mot de passe. La complexité de l'authentification est généralement définie par l'administrateur du système.

## **Guide d'Hygiène Informatique de l'ANSSI :** 
  - L'Agence nationale de la sécurité des systèmes d'information propose des ressources pour une gestion sécurisée de l'authentification et du contrôle d'accès.

- Ces processus sont cruciaux pour assurer la sécurité des systèmes informatiques en vérifiant l'identité des utilisateurs et en limitant l'accès aux seules personnes autorisées.

---

# **Choix des Comptes**

Les comptes locaux offrent une alternative indépendante des services Microsoft et des annuaires centralisés, idéale pour une utilisation hors ligne.

# **2.1 Comptes Locaux**

# **2.1.1 Création d'un Compte Local**

## **Définition** 
 - Un compte local fonctionne en mode hors ligne, permettant l'accès même sans connexion internet.

## **Types de Comptes sur Systèmes d'Exploitation Microsoft :**

  - **Comptes Utilisateurs :** Offrent un accès restreint aux tâches.
  - **Comptes Administrateur :** Fournissent un accès étendu pour les tâches administratives.

## **Étapes de Création ou Modification :**

  1. Accès aux Paramètres : Cliquez sur le menu Démarrer, puis sélectionnez Paramètres.
  2. Accès aux Comptes : Choisissez Comptes.
     - Sélectionnez "Famille et autres utilisateurs" ou "Autres utilisateurs".
  3. Ajout d'un Utilisateur :
     - Cliquez sur "Ajouter un autre utilisateur".
     - Sélectionnez "Je ne dispose pas des informations de connexion de cette personne".
     - Choisissez "Ajouter un utilisateur sans compte Microsoft".
  4. Saisie des Informations :
     - Entrez un nom d'utilisateur et un mot de passe.
     - Répondez aux questions de sécurité.
  5. Finalisation : Cliquez sur Suivant pour valider.

## **Modification du Type de Compte :**

  - Utilisez la flèche à droite du nom du compte.
  - Sélectionnez "Changer le type de compte".
  - Choisissez entre Utilisateur Standard et Administrateur dans le menu déroulant.
  - Validez avec OK.

La création et la modification des comptes locaux offrent une flexibilité et un contrôle accrus sur l'accès aux ressources, en fonction des besoins spécifiques de l'utilisateur.

---

# **Droits des Groupes d'Utilisateurs dans Windows 11**

Dans Windows 11, les droits des groupes d'utilisateurs sont définis pour assurer une utilisation sécurisée et efficace du système.

## **2.1.2 Droits du Groupe Utilisateurs**

 - **Usage Quotidien** : idéal pour la navigation internet, création de fichiers/dossiers, lancement d'applications. 

 - **Pour Ordinateurs Personnels** : Convient aux comptes individuels au sein d'une famille. 

# **Remarque sur la Sécurité**

 - **Accés Limité et Restreint** : Prévention de l'installation de logiciels malveillants sans autorisation de l'administrateur.

## **2.1.3 Droits du Groupe Administrateurs**

## **Compte Administrateur**

 - **Création Automatique** : Un compte Administrateur est créé lors de l'installation de Windows 11.

 - **Compte Par Défaut**  : Ne peut être supprimé, mais peut être désactivé.

 - **Différenciation**  : Ne pas confondre le compte Administrateur individuel avec le groupe de sécurité
Administrateurs.

## **Fonctions du Compte Administrateur**

 - **Tâches d'Administration** : Gestion complète des fichiers/dossiers et des comptes utilisateurs.

 - **Droits d'Accès Étendus** : Accès total à l'ensemble du système.

 - **Session Interactive** : Possibilité d'ouvrir une session interactive.

## **Remarque sur la Sécurité**

 - **Compte Désactivé par Défaut** : Windows 11 désactive le compte Administrateur par défaut.

 - **Création d'un Compte Administrateur** : Possibilité de spécifier un nom d'utilisateur administrateur
lors de l'installation.

 - **SID (Security Identifier)** : Identifiant de sécurité constant, cible privilégiée pour les pirates
informatiques.

---

# **Groupes Spéciaux dans Windows 11**

# **Caractéristiques des Groupes Spéciaux**

 - **Création Automatique** : Formés lors de l'installation de Windows 11.
 - **Usage** : Utilisés pour attribuer des accès aux ressources partagées sur un réseau.
 - **Restriction** : Ne peuvent pas être utilisés comme propriétaires de ressources.
Principaux Groupes Spéciaux.

## 1. **Anonymous Logon**

 - **Définition** : Compte par défaut pour les utilisateurs sans droits spécifiques.
 - **Usage** : Généralement pour les accès limités ou non authentifiés.

## 2. **Utilisateurs Authentifiés**

 - **Membres** : Utilisateurs ayant un compte et ayant réussi l'authentification.

 - **Accès** : Accès standard aux ressources partagées, comme les dossiers partagés en entreprise.

## 3. **Tout le Monde**

 - **Inclusion** : Tous les utilisateurs et invités authentifiés du réseau.

 - **Accès Étendu** : Accès large aux ressources.

 - **Changement Important** : Depuis Windows Server 2003, la connexion anonyme n'est plus incluse
dans ce groupe.

---

# **Compte Utilisateur**

# **Composition d'un Compte Utilisateur**

## **Informations Personnelles**

 - **Données Incluses** : Nom de connexion, prénom, nom, nom d'affichage, numéro de téléphone.

 - **Objectif** : Permettent à un utilisateur de se connecter à une machine.

## **Identifiant d'Ouverture de Session**

- **Champ Active Directory** : Stocké dans le champ sAMAccountName .

 - **Identifiant Unique** : Doit être unique dans le domaine ou le système.

 - **Longueur Maximale** : 20 caractères.

## **Remarque**

 - **Compatibilité Windows 2000** : Le nom d'ouverture de session est tronqué au vingtième caractère
pour les versions antérieures à Windows 2000.

# **Méthodes de Connexion**

## **Options de Connexion**

1. **Format Domaine** : DOMAINE\Utilisateur .

2. **Format Email** : Utilisateur@DOMAINE .

 - Ces formats fournissent des moyens flexibles pour les utilisateurs de se connecter à leurs comptes
dans différents contextes, notamment dans un environnement Active Directory.

---

# **Compte Microsoft et Cloud Microsoft**

 - Le compte Microsoft est devenu un élément clé des services basés sur le cloud, offrant divers
avantages par rapport à un compte local traditionnel.

# **Cloud Microsoft**

## **Avantages du Compte Microsoft**

 - **Plus qu'un Compte Local** : Offre des fonctionnalités supplémentaires, principalement liées au
cloud.

 - **Services Intégrés** : Accès à une variété de services Microsoft en ligne.

## **Services Microsoft en Ligne**

 - **Système d'Exploitation** : Windows, bien connu pour ses nombreuses versions.

 - **Suite Office** : Comprend Word, Excel, PowerPoint, etc.

## **Services Professionnels**

 - **Création et Gestion de Fichiers** : Utilisation d'Office Online pour créer, modifier, stocker et
partager des fichiers.

 - **Gestion d'Agenda** : Service de calendrier pour gérer des rendez-vous.

 - **Outils de Communication** :

 - Outlook.com pour la gestion d'e-mails.

 - Teams et Messenger sur Outlook pour le chat.

 - **Plateforme de Collaboration** : OneDrive pour le stockage et le partage de fichiers en ligne.

## **Utilisation Flexible**

 - **Environnements Variés** : Adapté pour une utilisation à la maison comme au travail.

 - **Interface Familière** : Similaire à la suite bureautique classique de Microsoft.

 - Le compte Microsoft s'inscrit ainsi dans une logique de services intégrés et évolutifs, s'appuyant sur les
technologies cloud pour offrir une expérience utilisateur enrichie tant dans le domaine personnel que
professionnel.

---

## **Création d'un Compte Microsoft**

 - La création d'un compte Microsoft est une étape clé pour accéder à une gamme étendue de services
Microsoft, depuis Windows 8 jusqu'à Windows 11.

# **Processus de Création de Compte**

## **Création lors de l'Installation de Windows**

 - **Options de Compte** : Choix entre compte local, compte d'entreprise, ou compte Microsoft.

 - **Disponibilité** : Option proposée lors de l'installation de Windows.

## **Création en Dehors de l'Installation**

1. **Site Web Microsoft** :

 - Aller sur account.microsoft.com.

 - Cliquer sur "Créer un compte".

2. **Saisie des Informations** :

 - Entrer une adresse e-mail.

 - Renseigner un mot de passe, pays, et date de naissance.

3. **Vérification par E-mail** :

 - Un code est envoyé à l'adresse e-mail indiquée.

 - Saisir le code reçu pour valider le compte.

## **Création d'une Nouvelle Adresse E-mail**

 - **Options de Domaine** : @outlook.com ou @hotmail.com.

 - **Procédure** : Suivre les mêmes étapes sur signup.live.com.

## **Informations Requises**

 - **Choix de l'Adresse** : Outlook.fr, outlook.com, hotmail.com.

 - **Détails Personnels** : Mot de passe, prénom, nom, date de naissance, pays.

 - **Vérification Anti-Robot** : Résolution d'une énigme ou d'un captcha.

## **Remarque Importante**

 - **Services Microsoft Existants** : Si vous utilisez Outlook ou Skype, vous avez déjà un compte
Microsoft.

---

# **Synchronisation avec un Compte Microsoft**

 - L'utilisation d'un compte Microsoft offre une expérience utilisateur cohérente et pratique à travers tous
les appareils Windows.

# **Avantages de la Synchronisation**

## **Un Compte Unique pour Tous les Appareils**

 - **Simplicité** : Un seul identifiant et mot de passe pour tous les appareils Windows.

 - **Cohérence** : Expérience utilisateur homogène sur différents appareils.

## **Gain de Temps lors de Réinstallation ou Nouvel Achat**

## - **Personnalisation Sauvegardée** :

 - Paramètres personnalisés comme le menu Démarrer et les arrière-plans du bureau.

 - Options de mise en réseau et autres paramètres systèmes.

## **Portabilité de la Personnalisation**

 - **Transfert de Personnalisation** : La personnalisation se déplace avec l'utilisateur d'un appareil à
l'autre.

 - **Utilisation sur Divers Appareils** : Valable non seulement sur PC, mais aussi sur des tablettes
comme la Surface.

## **Synchronisation Étendue**

 - **Paramètres de Navigateur** : Synchronisation des paramètres d'Edge.

 - **Mots de Passe et Paramètres Clés** : Inclut certains mots de passe et paramètres de connectivité
(comme les réseaux Wi-Fi).

 - La synchronisation avec un compte Microsoft assure donc une expérience utilisateur fluide et
personnalisée, facilitant la gestion des paramètres et préférences sur plusieurs appareils.

---