# **Gestion des utilisateurs/groupes et permissions :**
---

# **Ce chapitre explique comment créer et gérer les utilisateurs / groupes, ainsi que la gestion des permissions de fichiers sous Linux.**
---

## **La gestion des utilisateurs/groupes dois s'éffectuer en temps qu'administrateur (root) ou à l'aide de sudo.**
---


# **Gestion des utilisateurs**
---


### * Création d'un utilisateur


"sudo adduser nomUtilisateur"


### **La commande adduser permet de créer un nouvel utilisateur.**
---


### * Modification d'un mot de passe utilisateur


"sudo passwd nomUtilisateur"


### **La commande passwd permet de changer le mot de passe d'un utilisateur.**
---


### * Renommer un utilisateur


"sudo usermod -l nouveauNomUtilisateur ancienNomUtilisateur"


### **La commande usermod -l permet de changer le nom de l'utilisateur en un nouveau nom d'un utilisateur**
---


### * Supprimer un utilisateur


"sudo deluser nomUtilisateur"


### **La commande deluser permet de supprimer un utilisateur.**
---


### * Afficher la liste de tous les utilisateurs


"getent passwd"


### **La commande passwd permet de definir le mot de passe d'un utilisateur**
---


# **Gestion des groupes**
---


### * Création d'un groupe


"sudo groupadd nomGroupe"


### **La commande groupadd permet de créer un nouveau groupe.**
---


### * Supprimer un groupe


"sudo delgroup nomGroupe"


### **La commande delgroup permet de supprimer un groupe.**
---


### * Ajouter un utilisateur à un groupe


"sudo usermod -aG nomGroupe nomUtilisateur"


### **l'option -aG siginifie "add group".**
---


### * Modifier le groupe primaire d'un utilisateur


"sudo usermod -g nomGroupe nomUtilisateur"


### **La commande usermod -g permet de définir ou modifier le groupe primaire d'un utilisateur.**
---


### * Modifier le groupe secondaire d'un utilisateur


"sudo usermod -G nomGroupe nomUtilisateur"


### **La commande usermod -G pemet de définir ou modifier le groupe secondaire d'un utilisateur.**
---


### * Afficher la liste de tous les groupes


"getent group"


### **La commande getent group permet d'afficher les membres d'un groupe d'utilisatuer.**
---


# **Gestion des permissions de fichiers**
---


### * Afficher les permissions d'un fichier


"ls -l nomFichier"


### **La commande ls -l affiche les permissions d'un fichier ou d'un répertoire.**
---


### * Modification des permissions


"chmod permissions nomFichier"


### **La commande chmod permet de modifier les permissions d'un fichier ou d'un répertoire.**
---


### * Les permissions peuvent être définies de plusieurs manière. Imaginons que je souhaite donner des permissions à mon utilisateur :


"chmod u+rwx nomDuFichier"


    * u veux dire utilisateur.

    * + désigne le fait que je souhaire ajouter des permissions.

    * r signifie read (lire), et donc autorise mon utilisateur à lire le fichier.

    * w signifie write (écrire), et donc autorise mon utilisateur à écrire dans le fichier.
    
    * x signifie exécute (éxecuter), et donc autorise mon utilisateur à exécuter le fichier.


"chmod u-rwx nomDuFichier"


### **de la même manière, si vous souhaitez retirer des permissions, utilisez - au lieu de +.**
---


"chmod g+rwx nomDuDossier"


### **pour les groupes avec g.**
---


"chmod o+rwx nomDuDossier"


### **pour les autres utilisateurs avec o.**
---