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