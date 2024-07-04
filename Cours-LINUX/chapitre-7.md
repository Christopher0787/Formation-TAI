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


En bash comme dans n’importe quel langage de programmation, on retrouvera des conditions que l’on pourra utiliser dans nos scripts.


**Commençons par la plus simple, à savoir la condition if (si en français) :**


    "#!/bin/bash"


    "prenom="Nathan""
    "age=21"
    "hote=`hostname`"


    "if [ $prenom = "Nathan" ]; then"


        "echo "Bonjour $prenom ! Tu as $age ans""
        "echo "Je suis $hote, ta machine !""


    "fi"
---


**Si la variable $prenom est égale à Nathan , alors on écrit :**


    "Bonjour Nathan ! Tu as 21 ans"
    "Je suis Ubuntu, ta machine !"
---


⚠ Attention, plusieurs points sont à noter ici, un espace est OBLIGATOIRE entre les crochets, on ne peut pas écrire par exemple [$prenom="Nathan"] , on doit laisser
deux espaces (avant/après). Il n’est pas nécessaire de faire un espace ou une tabulation entre « ; » et then, mais c’est toujours mieux pour plus de lisibilité.


**Ensuite, il faut savoir qu’on peut écrire cette condition de la manière suivante, qui revient au même, c’est à vous de choisir laquelle vous préférez :**


    "#!/bin/bash"


    "prenom="Nathan""
    "age=21"
    "hote=`hostname`"


    "if [ $prenom = "Nathan" ]"


    "then"


        "echo "Bonjour $prenom ! Tu as $age ans""
        "echo "Je suis $hote, ta machine !""


    "fi"
---


On enlève simplement le « ; » et on place le then sur la ligne en dessous. Certains aiment moins, d’autres préfèrent... le résultat est cependant lemême.


**Passons ensuite à la condition else (sinon en français) :**


    "#!/bin/bash"


    "prenom="Nathan""
    "age=21"
    "hote=`hostname`"


    "if [ $prenom = "Nathan" ]"


    "then"


        "echo "Bonjour $prenom ! Tu as $age ans""
        "echo "Je suis $hote, ta machine !""


    "else"

    
        "echo "Vous êtes qui ?!""


    "fi"
---


**Ici, si la variable $prenom est égale à Nathan , alors on écrit :**


    "Bonjour Nathan ! Tu as 21 ans"
    "Je suis Ubuntu, ta machine !"
---


**Sinon, on écrit :**


    "Vous êtes qui ?"
---


Et enfin la dernière condition que nous verrons, c’est la condition elif (sinon si en français). Globalement, rien de nouveau, on reprend la condition ci-dessus, mais on la modifie pour rendre le tout cohérent :


    "#!/bin/bash"


    "prenom="Nathan""
    "age=21"
    "hote=`hostname`"


    "if [ $prenom = "Nathan" ]"


    "then"


        "echo "Bonjour $prenom ! Tu as $age ans""
        "echo "Je suis $hote, ta machine !""


    "elif [ $prenom = "Anonyme" ]"


    "then"


        "echo "Vous êtes malin..""


    "else"


        "echo "Vous êtes qui ?!""


    "fi"
---


**Ici, si la variable $prenom est égale à Nathan , alors on écrit :**


    "Bonjour Nathan ! Tu as 21 ans"
    "Je suis Ubuntu, ta machine !"


**Sinon si la variable $prenom est égale à Anonyme , alors on écrit :**


    "Vous êtes malin.."
---


**Sinon, on écrit :**


    "Vous êtes qui ?!"
---


# **Variables dynamiques**
---


Nous allons maintenant voire comment rendre nos script plus « Autonome ».


    "#!/bin/bash"


    "prenom="Nathan"
    "age=21"
    "hote=`hostname`"


    "echo "Votre prenom ?""
    "read prenom"


    "if [ $prenom = "Nathan" ]"


    "then"


        "echo "Bonjour $prenom ! Tu as $age ans""
        "echo "Je suis $hote, ta machine !""


    "elif [ $prenom = "Anonyme" ]"


    "then"


        "echo "Vous êtes malin..""


    "else"


        "echo "Vous êtes qui ?!""


    "fi"
---


Ici, la commande read permet de demander à l'utilisateur de définir le contenu de la variable prenom. Grâce à cette commande, il n'est plus nécessaire de changer
manuellement le contenu d'une variable !

---


# **Les boucles**
---


**La boucle while répète un ensemble d'instructions tant qu'une condition est vraie :**


    "while [ condition ]"

    "do"

        "# Instructions à répéter"

    "done"
---


## **Exemple pratique :**
---


    "#!/bin/bash"

    "compteur=1"

    "while [ $compteur -le 5 ]"

    "do"


        "touch fichier_$compteur.txt"
        "echo "fichier $compteur crée""
        "((compteur++))"


    "done"
---


**Ici, tant que la variable compteur est inférieur ou égale à 5, alors :**


    * On créer un fichier portant le numéro du compteur.

    * On écrit fichier $compteur crée .

    * On incrémente la variable compteur de 1.
---


**Voici la liste des comparaisons numériques :**


    * -eq = est égal à

    * -ne = n'est pas égal à

    * -gt = est plus grand que

    * -ge = est plus grand ou égal à

    * -lt = est plus petit que

    * -le = est plus petit ou égal à
---


# **La boucle For**
---


**La boucle for itère sur une séquence d'éléments.**

    "for variable in liste"

    "do"

        "# Instructions à répéter pour chaque élément"

    "done"
---


**Exemple :**


    "#!bin/bash"

    "dossiers=("Bureau" "Musique" "Video" "Téléchargement")"

    "for dossier in "${dossiers[@]}""

    "do"

        "echo $dossier"

    "done"
---


**Ici, pour chaque élément dossier dans le tableau dossiers :**


    " On écrit le nom du dossier contenu dans le tableau.
---


## **Exemple pratique 1 :**
---


    "#!/bin/bash"

    "repertoire="/home/ubuntu""

    "for element in "$repertoire"/*"

    "do"

        "echo $element"

    "done"
---


***Ici, pour chaque élément element dans le répertoire repertoire/* :**

    * On écrit le nom du dossier ou fichier contenu dans le répertoire.


**Avant de passer à la prochaine partie, il faut savoir qu'il existe un autre type de boucle for, appelée la boucle for arithmétique !**

**Elle est utilisée pour effectuer des itérations numériques et est particulièrement utile lorsque vous avez besoin de compter de manière arithmétique, par exemple, pour itérer sur un certain nombre de fois :**


    "#!/bin/bash"

    "for ((initialisation; condition; itération))"

    "do"

        "# Instructions à répéter"

    "done"
---


**Vous vous rappelez des fichiers que vous avez générés avec la boucle while un peu plus haut dans le cours ? Et bien grâce à la boucle for arithmétique, nous allons les renommer !**

---


## **Exemple pratique 2 :**
---


    "#!/bin/bash"

    "for ((i=1; i<=5; i++))"

    "do"

        "mv fichier_$i.txt nouveau_fichier_$i.txt"

    "done"
---


**Ici, la variable i est égale à 1, tant que i est inférieur ou égale à 5, j'incrémente i de 1 et je renomme le fichier.**

---

**Pour faire simple, le script continuera de boucler tant que la variable i ne sera pas supérieur à 5 ! Facile, non ?**

---


# **Les fonctions**
---


**Les fonctions permettent de regrouper des blocs de code réutilisables, facilitant ainsi la modularité et la maintenance des scripts.**

---


## **Syntaxe de Déclaration**
---


    "nomDeLaFonction() {
        # Instructions de la fonction
    }"
---


## **Syntaxe d'Appel**
---

    "nomDeLaFonction"
---


## **Exemple fonction simple :**
---


    "#!/bin/bash"

    "bonjour() {

        "echo "Bonjour !"
    }"

    "bonjour"
---


**Dans cet exemple, la fonction bonjour affiche un message simple. Lorsque la fonction est appelée, le message est affiché. Une fois exécuté :**


    "Bonjour !"
---


## **Exemple fonction avec paramètres**
---


    "#!/bin/bash"

    "bonjour() {

        "echo "Bonjour $1 !"
    }"


    "bonjour "Nathan""
---


**Dans cet exemple, la fonction bonjour prend un paramètre (ici, "Nathan") et affiche un message personnalisé. Une fois exécuté :**

    "Bonjour Nathan !"
---


**Il est également possible de passer plusieurs paramètres à la fonction :**


    "#!/bin/bash"

    "bonjour() {

        "echo "Bonjour $1 ! Tu as $2 ans !"
    }"

    "bonjour "Nathan" 21"
---


**Une fois exécuté :**

    "Bonjour Nathan ! Tu as 21 ans !"
---


**Vous l'aurez compris, si vous souhaitez par exemple rajouter un troisième paramètre, il suffira de le déclarer dans la fonction avec la variable $3 , et ainsi de suite !**

---


## **Exemple fonction avec retour de valeur**
---


**Les fonctions peuvent également retourner des valeurs !**


    "#!/bin/bash"

    "addition() {

        "local resultat=$(( $1 + $1 ))
        "echo $resultat

    }"

    "calcul=$(addition 5)
    "echo "Résultat du calcul : $calcul"
---


**Une fois exécuté :**

    "Résultat du calcul : 10"
---


**Dans cet exemple, vous avez découvert de nouveaux principes :**


    * La commande local . elle permet de déclarer une variable avec une portée locale à la fonction. Cela signifie que la variable ne sera accessible qu'à l'intérieur de la fonction où elle est déclarée, et ne modifiera pas une variable portant le même nom en dehors de la fonction.

    * La substitution arithmétique $(( )) . Utilisé pour effectuer des opérations mathématiques.

    * La commande de substitution $( ) . Utilisé pour exécuter une commande et utiliser son résultat.
---


## **Exemple de scripts**
---


### **Vérifier l'âge de l'utilisateur**


    "#!/bin/bash"


    "valider_age() {
        "if [ $1 -ge 18 ]; then
            "echo "Accès autorisé."
        "else
            "echo "Accès refusé. Vous devez avoir au moins 18 ans."
        "fi
    }"


    "# Demander l'âge à l'utilisateur"
    "echo -n "Entrez votre âge : ""
    "read age"


    "# Appel de la fonction de validation"
    "valider_age $age"
---