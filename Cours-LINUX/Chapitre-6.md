# **Tâches Planifiées sous Linux**
---


# **Introduction**
---


* Les tâches planifiées, également connues sous le nom de cron jobs, sont un moyen puissant d'automatiser l'exécution de scripts, de commandes ou de programmes à des intervalles spécifiés. Sous Linux, le service responsable de la planification des tâches est appelé Cron. Ce chapitre explore les concepts fondamentaux des tâches planifiées et comment les utiliser efficacement.
---


# **Syntaxe**
---


* Les tâches planifiées sont définies en utilisant la syntaxe suivante dans le fichier crontab :


    * Minute (0 - 59)
    * | Heure (0 - 23)
    * | | Jour du mois (1 - 31)
    * | | | Mois (1 - 12)
    * | | | | Jour de la semaine (0 - 6, où 0 = dimanche)
    * | | | | |
    * * * * * commande à exécuter
---


# **Accéder au Crontab**
---


- Lors de la création d'une tâche, la configuration est généralement stockée dans un fichier contenu dans le dossier temporaire du systeme /tmp/ pendant l'édition, puis ce fichier est déplacé vers l'emplacement correct si tout se passe bien.


- Il se trouve que le dossier /tmp/ appartient généralement à l'utilisateur root , il faut donc nous ajoutés des droits sur ce dossier :


    "sudo chmod 1777 /tmp"


- Comme vous pouvez le constater, ce chmod est assez particulier, il contient 4 chiffres !


- En effet, il y a un 1 devant les permissions 777. Il s'agit dubit "sticky" (ou bit de contrôle d'accès spécial) ! Lorsque ce dernier est activé, il permet de restreindre la capacité des utilisateurs à supprimer ou renommer des fichiers ou dossiers dans un répertoire. Voici une clarification plus détaillée :
---


## **Bit "sticky" activé sur un répertoire (par exemple, "1777"):**


    * Les utilisateurs ont le droit d'écrire dans le répertoire (ajouter, créer des fichiers).

    * Les utilisateurs peuvent supprimer ou renommeruniquement les fichiers qu'ils possèdent dans ce répertoire.

    * Cela aide à prévenir la suppression accidentelle ou malveillante de fichiers d'autres utilisateurs dans le même répertoire.
---


## **Bit "sticky" désactivé sur un répertoire (par exemple, "777"):**


    * Les utilisateurs ont le droit d'écrire dans le répertoire (ajouter, créer des fichiers).

    * Les utilisateurs peuvent supprimer ou renommern'importe quel fichier dans ce répertoire, quel que soit le propriétaire du fichier.

    * Cela peut potentiellement poser des problèmes de sécurité si plusieurs utilisateurs partagent le même répertoire et que la suppression ou le renommage de fichiers par d'autres utilisateurs n'est pas souhaitable.
---


- Pour éditer le fichier crontab de l'utilisateur actuel, utilisez la commande :


    "crontab -e"
---


- Si c'est la premiére fois que vous ouvrez le crontab, ce dernier vous demandera quel éditeur en ligne de commande souhaitez-vous utiliser 
---


    * Select an editor. To change later, run 'select-editor'.

        1. /bin/nano <---- easiest
        2. /usr/bin/vim.basic
        3. /usr/bin/nvim
        4. /usr/bin/vim.tiny
        5. /bin/ed

    Choose 1-5 [1]:
---


# **Exemple de planification**
---


    "0 0 * * * commande"


**Exécuter tous les jours à minuit.**

---

    "30 8 * * 1 commande"


**Exécuter tous les lundis à 8h30.**

---


    "0 * * * * commande"


**Exécuter chaque heure.**

---


# **Commandes Utiles pour Crontab**
---


    "crontab -l"


**Lister les tâches planifiées.**

---


    "crontab -r"


**Supprimer toutes les tâches planifiées.**

---


# **Exemples pratiques**
---


## **Planifier l'écriture dans un fichier avec un intervalle de 5 min**
---


    "*/5 * * * * echo "Bonjour !" >> /chemin/vers/mon/fichier.txt"


**Attention à ne pas écrire :**


    "5 * * * * echo "Bonjour !" >> /chemin/vers/mon/fichier.txt"
---


**En effet, il y à une grosse différence entre écrire 5 au lieu de */5 :**


    * La première notation */5 indique un intervalle régulier de 5 minutes.


    * La deuxième notation 5 indique une exécution spécifique à la cinquième minute de chaque heure.
---


# **Exécuter un script toute les deux heures :**
---


    "0 */2 * * * /chemin/vers/votre/script.sh"


**Dans cette configuration, */2 dans le champ des heures signifie que la tâche sera exécutée toutes les 2 heures.**

---


# **Supprimer le cache du systeme tout les lundi à trois heures du matin :**
---


**Pour pouvoir effectuer des tâches planifier au niveau système, vous devez exécuter la commande suivante pour pouvoir créer une tâche planifiée avec les droits root** 


    "sudo crontab -e"
---

    "0 3 * * 1 /bin/rm -rf /tmp/*"


**Ici, le script s'exécutera tout les lundi ( 1 ) à trois heure du matin ( 3 ) à la minute 0 .**

---