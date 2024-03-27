# Configuration du CLI 

** Materiel requi **

- Un comutateur
- 2 PC
- Relier avec un cable les PC au comutateur (Switch)
- Cliquer sur le switch aller sur CLI

![Topologie Exercice 1](../img/Exo-1-topo.png)

```cli
Switch>en
Switch#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Switch(config)#Vlan 10
Switch(config-vlan)#int Vlan 10
Switch(config-if)#exit
Switch(config)#int Fa0/1 
Switch(config-if)#switchport mode access
Switch(config-if)#switchport access Vlan 10
Switch(config-if)#
```
