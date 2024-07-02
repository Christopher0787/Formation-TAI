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