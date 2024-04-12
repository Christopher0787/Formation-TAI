# **Création de Partage de Fichier**

VM :
    1) Ajouter un disque
    2) Ajouter une interface réseau(Bridge ou "par pont")


Windows :
    1) Initialiser le disque
    2) Créer l'arborescence
    3) Appliquer les protections (groupes ou utilisateurs ) Attention: ne concerne que les donner sur le disque
    4) Ajouter le rôle "Serveur de Fichier"
    5) Gestionnaire de serveur -> Serveur de ficher et de stockage -> onglet partage -> tache -> nouveau partage
    6) SMB-Rapide
    7) Emplacement ->Tape un chemin personnalisé -> Bouton -> choisir le disque et le repertoire
    8) Donner un nom au partage
    9) Garder l'option mis en cache

    ---