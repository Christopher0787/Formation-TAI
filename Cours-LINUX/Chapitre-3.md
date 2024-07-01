# **Personnalisation de Bash et découverte de Zsh :**
---


## **Les Shells**
---


### * Un shell et le programme qui va executer vos commandes dans un terminal, il en existe plusieurs :


    * Sh -> premier shell.

    * Bash -> reprend des fonctionnalité du shell sh avec des optimisations.

    * Zsh -> un des derniers venu dans le monde des shells qui reprend les fonctionnalités de plusieurs shell avec plusieurs optimisation.
---

 
## **Modifier son shell**
---


### * Vous pouvez customizer votre shell en ligne de commande.
---


### **Bash**
---


### * Sur bash, la configuration de votre shell se fait grâce au fichier .bashrc qui se trouve dans votre home directory (chaque utilisateur à son propre .bashrc), et donc, lamodification du shell se fait à l'échelle de l'utilisateur.


### * Si vous souhaitez modifier votre configuration bash vous devez donc entrer la commande (dans votrehome directory) :


"nano .bashrc"


### **Vous allez ouvrir un éditeur en ligne de commande (nano) avec le fichier.bashrc que vous pouvez modifier.**
---


### **Modifier le prompt**


### * Le prompt est l'invite de commande (le texte qui s'affiche avec de lancer chaque commande). Si vous souhaitez le modifier, allez à la fin du fichier .bashrc et écrivez :


"export PS1="nouveau prompt $ ""


### **La variable PS1 est utilisé par bash pour afficher le prompt, vous pouvez donc modifier votre prompt en la redéfinissant.**
---


### **Les variables d'affichage**
---


### * Pour avoir un prompt dynamique et afficher des informations sur l'utilisateur connecté ou encore l'emplacement du terminal, vous devez connaitre leurencodage pourles définir dans votre prompt :


    * \u -> pour afficher l'utilisateur.

    * \t -> afficher l'heure.

    * \w -> afficher l'emplacement du terminal.

    * \h -> nom de votre sytème.


"export PS1="\u@\h \t \w $ ""


### **Vous pouvez les afficher dans votre prompt comme ceci :**
---


"nathan@ubuntu 12:15:48 ~ $"


### **qui vous donnera :**
---


## **Les Alias**


### * Les alias permettent de créer des raccourcies vers des commandes. Il dois être déclaré dans le fichier de configuration du shell (.bashrc pour Bash).


"alias ll="ls -al""


### **cette alias permet d'exécuter la commande ls -al lorque l'on écrit ll et renverra donc :**
---


### * total 416

    * drwx------. 1 nathan nathan 1096 8 nov. 21:29 .
    * drwxr-xr-x. 1 root root 12 21 juil. 02:00 ..
    * drwxr-xr-x. 1 nathan nathan 0 27 oct. 14:15 .android
    * drwxr-xr-x. 1 nathan nathan 320 31 oct. 18:05 auto-cpufreq
    * -rw-------. 1 nathan nathan 3019 23 oct. 13:46 .bash_history
    * -rw-r--r--. 1 nathan nathan 18 6 févr. 2023 .bash_logout
    * -rw-r--r--. 1 nathan nathan 141 6 févr. 2023 .bash_profile
    * -rw-r--r--. 1 nathan nathan 534 8 nov. 21:31 .bashrc
    * drwxr-xr-x. 1 nathan nathan 0 28 sept. 20:29 Bureau
    * drwx------. 1 nathan nathan 822 31 oct. 18:00 .cache
    * drwxr-xr-x. 1 nathan nathan 52 27 oct. 14:23 CAMPUS
    * drwxr-xr-x. 1 nathan nathan 28 23 oct. 13:57 .composer
    * drwxr-xr-x. 1 nathan nathan 792 28 oct. 15:49 .config
    * drwxr-xr-x. 1 nathan nathan 8 2 oct. 18:07 'copy paste'
    * drwx------. 1 nathan nathan 66 28 sept. 22:11 .docker
    * drwxr-xr-x. 1 nathan nathan 28 27 oct. 09:17 Documents
    * drwxr-xr-x. 1 nathan nathan 12 28 sept. 21:52 .dotnet
    * -rw-r--r--. 1 nathan nathan 48 23 oct. 14:06 .gitconfig
    * drwx------. 1 nathan nathan 8 28 sept. 23:07 .gnome
    * drwxr-xr-x. 1 nathan nathan 42 29 sept. 15:43 .icons
    * drwxr-xr-x. 1 nathan nathan 488 27 oct. 14:54 Images
    * drwxr-xr-x. 1 nathan nathan 30 29 sept. 09:07 .java
    * drwx------. 1 nathan nathan 26 31 oct. 18:00 .local
    * drwxr-xr-x. 1 nathan nathan 0 28 sept. 20:29 Modèles
    * drwxr-xr-x. 1 nathan nathan 48 28 sept. 20:30 .mozilla
    * drwxr-xr-x. 1 nathan nathan 0 28 sept. 20:29 Musique
    * drwx------. 1 nathan nathan 18 29 sept. 08:55 .mysql
---


# **Installer le shell zsh**
---


### * Pour installer le shell zsh vous devez d'abord installer le paquet avec apt :


"sudo apt install zsh"


### * Pour changer de shell pendant une session du terminal :


"zsh"


### **Pour zsh :**
---


"bash"


### **Pour bash :**
---


"chsh"


### **Changer le shell par défaut (au lancement du terminal) :**
---


### * Et ensuite vous entrez le chemin vers le shell :usr/bin/zsh ou usr/bin/bash.


### * Vous devez ensuite redémarrer la session utilisateur pour que les modifications du shell par défaut soientprise en compte.
---


# **Customization zsh**
---


### * Pour zsh, le fichier de configuration se nomme .zshrc, pour modifier votre shell zsh, vous devez donc modifier ce fichier.
---


"export PROMPT="Nouveau prompt""


### * Pour modifier le prompt, zsh utilise la variable PROMPT, vous devez écrire à la fin du fichier.zshrc :
---


### **Les variables dynamiques :**
---


    * %n% -> Nom de l'utilisateur.

    * %~% -> emplacement du terminal.

    * %t% -> heure.

### * Si vous voulez plus d'information et de possibilité sur la customization prompt avec zsh -> Cliquez ici.
---


# **Utiliser Oh-My-Zsh**
---


### **Oh-my-Zsh est unplugins de customization poussé de votre shell zsh, il va grandement faciliter la customization de votre shell et vous donner la possibilité d'utiliserdes plugins pour vous aider dans l'utilisation de votre terminal.**
---


## **Installation**
---