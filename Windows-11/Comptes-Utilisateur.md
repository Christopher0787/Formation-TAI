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