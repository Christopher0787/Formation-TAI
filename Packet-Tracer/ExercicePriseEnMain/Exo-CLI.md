# Prise en main de l'interface CLI

## Exercice 1 : Configuration du CLI 

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

---

## Exercice 2 : des modes d'execution sur un switch cisco

** Materiel requi **

- Un comutateur (Switch)

![Topologie Exercice 1](../img/Exo-2-topo.png)

- **Mode utilisateur :**
```cli
Switch>
```

- **Mode Privilegier :**
```cli
Switch>en	
Switch#
```	

- **Retour mode utilisateur :**
Commande pour quittere le mode privilegier
```cli	
Switch#disable
Switch>
```	

---

## Exercice 3 : Entrer et sortie du mode de configuration globale sur un routeur cisco

** Materiel requi **

- Un Routeur
