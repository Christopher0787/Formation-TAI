# **Windows 11**

- Lancé par **Microsoft** le 4 octobre 2021 aux États-Unis et le 5 octobre dans le reste du monde, Windows
11 a marqué une évolution surprenante dans la série des systèmes d'exploitation Windows.
Contrairement aux déclarations antérieures de Microsoft, Windows 11 a été présenté comme une
nouvelle génération de Windows, succédant à Windows 10, qui était censé être le dernier.

## **Nouveauté et Améliorations**

1. **Design et interface Utilisateur**

---

# Windows 11 : Amélioration de l'Expérience Utilisateur

## 1. Design et Interface Utilisateur
- Nouveau design avec des sons modernes.
- Menu Démarrer centré, bords arrondis, et nouveau logo.
- Agencement revu de l'application des paramètres pour une meilleure ergonomie.

## 2. Centre de Notifications
- Nouveau centre de notifications pour une gestion améliorée des alertes et messages.

## 3. Intégration Microsoft 365
- Renforcement de l'intégration avec Microsoft 365.
- Utilisation d'Azure Virtual Desktop pour une expérience de bureau à distance sécurisée.

## 4. Gestion des Bureaux Multiples
- Simplification de la gestion des espaces de travail.
- Meilleure organisation des tâches et optimisation de l'espace d'écran.

## 5. Widgets et Intelligence Artificielle
- Widgets personnalisés grâce à l'intelligence artificielle.
- Fourniture d'informations plus pertinentes et adaptées.

## 6. Gaming
- Amélioration de l'expérience de jeu avec DirectX12 Ultimate, DirectStorage et Auto HDR.
- Accès à une vaste bibliothèque de jeux via l'application Xbox Game Pass.

## 7. Windows Store
- Windows Store remanié avec un nouveau design.
- Recherche et découverte facilitées d'applications et de contenus multimédias.
- Plateforme ouverte pour les développeurs.

## Conclusion
Globalement, Windows 11 se positionne comme une mise à jour majeure, visant à améliorer l'expérience utilisateur sur plusieurs fronts, depuis la productivité jusqu'aux loisirs, en passant par la sécurité et l'efficacité.

---

# **Windows 11 - Licences**

Windows 11 est disponible en plusieurs éditions, chacune conçue pour répondre à des besoins spécifiques.

# Éditions de Windows 11

## 1. Windows 11 Familial (Home) 
   - Destiné aux utilisateurs grand public.
   - Fonctionnalités adaptées à l'usage quotidien.

## 2. Windows 11 Professionnel pour l'éducation
   - Conçu spécifiquement pour le secteur de l'éducation.

## 3. Windows 11 Professionnel (Pro)
   - Fonctionnalités avancées comme Bitlocker, stratégies de groupe, domaine, bureau à distance.
   - Licence unique pour chaque installation.

## 4. Windows 11 Entreprise
   - Mêmes fonctionnalités que l'édition Professionnelle.
   - Utilise une Volume Licence Key (VLK) pour les grandes entreprises.

## 5. Windows 11 SE (Éducation)
   - Optimisé pour le secteur éducatif.
   - Fonctionne bien sur des ordinateurs économiques.
   - Système sans distractions, axé sur la gestion à distance et le cloud.

## 6. Windows 11 Pro pour les stations de travail (Workstation)
   - Pour les utilisateurs avec des besoins avancés (bases de données, CAO, recherche, production média).
   - Supporte des charges de travail exigeantes.

## 7. Windows 11 Réalité Mixte
   - Base logicielle pour périphériques de réalité virtuelle et augmentée.

## 8. Windows 11 IoT (Entreprise)
   - Successeur de Windows Embedded.
   - Utilisé pour des appareils spécialisés comme des guichets automatiques, terminaux de point de vente, etc.

## Coût des Licences
- Windows 11 Familial (OEM) : 133,29 € TTC.
- Windows 11 Professionnel (OEM) : 174,97 € TTC.
- Windows 11 Station de travail : 285,22 € TTC.

Le coût des licences est similaire à celui de Windows 10, avec une structure de prix adaptée à chaque édition.

---

# Prérequis pour Windows 11

Pour installer ou mettre à jour vers Windows 11, votre ordinateur doit répondre à des exigences matérielles spécifiques.

## Configuration Matérielle Minimale:

1. **Processeur**
   - Fréquence : 1 GHz ou plus rapide.
   - Coeurs : Minimum deux coeurs.
   - Compatibilité : Doit être un processeur 64 bits.

2. **Mémoire Vive (RAM)**
   - Minimum : 4 Go.

3. **Stockage**
   - Capacité minimale : 64 Go.
   - Stockage supplémentaire requis pour les mises à jour et fonctionnalités additionnelles.

4. **Carte Graphique**
   - Compatibilité : Doit supporter DirectX12.
   - Résolution minimale : 720px.
   - Taille d'écran : Minimum 9 pouces.

5. **Réseau et Connectivité**
   - Carte réseau nécessaire.
   - Connexion Internet requise pour les mises à jour et l'activation de fonctionnalités.

## Prérequis Spécifiques pour Certaines Fonctionnalités:

- **BitLocker To Go :** Nécessite une clé USB.
- **Cortana :** Exige l'utilisation d'un microphone.
- **Direct Storage :** Requiert un disque dur SSD NVMe (Solid-State Drive Non-Volatile Memory Express).

Ces prérequis garantissent que votre système peut prendre en charge les fonctionnalités et les performances offertes par Windows 11. Veillez à vérifier que votre matériel répond à ces exigences avant de procéder à l'installation ou à la mise à jour vers Windows 11.

---

# Le TPM pour Windows 11

Le TPM (Trusted Platform Module) est un élément crucial pour l'installation et le fonctionnement de Windows 11, avec des exigences spécifiques en matière de sécurité et de démarrage.

## Exigences TPM pour Windows 11:

1. **Boot UEFI et TPM**
   - Le démarrage UEFI (Unified Extensible Firmware Interface) est requis.
   - La présence d'une puce TPM sur la carte mère est nécessaire.
   - La plupart des ordinateurs récents prennent en charge TPM 2.0, qui est le standard depuis le 28 juillet 2016.

2. **Fonctions du TPM**
   - Gère le chiffrement des données.
   - Stocke des informations sensibles telles que les données biométriques pour Windows Hello et les clés de chiffrement pour BitLocker.
   - La puce TPM vérifie l'intégrité de Windows avant le chargement du système d'exploitation.
   - Aide les logiciels antivirus à prévenir l'installation de rootkits.

3. **Avantages Sécuritaires**
   - Les données sont stockées sur le matériel, les rendant insensibles aux attaques logicielles.
   - Assure la protection des données sensibles directement sur la carte mère.
   - Contribue à la sécurité du démarrage et du fonctionnement du système.

4. **Intégration avec Windows 11**
   - Windows contrôle le TPM pendant le démarrage pour garantir qu'aucun système d'exploitation malveillant n'est chargé.

**TPM matériel vs TPM logiciel:**
- TPM matériel : Plus sécurisé car isolé et indépendant.
- TPM logiciel (micrologiciels) : Utilise le CPU pour les fonctions cryptographiques, potentiellement plus sujet à la falsification.

5. **Norme TPM 2.0**
   - Windows 11 exige la conformité à la norme TPM 2.0, indépendamment du type de TPM (matériel ou logiciel).

L'intégration du TPM avec Windows 11 renforce la sécurité du système, assurant une protection robuste des données et du démarrage du système contre les menaces potentielles.

---

# Secure Boot pour Windows 11

Le Secure Boot est une autre exigence importante pour l'installation de Windows 11, activant une fonction de sécurité présente sur la plupart des matériels modernes.

## Qu'est-ce que le Secure Boot ?

1. **Définition**
   - Fonction de sécurité utilisant le micrologiciel UEFI.
   - Crée un environnement sécurisé pour le démarrage de Windows.
   - Empêche les logiciels malveillants de détourner le système pendant le démarrage.

2. **Fonctionnement**
   - Permet à l'ordinateur de démarrer uniquement avec des logiciels fiables fournis par le fabricant de l'équipement (OEM).

## Vérification et Activation de Secure Boot

1. **Vérification de l'activation**
   - Pour vérifier si Secure Boot est activé sur votre ordinateur :
     - Sélectionnez le menu démarrer.
     - Allez dans informations système.
     - Identifiez les lignes "Mode BIOS" et "Etat du démarrage sécurisé".

L'activation du Secure Boot garantit un niveau supplémentaire de sécurité lors du démarrage de Windows 11, empêchant les logiciels malveillants de compromettre le système dès le démarrage. Assurez-vous que cette fonctionnalité est activée pour bénéficier d'une protection maximale.

# Indicateurs clés pour l'installation sécurisée de Windows 11

Pour une installation sécurisée de Windows 11, deux indicateurs clés doivent être vérifiés :

1. **Mode BIOS sur UEFI**
   - Le mode BIOS doit être configuré sur UEFI (Unified Extensible Firmware Interface) pour garantir une compatibilité avec Windows 11 et profiter des fonctionnalités de démarrage sécurisé.

2. **État du démarrage sécurisé activé**
   - L'état du démarrage sécurisé doit être activé dans les paramètres du BIOS pour empêcher les logiciels malveillants de s'introduire pendant le processus de démarrage.

## Installation de Windows 11 avec Secure Boot

1. **Activation de Secure Boot**
   - Nécessaire pour une installation sécurisée de Windows 11, cette fonction garantit l'intégrité du démarrage du système.

2. **Conversion de MBR en GPT (si Secure Boot est désactivé)**
   - Créez une sauvegarde de l'ordinateur.
   - Convertissez l'installation de MBR (Master Boot Record) en GPT (GUID Partition Table) pour être compatible avec Secure Boot.

3. **Commandes pour la conversion**
   - Utilisez les commandes suivantes dans l'invite de commandes en mode Récupération :
     - `mbr2gpt /validate`
     - `mbr2gpt /convert`

4. **Validation de la conversion**
   - Un succès de la conversion retourne le code 0. En cas d'échec, une erreur peut survenir.

5. **Activation dans le BIOS**
   - Activez Secure Boot dans les paramètres du BIOS, en suivant la procédure spécifique à la marque et au modèle de la carte mère.

**Conclusion**

L'activation de Secure Boot est essentielle pour garantir un environnement de démarrage sécurisé pour Windows 11, protégeant ainsi le système contre les menaces potentielles dès le démarrage. Veillez à configurer correctement ces paramètres lors de l'installation ou de la mise à niveau vers Windows 11 pour bénéficier d'une sécurité maximale.

---

# **Fonctionnalités**

# **Tableau Comparatif Windows 10 vs Windows 11**

| Fonctionnalité                | Windows 10                           | Windows 11                          |
|-------------------------------|--------------------------------------|-------------------------------------|
| Nouvelle interface           | Non disponible                       | Disponible                          |
| Sort de veille à l'approche  | Non disponible                       | Disponible                          |
| Smart App Control            | Non disponible                       | Disponible                          |
| Réorganisation simplifiée    | Non disponible                       | Disponible                          |
| Sous-titrages en direct      | Non disponible                       | Disponible                          |
| Narrateur naturel            | Non disponible                       | Disponible                          |
| Amazon Appstore              | Non disponible                       | Disponible                          |
| Effets Windows Studio        | Non disponible                       | Disponible                          |
| Barre de commande            | Non disponible                       | Disponible                          |
| HDR automatique              | Non disponible                       | Disponible                          |
| Widgets                      | Non disponible                       | Disponible                          |
| Sauvegarde Windows           | Disponible (Sauvegarder uniquement)  | Disponible (Sauvegarder et restaurer) |
| Paint                        | Disponible                           | Disponible (avec fonctionnalités supplémentaires) |
| Synchronisation PC et téléphone | Disponible (Android uniquement)  | Disponible (Android et iPhone)     |
| Écran tactile                | Disponible                           | Disponible                          |
| Rechercher                   | Disponible                           | Disponible                          |
| TPM                          | Disponible                           | Disponible                          |
| Microsoft Edge               | Disponible                           | Disponible                          |
| Sauvegarde OneDrive          | Disponible                           | Disponible                          |
| Application Sécurité Windows | Disponible                           | Disponible                          |
| Alignement automatique       | Disponible                           | Disponible                          |
| Groupes de bureaux           | Disponible                           | Disponible                          |
| Thèmes de contrastes         | Disponible                           | Disponible                          |
| Commande vocale              | Disponible                           | Disponible                          |
| Microsoft Store repensé      | Disponible                           | Disponible                          |
| Outil Capture                | Disponible                           | Disponible                          |
| Application Journal          | Disponible                           | Disponible                          |
| Clipchamp                    | Disponible                           | Disponible                          |
| Stylet numérique             | Disponible                           | Disponible                          |
| Emojis                       | Disponible                           | Disponible                          |
| DirectStorage                | Disponible                           | Disponible                          |
| DirectX 12 Ultimate          | Disponible                           | Disponible                          |
| Son 3D spatial               | Disponible                           | Disponible                          |
| PC Game Pass                 | Disponible                           | Disponible                          |
| Xbox Game Bar                | Disponible                           | Disponible                          |
| Prise en main                | Disponible                           | Disponible                          |
| Compte Microsoft             | Disponible                           | Disponible                          |
| Transfert de fichier OneDrive| Disponible                           | Disponible                          |
| Windows sur ARM              | Disponible                           | Disponible                          |

# **Tableau Comparatif Window 11 Familial vs Windows 11 Professional**

| Fonctionnalité                  | Windows 11 Professionnel       | Windows 11 Famille          |
|--------------------------------|---------------------------------|-----------------------------|
| Chiffrement de lecteur BitLocker | Disponible                    | Non disponible              |
| Chiffrement du périphérique    | Disponible                    | Disponible                  |
| Localiser mon appareil         | Disponible                    | Disponible                  |
| Pare-feu et protection du réseau | Disponible                  | Disponible                  |
| Protection Internet            | Disponible                    | Disponible                  |
| Contrôle parental et protection | Disponible                   | Disponible                  |
| Démarrage sécurisé             | Disponible                    | Disponible                  |
| Windows Hello                  | Disponible                    | Disponible                  |
| Sécurité Windows               | Disponible                    | Disponible                  |

---

# **Amélioration dans Windows 11**

- Windows 11 se distingue de son prédécesseur, Windows 10, par des changements significatifs dans son design et son fonctionnement.

## **Principales Améliorations de Performances :**

1. **Gestion de la Mémoire :** Windows 11 optimise la gestion de la mémoire en favorisant les applications en premier plan, ce qui permet d'allouer plus de ressources pour améliorer leur performance. Par exemple, même sous une charge processeur élevée, des applications telles que Microsoft Excel s'ouvrent rapidement, démontrant ainsi l'efficacité de cette gestion de la mémoire.

2. **Menu Démarrer et Effets Visuels :** Windows 11 optimise également le processus de gestion du menu Démarrer et d'autres effets visuels, ce qui améliore l'expérience utilisateur globale.

3. **Sortie de Veille :** Une amélioration notable de la sortie de veille est observée dans Windows 11. Contrairement à Windows 10, où la RAM était complètement mise hors tension en mode veille, dans Windows 11, la RAM reste sous tension, ce qui permet un réveil plus rapide du PC.

4. **Navigateur Edge :** Le navigateur Edge dans Windows 11 offre des performances accrues grâce à une meilleure gestion des onglets en veille. Cette optimisation permet d'économiser jusqu'à 32% de mémoire et 37% d'utilisation du processeur, ce qui se traduit par une expérience de navigation plus fluide et réactive.

- En résumé, Windows 11 apporte des améliorations significatives dans la gestion de la mémoire, le fonctionnement du menu Démarrer, la sortie de veille et les performances du navigateur Edge, offrant ainsi une expérience utilisateur améliorée et plus fluide par rapport à Windows 10.

---

# **Installation de Windows 11**

Avant d'installer Windows 11, il est essentiel de vérifier la compatibilité de votre ordinateur avec le système d'exploitation. Plusieurs étapes et options sont disponibles pour mener à bien cette installation.

**1. Vérification de la Compatibilité :**
   - **Mise à Niveau depuis Windows 10 :** 
     - Notification via Windows Update : L'ordinateur informe si la mise à niveau est prête.
     - Consultation du Bilan de Santé du PC : Disponible dans Windows Update.
     - Utilisation de l'Outil PC Health Check : Téléchargement depuis le site de Microsoft, cet outil indique si l'ordinateur répond aux exigences de Windows 11.

**2. Options de Support d'Installation :**
   - **Assistant d'Installation :** 
     - Utilisation : Installation de Windows 11 sur l'appareil en cours d'utilisation.
     - Disponibilité : Sur le site de Microsoft.
     - Droits d'Administrateur : Nécessaires pour exécuter l'outil.
   - **Image ISO :**
     - Utilité : Création d'une machine virtuelle, DVD-ROM ou clé USB bootable.
     - Téléchargement : Disponible sur le `Microsoft Volume Licensing Service Center (VLSC)` ou le site de Microsoft.
   - **Support d'Installation :**
     - Idéal Pour : Installation propre de Windows 11.
     - Outils Requis : DVD-ROM ou clé USB (8 Go minimum) et Media Creation Tool.
     - Formatage : Clé USB formatée et données effacées.

**3. Nouvelle Installation :**
   - **Démarrage sur le Support d'Installation :**
     - Accès BIOS/UEFI : Pour modifier l'ordre de priorité de démarrage.
     - Touche de Démarrage : Utilisation générale de [F11] ou [F12].
   - **Sélection des Paramètres d'Installation :**
     - Options : Langue, format de l'heure, devise, clavier ou méthode de saisie.
     - Modification : Cliquer sur la flèche à droite de l'option pour changer les paramètres.

En suivant ces étapes et options, vous pourrez installer Windows 11 sur votre ordinateur en toute efficacité et sécurité.

---