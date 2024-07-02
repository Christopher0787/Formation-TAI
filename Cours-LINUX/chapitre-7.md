# **Les scripts**
---


# **La notion de shebang**
---


La première étape lorsque l’on créer un script sur linux, c’est de définir la portabilité de ce script.

Sur linux, il existe plusieurs shells, en voici quelques-uns :


    * bash, pour Bourne Again Shell, celui qui représente 99% des distributions.

    * sh, pour Bourne Shell, qui est le plus ancien shell.

    * zsh, pour Z shell, qui est plus récent et compatible Bash avec des fonctionnalités supplémentaires.
---

En bref, il en existe beaucoup d’autres, mais le plus important à retenir ici est que lorsque l’on créer un script, le toute première ligne est nommée le shebang, elle
permet de définir le shell à utiliser pour exécuter notre script.


De ce fait, si je mets comme shebang #!/bin/bash, mon script utilisera bash. Sauf que, si vous désirez rendre ce script portable et donc qu’il puisse s’exécuter aussi
bien sur des distributions modernes que des plus anciennes, ça ne marchera pas ! et pour cause, il existe encore certaines distributions où le shell par défaut est sh, et
bash n’est pas installé.

---

**C’est donc à vous de voir :**


    * Vous souhaitez rentre votre script portable ? Utilisez sh.

    * Si vous souhaitez créer un script uniquement pour les distributions GNU/Linux, utilisez bash.
---

Dans ce cours, nous utiliserons bash, mais si vous souhaitez utilisez un autre shell, la méthode reste la même ! Par exemple, il vous suffis de remplacer#!/bin/bash
par #!/bin/sh.

---


# **Rendre le script exécutable**
---


    "nano script.sh"
---

**Créer et ouvrir le script.**


    "#!/bin/bash"


    "echo "Bonjour !""
---


**Déclaration du shebang et ajout de la commande echo "Bonjour" .**


    "chmod +x script.sh"
---


**Ajout de la permission d'exécution sur le script.**


    "./script.sh"
---


Exécution du script.

Maintenant, le script s’exécute correctement et nous affiche bien « Bonjour ! ». On va pouvoir s’attaquer à la partie algorithmie de Bash 

---


# **Les variables**
---


La première chose que vous allez apprendre ici est comment créer des variables et leur attribuer des valeurs.

Réouvrez votre script avec nano script.sh et commencez simplement par créer deux variables :


    "#!/bin/bash"


    "prenom="Nathan""

    "age=21"


    "echo "Bonjour $prenom ! Tu as $age ans""
---


Une fois enregistrer et exécuter, le script retournera :


    "Bonjour Nathan ! Tu as 21 ans"


⚠ Attention, Vous devez englober votre message avec des doubles quotes " " car si vous utilisez des simples quotes ' ' , Bash considèrera vos variables comme
du simple texte et renverra ceci :


    "Bonjour $prenom ! Tu as $age ans"


Avant de clôturer ce chapitre sur les variables, il faut savoir qu'il existe une troisième sorte de quotes, appelé les back quotes, qui sont des accents graves ` ` .

Ces back quotes sont un peu spéciales, elles permettent de dire à Bash d'exécuter ce qui se trouve à l'intérieur :


    "#!/bin/bash"


    "prenom="Nathan""

    "age=21"

    "hote=`hostname`"


    "echo "Bonjour $prenom ! Tu as $age ans""

    "echo "Je suis $hote, ta machine !""
---


Dans cette exemple, Bash a exécuté la commande hostname qui permet de retourner le nom de l'hôte, d'où le resultat Ubuntu 

    "Bonjour Nathan ! Tu as 21 ans"

    "Je suis Ubuntu, ta machine !"
---


# **Les conditions**
---