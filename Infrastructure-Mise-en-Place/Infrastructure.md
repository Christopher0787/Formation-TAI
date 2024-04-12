# **Mise en Place D'une Infrastructure**

## **Étape 1**

    -  branchement câbles switch et routeur en faisant attention au câble de l’IDRAC connectant le serveur au switch.
 
## **Étape 2**

    – Réinitialiser le switch ( ?) t’attends que le switch soit allumé puis tu mets l’épingle dans le trou pour le redémarrer, tu sais quand toutes les lumières sont allumées.
 
    - Avec le PowerShell on vérifie en pinguant le switch sur son adresse par défaut qui est 192.168.1.254
 
    - On s’attribue une adresse fixe puis on indique sur la carte Ethernet dans le même numéro de réseau que le switch, en mettant la masque de sous réseau équivalent puis laisser la passerelle et le DNS vide.
 
## **Étape 3**

    - réinitialisation du serveur en maintenant le bouton minuscule appuyé à côté de l’écran jusqu’à ce qu’il fasse du vacarme. En principe l’écran devrait se mettre en marche. Sur l’écran configurer l’interface console IDRAC en 192.168.1.253 mettre rien pour la passerelle (GTW = Gateway). 
 
## **Étape 4**

    - indiquer dans une page web l’adresse configurée dans le serveur. 192.168.1.253. Entrer root comme identifiant et calvin comme mot de passe qui sont les identifiants par défaut. 
 
## **Étape 5** 
    - Redémarrer le serveur et préparer les disques en RAID5 

- Appuyer sur F11ou F12

- Faire contrôle R quand la configuration RAID apparaît

- Aller dans Virtual disc

- choisir la suppression des disques virtuels

- Réinitialiser la configuration des disques virtuels

- Faire Fn F2

- Unconfigured Physical Disks Fn F2

- Faire un Fast Init pour les disques RAID pour un formatage rapide

- Non configuration Create New Virtual Disk RAID-5 dans RAID level

- Faire entrée à côté de chaque disque pour les sélectionner 

- Renommer dans Basic Settings dans cet exemple DATAs

- Faire échap pour « do you want to exit ». Maintenant échap. 

- Puis rebooter le serveur sur une clef contenant windows server.

(on peut aller dans alimentation puis aller dans ‘cycle d’alimentation du système redémarrage à froid – pour info à froid il arrête tout alors qu’avec le redémarrage à chaud refait une séquence de démarrage.)
 
- Rester appuyé sur Fn puis taper F11 ensuite 

- Aller dans le boot manager

- Puis sélectionner le BOOT UEFI (F10 )

- Aller dans la sélection qui mentionne l’USB pour booter sur la clef

- Lors de l’installation Windows l’installer 
 
## **Étape 6** 

    - Définir un mot de passe sécurisé « azerty1234@ » comme mot de passe admin histoire de prouver que le mot de passe est sécurisé
 
## **Étape 7**

    - Brancher le serveur sur l’interface une en RJ45 sur un des ports du switch. 
 
## **Étape 8** 

    - Attribuer une IP statique au serveur dans la plage appropriée en cliquant sur NIC1    
             - 192.168.1.50

    - Dans la case « DNS préféré » sur l’interface loopback 127.0.0.1 l’interface réseau locale qui ne sort pas de l’ordinateur son interface locale de loopback. 
 
## **Étape 9**  

    - Renommer son serveur « SRV_DAV »   
 
    - Installer AD DS

    - Dans terminer la configuration sur active directory et créer une nouvelle forêt qui aura pour domaine « corporation.lan »
 
## **Étape 10**

- Dans le menu démarrer  « Utilisateurs et groupes Active Directory » 

- Aller dans corporation.lan clic droit nouveau – Unité d’organisation

- Créer une OU CORPORATION 

- Refaire puis à l’intérieur de cette OU créer deux nouvelles unités d’organisation Users et Computers
 
## **Étape 11**

    - Dans l’unité organisationnelle « USERS » créer 2 utilisateurs par stagiaire avec le mot de passe   « azerty1234A@ » donc six utilisateurs PC.

    - Utilisateur 1 à 6 et faire en sorte que  le mot de passe n’expire jamais.
 
## **Étape 12**

    - Sur Virtual Box créer deux utilisateurs un en windows 10 un en windows 11 – Windows 11 Pro « PC-WIN11-5
 
## **Étape 13**

    - Configurer une IP statique sur vos clients et ajouter comme DNS préféré l’IP du serveur soit 192.168.1.50
 
## **Étape 14**

    - Sur Windows server installer un serveur DHCP windows avec une nouvelle étendue de classe C allant de 192.168.1.1 – 192.168.1.50 ainsi qu’un masque adapté en utilisant la méthode du vlsm. Ensuite ajouter comme passerelle l’adresse IP du Windows server 192.168.1.59 donc en /26. 
 
## **Étape 15**

    - Dans le sysvol de windows server
    - Disque Local>Windows>Sysvol
    - Insérer une clef avec les versions mobiles de Wireshark et de NPCAP
 
    - Aller dans la VM cliquer sur le réseau / autoriser la découverte de réseau / dans la barre de recherche inscrire \\lenomdedomaine   donc dans cet exemple corporation.lan puis cliquer sur sysvol pour retrouver les documents
 
    - créer un répertoire partagé et ajouter à l’intérieur de ce dernier un installateur de Wireshark et NPCAP. Ensuite, depuis vos clients installez-les
 
## **Étape 16**

    - Exécutez Wireshark monitorez l’interface ETHERNET et filtrez par dhcp
 
## **Étape 17**

    - Modifiez la carte réseau des clients et regardez le DHCP DORA dans Wireshark 
 
 
- (mRemote est à proscrire pour des raisons de sécurité car on autorise tout le monde à se connecter sur le port RDP)
 
## **Étape 18**
 
    - Déplacer les pc dans le dossier Computer

    - Créer la GPO à la racine de l’unité de groupe corporation.
 
    - La GPO ne marchera pas dans la mesure où les Windows ne sont pas activés.
 
 
- voir dans le tuto suivant
 
### - https://www.it-connect.fr/copier-et-deployer-un-fond-decran-par-gpo/
 
- Le fichier source est dans le dossier de partage,

- le fichier de destination est le dossier dans lequel il doit être déposé dans les machines clients donc dans les dossiers Wallpaper.
 
### - C:\Windows\Web\Wallpaper\wallpaper.png
 
## **Étape 19**
 
    - Configuration du serveur de temps. Intégré par défaut sur le Windows server mais n’est pas installé
 
    - Taper sur le powershell administrateur dans le windows server

- w32tm /config /manualpeerlist:"fr.pool.ntp.org" /syncfromflags:manual /reliable:YES / update
 
- Restart-Service w32time
 
- Pour voir la synchronisation du service de temps
 
- w32tm /query /configuration

---