# **Sécuriser un systeme linux**
---


La sécurité d'un système Linux est d'une importance cruciale pour garantir la confidentialité, l'intégrité et la disponibilité des données. Ce chapitre explore les différentes techniques et bonnes pratiques pour renforcer la sécurité d'un système Linux.

---


# **Gestion des utilisateurs et des droits d'accès**
---


La création d'utilisateurs sécurisés et la gestion appropriée des droits d'accès sont des mesures essentielles pour contrer les risques liés aux intrusions. En attribuant
des mots de passe robustes, on réduit grandement les chances d'intrusions par bruteforce. De plus, en définissant correctement les permissions avec chmod/chown
et en utilisant des groupes de manière judicieuse, on limite l'accès aux fichiers et répertoires sensibles, renforçant ainsi la confidentialité des données.

---


## **Ne jamais se connecter en tant qu’utilisateur root**
---


Le profil root est désactivé sur les distributions Ubuntu. Néanmoins, il est possible sur d’autres distributions (notamment Debian et Fedora) de se connecter
facilement en tant qu’utilisateur root afin de pouvoir tout faire sans avoir à se soucier de sudo.
Pour autant, utiliser ce profil est déconseillé. En tant qu’utilisateur root, vous avez un accès hyperprivilégié et, si quelqu’un s’introduit dans votre système, cette
personne aura elle aussi un accès illimité à tous les services, à toutes les applications et à toutes les données que vous avez stockées.
Il est donc conseillé de ne JAMAIS vous connecter en tant qu’utilisateur root. Utilisez toujours sudo pour les tâches admin afin de ne pas exposer votre système à des
attaques potentiellement graves.

---

## **Points clés**
---


    * Limiter l'accès a l'utilisateur root.

    * Utilisation de mots de passesrobuste ( avec lettres majuscule, minuscule, chiffres et caractères speciaux ).

    * Limiter les permissions des utilisateurs et groupes en leur attribuant uniquement les permissionsnécessaire.

    * Ne jamais définir les droits total à un fichier ou répertoire dans un environnement de production (chmod 777).
---


# **Configuration du pare-feu**
---


La configuration d'un pare-feu comme UFW, vise à contrôler le trafic réseau et à protéger le système contre les attaques externes. En limitant les ports et les services
exposés, on réduit la surface d'attaque potentielle. L'utilisation de Fail2Ban complète cette stratégie en surveillant les journaux d'authentification, détectant les
tentatives d'intrusion, et bloquant temporairement les adresses IP suspectes, contribuant ainsi à la prévention des attaques par force brute.

---


## **Installation et configuration de UFW**
---


## **Installation**
---


**Sur Ubuntu/Debian :**

    "sudo apt-get install ufw"
---


**Sur CentOS/RHEL :**

    "sudo yum install ufw"
---


**Activer UFW**

    "sudo ufw enable"
---


**Autoriser un port ou service**

    "sudo ufw allow portOuService"
---


exemple :

    "sudo ufw allow 22"
---


ou alors :

    "sudo ufw allow ssh"
---


**Vérifier les règles**

    "sudo ufw status"
---


**Supprimer une règle**

    "sudo ufw delete numeroDeLaRègle"
---


**pour connaître les numéros des règles, il suffit d'utiliser la commande suivante :**

    "sudo ufw status numbered"
---


**Désactiver UFW ( si nécessaire )**

    "sudo ufw disable"
---


**Réinitialiser UFW**

    "sudo ufw reset"
---


## **Installation et configuration de Fail2Ban**
---


**Sur Ubuntu/Debian :**

    "sudo apt-get install fail2ban"
---


**Sur CentOS/RHEL :**

    "sudo yum install fail2ban"
---


## **Configuration de base**
---


**Copier le fichier de configuration par défaut**

    "sudo cp /etc/fail2ban/jail.conf /etc/fail2ban/jail.local"
---


**Éditer le fichier de configuration**

    "sudo nano /etc/fail2ban/jail.local"
---


Il existe une multitude de possibilités de configuration pour Fail2Ban, tout dépend du besoin. Je vous laisse vous référer au wiki disponible ICI.

---


# **Mise à jour et gestion des correctifs**
---


Quel que soit le système d’exploitation, faire régulièrement les mises à jour fait partie des premiers conseils à suivre.

En effet, les mises à jour n’apportent pas seulement de nouvelles fonctionnalités ou des nouveautés visuelles. Elles contiennent surtout des correctifs de sécurité
permettant de corriger les vulnérabilités qui ont été découvertes. Il faut vérifier les mises à jour quotidiennement, et les installer dès qu’elles sont disponibles. Elles
sont parfois mineures, mais d’autres fois, elles corrigent des failles de sécurité CVE (Common Vulnerabilities and Exposures) critiques.

CVE est un dictionnaire des informations publiques relatives aux vulnérabilités de sécurité. Le dictionnaire est maintenu par l'organisme MITRE, soutenu par le
département de la Sécurité intérieure des États-Unis.

Il est important de se tenir informé des vulnérabilités connus, voici quelques liens utiles :

"cve.mitre.org - cvedetails.com"

---


# **Surveillance du système**
---


La surveillance du système est un aspect crucial de la sécurité informatique, permettant de détecter rapidement les comportements anormaux, les activités
suspectes et les éventuelles tentatives d'intrusion. Voici quelques pratiques et outils pour renforcer la surveillance de votre système Linux.

---


## **Historique des connexions**
---


    "last*

la commande last permet d'avoir un historique des connexion au système sur un delai de 1 mois.

---


**Lynis**


Lynis est un outil d'audit de sécurité pour les systèmes basés sur UNIX comme Linux, macOS, BSD et autre. Il effectue une analyse se sécurité approfondie et
s'exécute sur le système lui-même.

L'objectif principal est de tester les défenses de sécurité et de fournir des conseils pour renforcer davantage le système. Il cherchera également des informations
générales sur le système, des progiciels vulnérables et d'éventuels problèmes de configuration.

Voici comment l'installer :


    "git clone https://github.com/CISOfy/lynis"

    "cd lynis"

    "./lynis"
---


Éffectivement, Lynis est récupérable depuis github, d'où la commande git clone . La page GitHub de cet outil est disponible ICI.

Pour réaliser un audit du système, il suffit de rentrer la commande suivante à l'intérieur du dossier lynis :

    "sudo ./lynis audit system"
---


## **Rkhunter**
---


rkhunter, ou Rootkit Hunter, est un outil de sécurité open source conçu pour détecter la présence de rootkits, de backdoors, et de divers exploits locaux potentiels sur
un système Linux ou Unix. Son objectif principal est d'identifier des signes de compromission du système, en particulier les activités malveillantes qui pourraient
échapper à la détection normale.

Définitions importante :


    ## * 1. Rootkits :

        * Définition : Un rootkit est un ensemble de logiciels ou de techniques qui permettent à un attaquant d'obtenir un accès et un contrôle non autorisés sur un système, souvent en dissimulant sa présence et ses activités.


        * Objectif : Les rootkits sont généralement utilisés pour maintenir un accès persistant au système. Ils peuvent manipuler le système d'exploitation pour masquer les processus, les fichiers, les connexions réseau, et même les utilisateurs.


        * Fonctionnement : Un rootkit peut modifier le noyau du système d'exploitation ou s'installer en tant que module du noyau pour cacher sa présence. Certains rootkits peuvent également altérer les commandes système pour fournir des informations trompeuses lorsqu'elles sont consultées.
---

    ## * 2. Backdoors :

        * Définition : Une backdoor (porte dérobée) est une méthode qui consiste contourner les mécanismes de sécurité normaux d'un système.


        * Objectif : Les backdoors sont souvent utilisées pour garantir un accès futur à un système compromis. Elles peuvent être utilisées pour exécuter des commandes à distance, collecter des informations, ou installer d'autres types de logiciels malveillants.


        * Fonctionnement : Les backdoors peuvent être installées à travers des failles de sécurité, des vulnérabilités logicielles, ou même par le biais de logiciels malveillants déjà présents sur le système. Elles permettent à un attaquant d'éviter les mécanismes de sécurité usuels pour entrer et sortir du système sans être détecté.
---


Voci comment l'installer :

    "sudo apt-get install rkhunter"
---


pour scranner tout le système :

    "rkhunter --check"
---


ou

    "rkhunter -c"
---


# **Configuration sécurisée de SSH**


Dans cette section, nous explorerons des pratiques de sécurisation supplémentaires pour renforcer la configuration de votre serveur SSH. En accédant au fichier de
configuration SSH à l'aide de la commande suivante :


    "sudo nano /etc/ssh/sshd_config"
---


## **1. Changement du Port SSH :**

Le changement du port par défaut (22) auquel le service SSH écoute peut être une mesure de sécurité efficace. Modifier ce port contribue à empécher les bots
(robots) qui ciblent souvent le port par défaut. Choisissez un port non standard, mais assurez-vous qu'il n'est pas déjà utilisé par d'autres services sur votre système.


    "# Port 22 (remplacez-le par un port non standard)"
    "Port 2222"

La liste des ports logiciels est disponible ICI.

---


## **2. Désactivation de la Connexion en tant que Root :**

Il est important de désactiver la connexion directe en tant que root car les attaquants tentent souvent de se connecter sur ce dernier. De plus, le compte root doit être
uniquement accessible en local et utiliser en cas de besoins.


    "# PermitRootLogin no"
    "PermitRootLogin no"

---


## **3. Désactivation de la Connexion par Mot de Passe :**

Privilégiez l'authentification par clé SSH plutôt que par mot de passe. Cela élimine les vulnérabilités potentielles liées aux attaques par bruteforce sur les mots de
passe.


    "# PasswordAuthentication no"
    "PasswordAuthentication no"

Pour que les nouveaux paramètres soient pris en compte, il suffit de redémarrer le serveur SSH :

    "sudo systemctl restart ssh"
---