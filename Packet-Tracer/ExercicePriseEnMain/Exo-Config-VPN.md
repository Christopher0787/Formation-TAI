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