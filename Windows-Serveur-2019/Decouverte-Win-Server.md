# **2-Decouverte-Windows-Server**

## **Découverte de Windows Server**

![Windows Serveur VirtualBox](./img/Windows-serveur-vm10.png)

# **Tableau de bord du Gestionnaire de Serveur**

Le Tableau de Bord du Gestionnaire de Serveur est le point central de l'administration sous Windows
Server 2019. Il offre une vue d'ensemble des rôles, fonctionnalités et performances du serveur. En tant
que première interface après la connexion, il présente les informations cruciales telles que le statut
global du serveur, la configuration matérielle et les alertes éventuelles. Ce tableau de bord constitue
l'élément essentiel pour gérer efficacement votre serveur.

## **Serveur Local**

Dans la partie "Démarrage rapide", on dispose du menu "Configurer ce Serveur Local". Un serveur local
dans Windows Server 2019 fait référence à la machine sur laquelle le système d'exploitation Windows
Server est installé et exécuté. C'est le serveur physique ou virtuel qui héberge divers rôles,
fonctionnalités et services pour répondre aux besoins d'un réseau ou d'une organisation. Le serveur
local joue un rôle central dans l'administration du réseau, offrant des services tels que le stockage de

fichiers, l'authentification des utilisateurs, le partage de ressources, la gestion des politiques de sécurité,
et bien plus encore. Il constitue le point focal où les administrateurs peuvent configurer, surveiller et
maintenir les opérations du serveur. En résumé, le serveur local dans Windows Server 2019 est le
nœud principal du réseau, fournissant les services et les ressources nécessaires pour assurer le bon
fonctionnement de l'infrastructure informatique de l'organisation.

# **Fonctionnalités du Menu de Démarrage Rapide**

 - Ajouter des Rôles et des Fonctionnalités : Le menu "Ajouter des Rôles et des Fonctionnalités"
dans Windows Server 2019 simplifie la personnalisation du serveur. Il offre une interface guidée
pour installer des rôles (services) et des fonctionnalités spécifiques. Cela permet d'adapter le
serveur aux besoins, d'optimiser les ressources en n'installant que ce qui est nécessaire, et de
gérer efficacement les fonctionnalités depuis le tableau de bord du Gestionnaire de Serveur. Ce
menu centralise les options de configuration, facilitant la gestion des services et contribuant à
l'efficacité opérationnelle du serveur.

 - Ajouter d'autres Serveurs à Gérer : Le menu "Ajouter d'autres Serveurs à Gérer" dans Windows
Server 2019 offre une fonctionnalité de gestion centralisée. En utilisant cet outil, les administrateurs
peuvent intégrer d'autres serveurs dans l'environnement, facilitant ainsi la surveillance et
l'administration à partir d'un emplacement central. Cela permet une gestion efficace des serveurs
dans un réseau, offrant une vue consolidée et simplifiée pour les tâches administratives. L'ajout de
serveurs supplémentaires peut se faire de manière transparente, améliorant la scalabilité et
l'efficacité opérationnelle du réseau.

 - Créer un Groupe de Serveur : L'option "Créer un Groupe de Serveur" dans Windows Server 2019
propose une fonctionnalité permettant d'organiser et de gérer plusieurs serveurs de manière plus
structurée. En créant des groupes, les administrateurs peuvent catégoriser les serveurs en fonction
de critères spécifiques tels que les rôles, les départements ou d'autres paramètres pertinents. Cela
simplifie la gestion en permettant des actions simultanées sur plusieurs serveurs, renforçant ainsi
l'efficacité opérationnelle. Les groupes de serveurs offrent également une manière plus intuitive de
naviguer dans l'environnement du Gestionnaire de Serveur, facilitant ainsi la maintenance et la
surveillance.

 - Connecter ce Serveur aux Services Cloud : L'option "Connecter ce Serveur aux Services Cloud"
dans Windows Server 2019 offre la possibilité d'intégrer le serveur local avec des services cloud,
tels que ceux proposés par Microsoft Azure. Cette connexion cloud permet d'étendre les
fonctionnalités du serveur en exploitant des services distants, offrant ainsi des avantages tels que le
stockage en nuage, la sauvegarde en ligne, ou d'autres fonctionnalités basées sur le cloud. Cette
intégration favorise la flexibilité et l'évolutivité du serveur, renforçant ainsi sa capacité à répondre
aux besoins changeants de l'entreprise tout en profitant des avantages offerts par les services
cloud.

---

# **Windows Admin Center**

![Windows Serveur VirtualBox](./img/Windows-serveur-vm11.png)

![Windows Serveur VirtualBox](./img/Windows-serveur-vm12.png)

**Windows Admin Center** est une interface de gestion basée sur le web pour les serveurs Windows,
conçue pour simplifier et centraliser l'administration des serveurs. Elle offre une alternative aux outils
d'administration traditionnels basés sur des interfaces utilisateur graphiques (GUI) locales.

# **Caractéristiques et Fonctionnalités Clés**

 - **Interface Web :** Windows Admin Center est accessible via un navigateur web, permettant aux
administrateurs de gérer leurs serveurs à partir de n'importe quel appareil disposant d'une
connexion réseau.

 - **Gestion Centralisée :** Il offre une interface centralisée pour la gestion des serveurs, permettant aux
administrateurs de configurer, surveiller et dépanner plusieurs serveurs à partir d'un emplacement
unique.

 - **Prise en Charge des Versions Récentes de Windows Server :** Windows Admin Center prend en
charge les versions récentes de Windows Server, y compris Windows Server 2012, 2012 R2, 2016,
2019 et les versions ultérieures.

 - **Gestion des Rôles et Fonctionnalités :** Il permet la gestion des rôles, des fonctionnalités et des
services installés sur les serveurs, simplifiant ainsi les opérations d'administration.

 - **Surveillance des Performances :** Windows Admin Center offre des outils de surveillance des
performances pour suivre l'utilisation des ressources telles que le processeur, la mémoire et le
stockage.

 - **Gestion des Machines Virtuelles :** Il offre des fonctionnalités de gestion des machines virtuelles
via Hyper-V, permettant de créer, modifier et surveiller des machines virtuelles.

 - **Gestion du Stockage :** Windows Admin Center permet la gestion du stockage, y compris la
configuration des pools de stockage et des espaces de stockage direct.

 - **Outils de Sécurité :** Il propose des outils de sécurité pour la gestion des mises à jour, la
configuration du pare-feu, et d'autres paramètres de sécurité.

En résumé, Windows Admin Center simplifie l'administration des serveurs Windows en fournissant une
interface web centralisée, accessible à distance, pour la gestion de divers aspects tels que les rôles, les
fonctionnalités, la surveillance des performances, et d'autres paramètres.

- **On exécute le fichier téléchargé en acceptant les choix par défaut**

![Windows Serveur VirtualBox](./img/Windows-serveur-vm13.png)

 - L'interface sera accessible via https:// nomDuServeur

- Inthernet Explorer n'est pas adéquat pour exécuter cette interface en ligne, on télégargera donc Google Chrome.

![Windows Serveur VirtualBox](./img/Windows-serveur-vm14.png)

---

# **Rôles et Groupes de Serveurs**

## **Services de Fichiers et de Stockage**

L'option "Services de Fichiers et de Stockage" dans Windows Server 2019 propose des fonctionnalités
dédiées à la gestion et à la distribution des données au sein du réseau. Elle permet de configurer des
services tels que le partage de fichiers, les quotas de stockage, ou encore le déploiement de systèmes
de fichiers distribués. Cette fonctionnalité est cruciale pour assurer une gestion efficace des données au
sein de l'entreprise, en fournissant des outils pour centraliser, organiser et sécuriser les fichiers. En
facilitant la gestion des données, cette option contribue à optimiser les performances du réseau et à
garantir un accès sécurisé aux informations essentielles pour les utilisateurs du serveur.

## **Serveur Local dans "Rôles et Groupes de Serveurs"**

Lorsque vous cliquez sur "Serveur Local" dans cette section, vous avez accès à des détails spécifiques
à la machine locale, en mettant en avant les rôles et fonctionnalités actuellement installés. Cela inclut
des informations détaillées sur chaque rôle ou fonctionnalité, leur état, ainsi que la possibilité d'ajouter
ou de retirer des rôles et fonctionnalités.
En résumé, l'option "Serveur Local" dans la section "Rôles et Groupes de Serveurs" offre une vue
détaillée des composants actuels du serveur sur lequel vous travaillez dans le contexte des rôles et
fonctionnalités. Cela permet aux administrateurs de gérer efficacement les rôles spécifiques du serveur
sans avoir à naviguer à travers divers menus.

## **Tous les Serveurs dans "Rôles et Groupes de Serveurs"**

L'option "Tous les Serveurs" dans la section "Rôles et Groupes de Serveurs" du Gestionnaire de
Serveur dans Windows Server 2019 offre une vue consolidée de tous les serveurs dans votre
environnement réseau.
En cliquant sur "Tous les Serveurs", vous accédez à une vue centralisée qui répertorie tous les serveurs
gérés. Cela permet aux administrateurs de surveiller l'état et les rôles des différents serveurs depuis
une seule interface. Vous pouvez obtenir des informations essentielles sur chaque serveur, y compris
les rôles installés, l'état actuel, et effectuer des actions de gestion, telles que l'ajout ou la suppression
de rôles et de fonctionnalités sur plusieurs serveurs simultanément.
En résumé, l'option "Tous les Serveurs" simplifie la gestion centralisée des serveurs dans un
environnement réseau, offrant une visibilité unifiée pour faciliter la maintenance et la configuration des
serveurs dans votre infrastructure.

## **Note :** Si vous avez fermé la fenêtre du gestionnaire de serveur, vous pouvez facilement le retrouver en
suivant ces étapes :

 - Allez dans le menu Windows, puis dans le gestionnaire de serveur (en passant par les outils
d'administration Windows si celui-ci n'apparaît pas directement).

---

![Windows Serveur VirtualBox](./img/Windows-serveur-vm15.png)

# **Préparez votre système à la mise en réseau**

Bienvenue dans ce chapitre crucial de la préparation de votre Windows Server pour le réseau.
L'importance de cette étape réside dans le fait que la plupart des erreurs se produisent ici. Il est
essentiel de comprendre chaque détail, car Microsoft a automatisé de nombreux aspects.

La négligence de la préparation peut créer des vulnérabilités significatives, mettant en danger la
sécurité du réseau. Pire encore, elle pourrait offrir un accès non autorisé au serveur, exposant ainsi les
données sensibles qu'il héberge.

Dans ce chapitre, nous plongerons dans les étapes critiques pour préparer efficacement votre Windows
Server, établissant ainsi une base robuste pour le réseau. Notre objectif est de vous armer contre les
erreurs fréquentes et de renforcer la sécurité de votre système. Restez attentifs, chaque étape compte
dans cette première ligne de défense contre les menaces.

## **Préparez votre machine virtuelle : Configuration réseau et Mises à jour**

Dans cette phase initiale, équivalente à brancher un câble réseau sur un serveur physique, votre
machine virtuelle, par défaut sous VirtualBox, bénéficie d'une protection extérieure grâce au réseau
NAT géré par la plateforme.

En résumé, votre serveur n'est pas directement accessible depuis Internet, mais il a la capacité d'y
accéder !

Vérifiez la configuration réseau. Si VirtualBox est correctement configuré, vous devriez disposer d'une
adresse IP, d'un masque, d'une passerelle, et d'un serveur DNS par défaut.

Maintenant que vous avez ces informations, par où commencer ? Quelle est la première action à
entreprendre ?

De manière similaire à une distribution Linux où vous exécuteriez des commandes telles que sudo apt
update suivi de sudo apt upgrade , vous allez vérifier les correctifs disponibles pour vos éditions,
versions, et options d'installation de Windows auprès des serveurs de Microsoft !

Rendez-vous dans la section "Serveur local" du Gestionnaire de serveur pour effectuer ces
vérifications. Procédez ensuite aux mises à jour nécessaires pour garantir la robustesse de votre
environnement. Une machine bien entretenue constitue la première ligne de défense contre les
vulnérabilités potentielles.

---

![Windows Serveur VirtualBox](./img/Windows-serveur-vm16.png)

![Windows Serveur VirtualBox](./img/Windows-serveur-vm17.png)

# **Configuration réseau et Mises à jour : Informations Essentielles**

Toutes les informations cruciales pour la mise en réseau se trouvent ici :

 - **Nom du Serveur :** WIN-1HOJWCE0IT

 - **Groupe de Travail :** WORKGROUP

 - **Mises à Jour :** Les dernières mises à jour installées

 - **Mode de Mise à Jour :** "Télécharger les mises à jour uniquement à l’aide de..."

 - **Date de la Dernière Recherche :** [Date]

Il vous suffit alors de cliquer sur "Télécharger les mises à jour uniquement à l’aide de..." pour accéder à
l'interface facilitant le processus de mises à jour. Cela vous assure de maintenir votre système à jour,
une étape cruciale pour garantir la stabilité et la sécurité de votre serveur.

Une fois logué, le gestionnaire de serveur apparaît et, par souci pratique, on désactive la sécurité
renforcée d'IE (On -> Off), afin d'éviter de devoir autoriser chaque accès à un nouveau composant.

---
