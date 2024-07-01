# **l'interface en ligne de commande :**
---

# **Navigation dans le terminal**
---


"cd nomDuDossier"

### **Pour change directory -> permet de changer le dossier courant du terminal**
---


"cd .."

    * Le ... fait référence au dossier parent

    * Le . fait référence au dossier courant

    * Le ~ fait référence au home directory (le dossier "racine" de votre utilisateur)
---


# **Gestion des dossiers dans le terminal**
---


"mkdir nomDuDossier"

### **Pour make directory -> permet de créer un dossier dans l'emplacement actuel.**
---


"rmdir nomDuDossier"

### **Pour remove directory -> permet de supprimer un dossier vide (attention, cette commande ne marche que si le dossier estvide).**
---


"rm -r nomDuDossier"

### **Pour remove avec l'option récursif, utilisé sur dossier non vide, celui signifie que la commande va supprimer tout ce qui se trouve dans le dossier avant de supprimerle dossier (⚠ Attention, cette commande supprime tout sans poser de questions à utiliser seulement si vous êtes sûr de ce que contient le dossier).**
---


"rm -ri nomDuDossier"

### **Avec l'argument informatif en plus de récursif, qui signifie que le terminal vous demandera de valider chaque suppression.**
---



# **Création de fichier**
---


"touch nomDuFichier.txt"

### **Permet de créer un fichier vide OU de modifier la date de création du fichier s'il existe déjà.**
---


"echo "Bonjour" > fichier.txt"

### **Permet de lancer la commande echo "bonjour" et de rediriger les données de sortie dans le fichier fichier.txt, si le fichier n'existe pas, il sera créé.**
---


"echo "Au revoir" >> fichier.txt"

### **Permet de lancer la commande echo et de rediriger les données de sortie dans le fichier bonjour.txt à la fin du fichier (sans écraser les données).**
---


"nano fichier.txt"

### **Nano est un éditeur en ligne de commande, vous allez l'ouvrir et pouvoir écrire votre fichier, et ensuite enregistrer le fichier.**
---


"rm fichier.txt"

### **Pour remove -> permet de supprimer le fichier.**
---


# **Déplacer des dossiers ou fichiers**
---


"mv nomDuDossier DestinationDossier"

### **Pour move -> permet de déplacer un dossier ou un fichier dans un emplacement différent.**
---


"mv ancienNom DestinationDossier/nouveauNom"

### **Permet de renommer un dossier ou un fichier.**
---



# **Copier Coller des dossiers ou fichiers**
---


"cp -r nomDuDossier DestinationDossierCopie"

"cp nomDuFichier DestinationFichierCopie"

### **pour copy -> permet de copier coller un dossier ou un fichier dans un emplacement différent (ne pas oublier l'option-r pour récursif pour la copie d'un dossier).**
---


# **Afficher le contenu d'un fichier**
---


"cat nomDuFichier"

### **pour concaténer -> permet d'afficher tout le contenu d'un fichier**
---


"tail nomDuFichier"

### **Permet d'afficher les 10 dernières lignes d'un fichier**
---


"tail -n 20 nomDuFichier"

### **Permet d'afficher les 20 dernières lignes d'un fichier**
---


"tail -f nomDuFichier"

### **Permet d'afficher en temps réel le contenu d'un fichier**
---


# **Lister les éléments d'un dossier**
---


"ls"

### **Affiche la liste des éléments du dossier actuel**
---


"ls -a"

### **Affiche tous les éléments (même cachés) du dossier actuel**
---


"ls -al"

### **Affiche tous les éléments du dossier actuel avec les droits utilisateurs**
---


# **Information processus**
---