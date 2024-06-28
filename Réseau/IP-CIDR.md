# **IP, MASQUES ET CIDR :**
---


    * CIDR (Classless Inter-Domain Routing, c'est à dire sans classe). 

    * Vers 1990, le CIDR a remplacé lesclasses de réseaux, pour des raisons de saturation des tables de routage et pour obtenir une plus grande souplesse dans les adressages.


---


## **Voici un tableau récapitulatif des masques de sous-réseaux IPv4, en notation actuelle :**


| Masque de sous-réseau | Notation CIDR | IP Totales  |
|-----------------------|---------------|-------------|
| 255.0.0.0             | /8            | 16,777,216  |
| 255.128.0.0           | /9            | 8,388,608   |
| 255.192.0.0           | /10           | 4,194,304   |
| 255.224.0.0           | /11           | 2,097,152   |
| 255.240.0.0           | /12           | 1,048,576   |
| 255.248.0.0           | /13           | 524,288     |
| 255.252.0.0           | /14           | 262,144     |
| 255.254.0.0           | /15           | 131,072     |
| 255.255.0.0           | /16           | 65,536      |
| 255.255.128.0         | /17           | 32,768      |
| 255.255.192.0         | /18           | 16,384      |
| 255.255.224.0         | /19           | 8,192       |
| 255.255.240.0         | /20           | 4,096       |
| 255.255.248.0         | /21           | 2,048       |
| 255.255.252.0         | /22           | 1,024       |
| 255.255.254.0         | /23           | 512         |
| 255.255.255.0         | /24           | 256         |
| 255.255.255.128       | /25           | 128         |
| 255.255.255.192       | /26           | 64          |
| 255.255.255.224       | /27           | 32          |
| 255.255.255.240       | /28           | 16          |
| 255.255.255.248       | /29           | 8           |
| 255.255.255.252       | /30           | 4           |
| 255.255.255.254       | /31           | 2           |
| 255.255.255.255       | /32           | 1           |


---

    * Une adresse IPv4 est codée sur 32 bits, idem pour un masque de sous-réseau.

    * Ces 32 bits sont des 0 et des 1 : du binaire.

    * En premier lieu, nous allons aborder la conversion du décimal (IP ou masque) vers le binaire, et l'inverse bien sûr.

    * Etant donné qu'une IP ou un masque est codé sur 32 bits, qu'il y a un point entre chaque nombre (ou chiffre), on a donc 4 x 8 bits.


---


### **Exemple pour une adresse IP (inventée) : 189.54.87.124**


    * Il y aura donc 8 bits pour 189, 8 bits pour 54, 8 bits pour 87 et idem pour 124 ; soit 32 bits au total.

    * Voici une méthode de calcul, avec comme aide le chiffre 2, car en binaire on compte ainsi :



    * Comme on peut le voir dans le tableau précédent, quand on lit de gauche à droite le binaire, on lit les nombres (ou chiffres) du plus grand au plus petit.

    * Pour convertir du décimal vers le binaire, notons bien qu'on ne peut utiliser une seule fois un nombre obtenu avec la base 2.


---


### **Exemple : pour obtenir le nombre 129, c'est 27 + 20**


    * c'est à dire 128 + 1. Cela ne peut pas être 26 + 26 + 20

    * ou d'autres combinaisons, car le même nombre ne peut être utilisé qu'une seule fois, pour que le binaire fonctionne.

    * En convertissant en binaire, il n'y a donc qu'une seule possibilité.

    * 129 donne donc : 27 + 20

    * Dans un tableau, on peut voir :



### **On obtient donc pour le nombre 129 décimal, en binaire : 10000001**


    * Pour l'adresse IP dont j'ai parlé tout à l'heure (189.54.87.124), voici le calcul et résultat :

    * 189 = 128 + 32 + 16 + 8 + 4 + 1 = 27 + 25 + 24 + 23 + 22 + 20 En binaire, cela donne : 10111101

    * 54 = 32 + 16 + 4 + 2 = 25 + 24 + 22 + 21 En binaire, cela donne : 00110110

    * 87 = 64 + 16 + 4 + 2 + 1 = 26 + 24 + 22 + 21 + 20 En binaire, cela donne : 01010111

    * 124 = 64 + 32 + 16 + 8 + 4 = 26 + 25 + 24 + 23 + 22 En binaire, cela donne : 01111100


---


    * Au final pour l'IP 189.54.87.124 on obtient : 10111101.00110110.01010111.01111100

    * A l'inverse, si on a une IP au format binaire, voici de quoi la convertir en décimal :

    * Une autre IP : 01010011.10011010.10110111.01100100

    * Avec le tableau de correspondance (ou de mémoire) de base 2, on peut convertir :

    * 01010011 → 26 + 24 + 21 + 20 = 64 + 16 + 2 + 1 = 83

    * 10011010 → 27 + 24 + 23 + 21 = 128 + 16 + 8 + 2 = 154

    * 10110111 → 27 + 25 + 24 + 22 + 21 + 20 = 128 + 32 + 16 + 4 + 2 + 1 = 183

    * 01100100 → 26 + 25 + 22 = 64 + 32 + 4 = 100

    * Ainsi l'IP binaire 01010011.10011010.10110111.01100100 veut dire en décimal : 83.154.183.100

    * Pour aller plus loin, revenons au tableau de départ, avec la notation CIDR, la liste des masques corresp * ondants et le nombre d'adresses IP disponible pour chaque masque de sous-réseau.

    * Comme les IPv4 sont codées sur 32 bits, ainsi que les masques de sous-réseaux, on va pouvoir facilement calculer un masque en fonction du nombre de bits que l'on alloue, et inversement.


---


### **Exemples : quand on parle d'un réseau /1 (notation CIDR), c'est un masque 128.0.0.0**


    * Pour un réseau /8 c'est un masque 255.0.0.0

    * Pour un réseau /24 c'est un masque 255.255.255.0


---


### **Pour la conversion, voici comment procéder :**


    * On active autant de bits à 1 que le nombre après le /


---


### **En activant les bits à 1 de gauche à droite, avec un /1 cela donne :**


    * 10000000.00000000.00000000.00000000

    * Avec ce code binaire, on obtient donc :

    * 10000000 → 27 = 128 00000000

    * → 0


---


### **Avec un réseau /1 on obtient donc un masque : 128.0.0.0**


    * Pour obtenir le nombre d'adresses IP, on va se servir du nombre de bits aussi :

    * Avec un /1 comme l'adresse est codée sur 32 bits, il reste 31 bits pour les hôtes : 2^31 = 2 147 483 648 IP

    * En réalité, il y a 2 IP "en moins" car il y a une IP pour le réseau, et une autre pour le broadcast.

    * Il y a donc 2 adresses IP réservées dans un réseau et donc on ne peut pas les attribuer à un périphérique.


---


### **Autre exemple, avec un /24 largement utilisé dans des réseaux de petite taille :**


    * En activant les bits à 1 de gauche à droite, avec un /24 cela donne : 11111111.11111111.11111111.00000000

    * Avec ce code binaire, on obtient donc :

    * 11111111 → 27 + 26 + 25 + 24 + 23 + 22 + 21 + 20 = 128 + 64 + 32 + 16 + 8 + 4 + 2 + 1 = 255 00000000

    * → 0


---


### **Avec un réseau /24 on obtient donc un masque : 255.255.255.0**


    * Pour obtenir le nombre d'adresses IP, on va se servir du nombre de bits aussi :

    * Avec un /24 comme l'adresse est codée sur 32 bits, il reste 8 bits : 28 = 256 IP

    * Idem là aussi, il y a 2 IP "en moins" car il y a une IP pour le réseau, et une autre pour le broadcast.

    * Avec un /24 on a donc 254 IP utilisables.

    * /24 → Masque 255.255.255.0 → 256 IP au total → 254 IP utilisables

    * /23 → Masque 255.255.254.0 → 512 IP au total → 510 IP utilisables

    * Pour mieux illustrer ce fonctionnement, j'ai ajouté une colonne au tableau de départ.


---


## **Voici un tableau récapitulatif des masques de sous-réseaux IPv4, en notation actuelle + avec code binaire :**


| Masque de sous-réseau | Notation CIDR | IP Totales  | Code Binaire                        |
|-----------------------|---------------|-------------|-------------------------------------|
| 255.0.0.0             | /8            | 16,777,216  | 11111111.00000000.00000000.00000000 |
| 255.128.0.0           | /9            | 8,388,608   | 11111111.10000000.00000000.00000000 |
| 255.192.0.0           | /10           | 4,194,304   | 11111111.11000000.00000000.00000000 |
| 255.224.0.0           | /11           | 2,097,152   | 11111111.11100000.00000000.00000000 |
| 255.240.0.0           | /12           | 1,048,576   | 11111111.11110000.00000000.00000000 |
| 255.248.0.0           | /13           | 524,288     | 11111111.11111000.00000000.00000000 |
| 255.252.0.0           | /14           | 262,144     | 11111111.11111100.00000000.00000000 |
| 255.254.0.0           | /15           | 131,072     | 11111111.11111110.00000000.00000000 |
| 255.255.0.0           | /16           | 65,536      | 11111111.11111111.00000000.00000000 |
| 255.255.128.0         | /17           | 32,768      | 11111111.11111111.10000000.00000000 |
| 255.255.192.0         | /18           | 16,384      | 11111111.11111111.11000000.00000000 |
| 255.255.224.0         | /19           | 8,192       | 11111111.11111111.11100000.00000000 |
| 255.255.240.0         | /20           | 4,096       | 11111111.11111111.11110000.00000000 |
| 255.255.248.0         | /21           | 2,048       | 11111111.11111111.11111000.00000000 |
| 255.255.252.0         | /22           | 1,024       | 11111111.11111111.11111100.00000000 |
| 255.255.254.0         | /23           | 512         | 11111111.11111111.11111110.00000000 |
| 255.255.255.0         | /24           | 256         | 11111111.11111111.11111111.00000000 |
| 255.255.255.128       | /25           | 128         | 11111111.11111111.11111111.10000000 |
| 255.255.255.192       | /26           | 64          | 11111111.11111111.11111111.11000000 |
| 255.255.255.224       | /27           | 32          | 11111111.11111111.11111111.11100000 |
| 255.255.255.240       | /28           | 16          | 11111111.11111111.11111111.11110000 |
| 255.255.255.248       | /29           | 8           | 11111111.11111111.11111111.11111000 |
| 255.255.255.252       | /30           | 4           | 11111111.11111111.11111111.11111100 |
| 255.255.255.254       | /31           | 2           | 11111111.11111111.11111111.11111110 |
| 255.255.255.255       | /32           | 1           | 11111111.11111111.11111111.11111111 |

---