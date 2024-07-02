# **Gestion des services**
---


## **La gestion des services sous Linux est cruciale pour assurer le bon fonctionnement du système.**
---


# **Gestion des Services avec systemd**
---


    "systemctl start nomDuService"


**Démarrer un service.**

---


    "systemctl stop nomDuService"


**Stopper un service.**

---


    "systemctl restart nomDuService"


**Redémarrer un service.**

---


## **Vérification de l'état d'un service**
---


    "systemctl is-active nomDuService"


**Afficher le status d'un services.**

---


    "systemctl status nomDuService"


**Afficher plus d'informations sur un service.**

---


    "systemctl list-units --type=service"


**Afficher la liste des servicesactifs.**

---


## **Configuration au démarrage**
---


    "systemctl enable nomDuService"


**Activer un service au démarrage.**

---


    "systemctl disable nomDuService"


**Désactiver un service au démarrage.**

---


# **Surveillance des services**
---


## **Utilisation de journalctl**
---


    "journalctl"


**Afficher les logs du système.**

---


    "journalctl -u nomDuService"


**Afficher les logs d'un service.**

---


    "journalctl -p niveauDePriorite"


**Filtrer les logs par priorité.**

---


## **Filtrer par Plage de Temps**
---


    "journalctl --since "YYYY-MM-DD HH:MM:SS""


**Afficher les logs depuis un certain temps.**

---


    "journalctl --until "YYYY-MM-DD HH:MM:SS""


**Afficher les logs jusqu'à un certain temps.**

---


## **Options de Formatage**
---