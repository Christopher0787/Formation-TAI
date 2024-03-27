# Exercice les Vlan avec cisco Packet Tracer

## Exercice 1 : Vérification du Vlan par défaut

**Model switch 2960**

![Topologie Exercice 1](../img/Exo-1-Vlan-topo.png)

```cli
Switch>
Switch>show Vlan brief

VLAN Name                             Status    Ports
---- -------------------------------- --------- -------------------------------
1    default                          active    Fa0/1, Fa0/2, Fa0/3, Fa0/4
                                                Fa0/5, Fa0/6, Fa0/7, Fa0/8
                                                Fa0/9, Fa0/10, Fa0/11, Fa0/12
                                                Fa0/13, Fa0/14, Fa0/15, Fa0/16
                                                Fa0/17, Fa0/18, Fa0/19, Fa0/20
                                                Fa0/21, Fa0/22, Fa0/23, Fa0/24
                                                Gig0/1, Gig0/2
1002 fddi-default                     active    
1003 token-ring-default               active    
1004 fddinet-default                  active    
1005 trnet-default                    active    
Switch>
```

---

## Exercice 2 : Création d'un Vlan de Donner 

**Model switch 2960**

![Topologie Exercice 2](../img/Exo-2-Vlan-topo.png)

```cli
Switch>
Switch>en
Switch#conf t
Switch(config)#Vlan 10
Switch(config-vlan)#name Utilisateur
Switch(config-vlan)#exit
Switch(config)#exit
Switch#
Switch#show Vlan brief

VLAN Name                             Status    Ports
---- -------------------------------- --------- -------------------------------
1    default                          active    Fa0/1, Fa0/2, Fa0/3, Fa0/4
                                                Fa0/5, Fa0/6, Fa0/7, Fa0/8
                                                Fa0/9, Fa0/10, Fa0/11, Fa0/12
                                                Fa0/13, Fa0/14, Fa0/15, Fa0/16
                                                Fa0/17, Fa0/18, Fa0/19, Fa0/20
                                                Fa0/21, Fa0/22, Fa0/23, Fa0/24
                                                Gig0/1, Gig0/2
10   Utilisateur                      active    
1002 fddi-default                     active    
1003 token-ring-default               active    
1004 fddinet-default                  active    
1005 trnet-default                    active    
Switch#
```

---

## Exercise 3 : Changement du Vlan natif sur un port trunk

**Model switch 2960**

![Topologie Exercice 3](../img/Exo-3-Vlan-topo.png)

```cli
Switch>
Switch>en
Switch#conf t
Switch(config)#int gigabitEthernet0/1
Switch(config-if)#switchport mode trunk
Switch(config-if)#switchport trunk native Vlan 99
Switch(config-if)#exit
Switch(config)#exit
Switch#
Switch#show interface trunk
Switch#
```

---

