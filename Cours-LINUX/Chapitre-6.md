# **Tâches Planifiées sous Linux**
---


# **Introduction**
---


* Les tâches planifiées, également connues sous le nom de cron jobs, sont un moyen puissant d'automatiser l'exécution de scripts, de commandes ou de programmes à des intervalles spécifiés. Sous Linux, le service responsable de la planification des tâches est appelé Cron. Ce chapitre explore les concepts fondamentaux des tâches planifiées et comment les utiliser efficacement.
---


# **Syntaxe**
---


* Les tâches planifiées sont définies en utilisant la syntaxe suivante dans le fichier crontab :


    # Minute (0 - 59)
    # | Heure (0 - 23)
    # | | Jour du mois (1 - 31)
    # | | | Mois (1 - 12)
    # | | | | Jour de la semaine (0 - 6, où 0 = dimanche)
    # | | | | |
    * * * * * commande à exécuter
---


# **Accéder au Crontab**
---