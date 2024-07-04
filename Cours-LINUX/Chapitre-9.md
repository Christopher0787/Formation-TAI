# **Réseautage**
---


## **Configurer le nom du réseau d'un serveur**
---


**Le nom réseau d'un serveur Linux (aussi appelé "system hostname") sert d'identifiant par défaut de la machine pour tous les services et applications qui s'exécutent en local et pour beaucoup de services et d'applications lorsque ceux-ci communiquent sur le réseau.**

---

**Prenez l'exemple d'un serveur de fichiers logs centralisés sur un réseau interne : toutes les communications logs des serveurs du réseau seront préfixées de leur nom réseau, ce qui permettra au service de centralisation des logs de savoir d'où viennent tels ou tels fichiers.**

---

**Le fichier /proc/sys/kernel/hostname contient la valeur courante du nom réseau du serveur.**

    "cat /proc/sys/kernel/hostname"
---    
    
**pour modifier ne nom réseau du serveur, il faut utiliser hostnamectl :**

    "hostnamectl set-hostname nouveauNom"
---

**il est également possible de modifier directement le nom dans le fichier /etc/hostname , ce dernier permet d'initialiser le nom réseau du serveur au démarrage du système.**

---

**Dernier point concernant ce nom réseau : il est de coutume de le garder sous un format très simple, le plus souvent, un mot, représentant un champ lexical commun entre plusieurs serveurs.**

---

**il existe beaucoup de nomenclatures de nom réseau en entreprise, allant de :**

    * la reprise de noms célèbres de villes du monde ( sydney, berlin, paris, etc. ),

    * en passant par des noms de planetes dans Star Wars( Dagobah, Tatooine, etc. ),

    * à des noms réseaux purement analytiques reprenant par exemple leur localisation ou leurs objectifs en termes de services ( web01mutu, srv10, mailintra, etc.).
---


## **Détecter les interfaces réseaux du système**
---


**Avant toute configuration, il est nécessaire de s'assurer que le noyau Linux a bien détecté les cartes réseaux connectées d'une manière ou d'une autre sur la machine.**

---

**La commande dmesg permet afficher les messages du noyau au démarrage :**

    "dmesg"
---

**dans certains cas, il est possible d'essayer de détecter les cartes réseaux reconnues par le noyau lors du démarrage :**

    "dmesg | grep Network"
---

**Consulter le système de fichier virtuel /sys pour lister les interfaces réseaux :**

    "ls -l /sys/class/net"
---

    "total 0"
    "lrwxrwxrwx. 1 root root 0 4 déc. 19:13 enp2s0 -> ../../devices/pci0000:00/0000:00:02.1/0000:02:00.0/net/enp2s0"
    "lrwxrwxrwx. 1 root root 0 4 déc. 19:13 lo -> ../../devices/virtual/net/lo"
    "lrwxrwxrwx. 1 root root 0 4 déc. 19:13 wlp3s0 -> ../../devices/pci0000:00/0000:00:02.2/0000:03:00.0/net/wlp3s0"
---


**Ici, j'ai trois interfaces réseau :**

### **1. enp2s0 :**

    * Cette interface est associée à un périphérique réseau filaire (Ethernet). En d'autres termes, c'est la connexion par câble.
---

### **2. lo :**

    * C'est une interface spéciale appelée interface loopback.

    * Cette interface est virtuelle et est utilisée pour la communicationinterne sur votre propre ordinateur. C'est comme une connexion à vous-même.

    * Elle est souvent référencée par l'adresse IP127.0.0.1 et permet aux applications sur votre ordinateur de communiquer avec d'autres applications sur le même ordinateur.
---


### **3. wlp3s0 :**

    * Cette interface est associée à un périphérique réseau sans fil (Wi-Fi). C'est la connexion sans fil.
---

# **Configurer les cartes réseaux de manière dynamique**
---

**Pour les plus anciens d'entre nous, la commande permettant de configurer une interface réseau de manière dynamique était ifconfig .**

**Cependant cette commande et le package associé net-tools ne sont plus maintenus depuis 2009. Notamment parce que la communauté de développeurs considérait qu’elles n’étaient pas optimisées, ne profitant pas non plus des nouvelles fonctionnalités des noyaux Linux. Ainsi la commande ifconfig mais également des commandes comme netstat, sont dépréciées.**

**Heureusement, le package iproute2 fournit les commandes qui remplacent les précédentes.**

**En l'occurrence, désormais, sur toutes les distributions Linux, vous pouvez configurer de manière dynamique les cartes réseaux avec la commande ip .**

**Voici comment utiliser la commande ip :**


## **Afficher les informations sur les interfaces réseau**


    "ip a"

    "1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000"
        "link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00"
        "inet 127.0.0.1/8 scope host lo"
            "valid_lft forever preferred_lft forever"
        "inet6 ::1/128 scope host noprefixroute"
            "valid_lft forever preferred_lft forever"
---


    "2: enp2s0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc fq_codel state DOWN group default qlen 1000"
        "link/ether fc:34:97:4d:44:0c brd ff:ff:ff:ff:ff:ff"
---


    "3: wlp3s0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc noqueue state UP group default qlen 1000"
        "link/ether ec:2e:98:aa:7e:17 brd ff:ff:ff:ff:ff:ff"
        "inet 192.168.0.101/24 brd 192.168.0.255 scope global dynamic noprefixroute wlp3s0"
            "valid_lft 42901sec preferred_lft 42901sec"
        "inet6 2a01:e0a:839:ea40:a618:6a57:c840:b6ee/64 scope global dynamic noprefixroute"
            "valid_lft 86341sec preferred_lft 86341sec"
        "inet6 fe80::fb1c:61b3:2ade:1539/64 scope link noprefixroute"
            "valid_lft forever preferred_lft forever"
---


### **1. lo (Loopback) :**


    * Adresse IP : 127.0.0.1/8 (IPv4) et ::1/128 (IPv6).

    * État : L'interface est activée (UP) et fonctionnelle (LOWER_UP).

    * Adresse MAC : 00:00:00:00:00:00 (car il s'agit d'une interface virtuelle).
---


### **2. enp2s0 (Ethernet) :**


    * État : L'interface est désactivée (DOWN) et ne transporte pas de trafic (NO-CARRIER).

    * Adresse MAC : fc:34:97:4d:44:0c.
---


### **3. wlp3s0 (Wi-Fi) :**


    * État : L'interface est activée (UP) et fonctionnelle (LOWER_UP).

    * Adresse MAC : ec:2e:98:aa:7e:17.

    * Adresse IP : 192.168.0.101/24 (IPv4) et 2a01:e0a:839:ea40:a618:6a57:c840:b6ee/64 (IPv6).

    * Broadcast : 192.168.0.255.

    * État de l'adresse IP : La première adresse IP est attribuée dynamiquement (DHCP) et a une durée de validité spécifiée (42901sec).

    * Adresse IPv6 locale : fe80::fb1c:61b3:2ade:1539/64.
---

**Chaque section fournit des informations sur une interface réseau spécifique, notamment son nom, son état (activé ou désactivé), son adresse MAC, son adresse IP (le cas échéant), et d'autres détails pertinents. L'interface loopback (lo) est toujours présente et active, tandis que les interfaces câblées et sans fil peuvent être activées ou désactivées en fonction de la connectivité.**

---


## **Activer ou désactiver une interface réseau**

    "ip link set nomiInterface up # Activer"

    "ip link set nomInterface down # Désactiver"
---
**exemple :**

    "ip link set wlp3s0 up # Activer"

    "ip link set wlp3s0 down # Désactiver"
---

## **Ajouter ou supprimer une adresse ip d'un interface réseau**

    "sudo ip addr add nouvelleAdresseIp/masqueReseau dev nomInferface # Ajouter"

    "sudo ip addr del nouvelleAdresseIp/masqueReseau dev nomInferface # Supprimer"
---

**exemple :**

    "sudo ip addr add 192.168.0.1/24 dev nomInferface # Ajouter"

    "sudo ip addr del 192.168.0.1/24 dev nomInferface # Supprimer"
---


# **Routes**
---


**Sur Linux, la commande ip route est utilisée pour afficher et gérer la table de routage du système. C'est un ensemble de règles qui détermine comment les paquets réseau doivent être dirigés vers leur destination. Elle spécifie le chemin qu'un paquet doit prendre pour atteindre un réseau ou une adresse IP spécifique.**

---

## **Afficher la table de routage**

    "ip route show"

    "default via 192.168.0.254 dev wlp3s0 proto dhcp src 192.168.0.101 metric 600"
    "192.168.0.0/24 dev wlp3s0 proto kernel scope link src 192.168.0.101 metric 600"
---

**Dans mon cas, voici ma confiuration :**

## **1. Default Route (Route par défaut) :**

    * Destination : "default" indique que c'est la route par défaut, utilisée lorsque la destination n'est pas couverte par d'autres routes.

    * Via : "via 192.168.0.254" spécifie la passerelle par défaut à travers laquelle le trafic non destiné au réseau local sera dirigé. Dans mon cas, il s'agit de ma box internet.

    * Dev : "dev wlp3s0" indique que l'interface réseau utilisée pour cette route est wlp3s0.

    * Proto : "proto dhcp" signifie que cette route a été configurée automatiquement par le protocole DHCP (Dynamic Host Configuration Protocol).

    * Src : "src 192.168.0.101" spécifie l'adresse source utilisée lors de l'envoi de paquets via cette route. Dans mon cas, il s'agit de l'addresse ip local de mon ordinateur.

    * Metric : "metric 600" est une métrique attribuée à la route. la métrique est utilisée comme unindicateur de priorité pour déterminer quelle route est préférée lorsqu'il y a plusieurs routes disponibles pour atteindre une destination. Plus une metric est basse, plus sa priorité est élevée.
---


## **2. Route pour le réseau 192.168.0.0/24 :**

    * Destination : "192.168.0.0/24" spécifie l'adresse IP du réseau.

    * Dev : "dev wlp3s0" indique que cette route est accessible via l'interface réseau wlp3s0.
    
    * Proto : "proto kernel" indique que cette route a été ajoutée par le noyau.

    * Scope : "scope link" signifie que cette route est valable uniquement pour le réseau local.

    * Src : "src 192.168.0.101" spécifie l'adresse source utilisée lors de l'envoi de paquets via cette route.

    * Metric : "metric 600" est la métrique attribuée à la route.
---


**En résumé, cette deuxième ligne décrit la route spécifique pour le réseau local 192.168.0.0/24. Elle est utilisée pour diriger le trafic vers des hôtes situés sur le même réseau local, et elle est généralement configurée automatiquement par le noyau du système d'exploitation.**

---


## **Ajouter ou supprimer une route**

    "sudo ip route add ipDestination via ipPasserelle dev nomiInterface # Ajouter"

    "ip route delete ipDestination # Supprimer"
---


## **Changer la passerelle par défaut**

    "sudo ip route change default via nouvelleIpPasserelle"
---


## **Supprimer toutes les routes vers une destination**

    "sudo ip route flush ipDestination"
---


# **Fichier hosts**
---

**Le fichier hosts est un fichier texte utilisé pour résoudre les noms de domaine en adresses IP locales. Il est présent sur la plupart des systèmes d'exploitation, y compris Linux. La manipulation de ce fichier peut être utile pour configurer des résolutions DNS locales ou pour bloquer l'accès à certains sites web.**

---


## **Le fichier hosts se trouve dans le répertoire suivant :**

    "/etc/hosts"

**Ce fichier a une structure très simple, associant des adresses IP à des noms de domaine. Chaque entrée est généralement disposée sur une ligne, avec l'adresse IP suivie du nom de domaine.**

---

**Exemple :**

    "127.0.0.1 localhost"

    "192.168.1.2 monServeur.local"
---

**Dans cet exemple, la première ligne associe l'adresse IP127.0.0.1 au nom de domaine localhost, et la deuxième ligne associe l'adresse IP192.168.1.2 au nom de domaine monserveur.local.**


## **Cas d'utilisations pratiques**
---

## **Résolution Locale de Noms de Domaine**

    * Ajouter des entrées personnalisées dans le fichier hosts permet de résoudre des noms de domaine localement sans dépendre d'un serveur DNS. Cela peut être utile dans des environnements de développement ou de test.
---


## **Blocage de Sites Web**

    * En associant des adresses IP factices à des domaines spécifiques, le fichier hosts peut être utilisé pour bloquer l'accès à certains sites web. Par exemple, rediriger un site indésirable vers l'adresse IP 127.0.0.1 peut empêcher l'accès à ce site.
---


# **Commandes réseau**
---


## **Tester si un équipement réseau est connecté**

    "ping adresseWebOuIp"
---

**Cette commande est souvent utilisée pour obtenir le temps de latence en millisecondes ou encore l'adresse IP du site web en question. À propos des informations sur les sites web, nous pouvons récupérer divers enregistrements, dont les enregistrements whois sur le propriétaire du site :**

    "whois adresseWeb"
---

**Ou encore les divers enregistrements DNS du site en question :**

    "dig adresseWeb"
---