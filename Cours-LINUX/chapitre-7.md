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