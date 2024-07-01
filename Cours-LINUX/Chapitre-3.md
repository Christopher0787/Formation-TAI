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