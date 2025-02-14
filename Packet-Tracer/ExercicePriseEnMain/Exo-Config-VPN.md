# Configuration d'un VPN

## Exercice 1 : Accés au mode de configuration

**Model router 4331**

![Topologie Exercice 1](../img/Exo-1-VPN-topo.png)

```cli
Router>
Router>en
Router#conf t
Router(config)#
```

---

## Exercice 2 : Définition d'un nom d'hôte

**Model router 4321**

![Topologie Exercice 2](../img/Exo-2-VPN-topo.png)

```cli
Router>
Router>en
Router#conf t
Router(config)#hostname RouteurVPN
RouteurVPN(config)#
```

---

## Exercice 3 : Configuration d'un Mot de Passe pour un mode privilégier

**Model router 4331**

![Topologie Exercice 3](../img/Exo-3-VPN-topo.png)


```cli
Router>
Router>en
Router#conf t
Router(config)#enable secret monMotDePasse
Router(config)#exit
Router#
Router#disable
Router>en
Password: 
Router#
```
---

## Exercice 4 : Configuration de SSH

**Model router 4321**

![Topologie Exercice 4](../img/Exo-4-VPN-topo.png)

```cli
Router>
Router>en
Router#conf t
Router(config)#ip domain-name mondomaine.com
Router(config)#hostname RouteurSSH
RouteurSSH(config)#crypto key generate rsa
RouteurSSH(config)#ip ssh version 2
*Mar 1 0:3:48.512: %SSH-5-ENABLED: SSH 2 has been enabled
RouteurSSH(config)#
RouteurSSH(config)#exit
RouteurSSH#
RouteurSSH#show ip ssh
SSH Enabled - version 2.0
RouteurSSH#
```
---

## Exercice 5 : Création d'un utilisateur Administrateur

**Model router 4321**

![Topologie Exercice 5](../img/Exo-5-VPN-topo.png)

```cli
Router>
Router>en
Router#conf t
Router(config)#username admin privilege 15 secret monMotDePasse
Router(config)#
```

---

## Exercice 6 : Configuration des Mot de passe pour l'accés console

**Model router 4321**

![Topologie Exercice 6](../img/Exo-6-VPN-topo.png)

```cli
Router>
Router>en
Router#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#line console 0
Router(config-line)#password monmotdepasee
Router(config-line)#login
Router(config-line)#
```

---

## Exercice 7 : Configuration des Mot de passe pour pour les lignes VTY

**Model router 4321**

![Topologie Exercice 7](../img/Exo-7-VPN-topo.png)

```cli
Router>
Router>en
Router#conf t
Router(config)#line vty 0 15
Router(config-line)#transport input ssh 
Router(config-line)#login local
Router(config-line)#
```

---

## Exercice 8 : Activation du chiffrement des mots de passe

**Model router 4321**

![Topologie Exercice 8](../img/Exo-8-VPN-topo.png)


```cli
Router>
Router>en
Router#conf t
Router(config)#service password-encryption
Router(config)#exit
Router#
Router#show running-config
Router#
```

---

## Exercice 9 : Configuration du bagnière MOTD (Message of the Day)

**Model router 4321**

![Topologie Exercice 9](../img/Exo-9-VPN-topo.png)

```cli
Router>
Router>en
Router#conf t
Router(config)#banner motd #Message d'avertissement#
Router(config)#exit
Router#
Router#exit
Message d'avertissement
Router>
```

---

## Exercice 10 : Sauvegard de la configuration dans la NVRAM

**Model router 4321**

![Topologie Exercice 10](../img/Exo-10-VPN-topo.png)

```cli
Router>
Router>en
Router#conf t
Router(config)#exit
Router#
Router#copy running-config startup-config
Router#show startup-config
```

---

