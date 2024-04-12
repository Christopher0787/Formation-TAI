# **Révision Adressage IP**

4 Octets
32 Bits
1 Octets = 8 Bits
192.168.0.1 = décimal .t
Ipv6 = alphanumérique hexadécimal


32 - 20 = 12  : 2^ 12 = 4 096 = calculer le nombre adresse réseau 


- **CORP   19.168.0.0/24**

A (60) /26 = 192.168.0.0 - 192.168.0.63 | 4 IP
B (30) /27 = 192.168.0.64 - 192.168.0.96  | 2 IP
C (10) /28 = 192.168.0.97 - 192.168.0.113 | 6 IP
D (2)   /30 =  192.168.0.114 - 192.168.0.118 | 2 IP
    • PERTE = 14 IP 

- **CORP  10.0.0.0/16**
**10.0 (Réseau) | 0.0 (Hôtes)**

A (1000) /22= 10.0.0.0 - 10.0.3.255 | 24 IP
B (500) /23 = 10.0.4.0  -  10.0.5.255 | 12 IP
C (200) /24 = 10.0.6.0 - 10.0.6.255 | 56 IP
D (100) /25 = 10.0.7.0 - 10.0.7.127 | 28 IP
    • PERTE = 120 IP

- **CORP 10.1.0.0/16 - 65536 IP**
**10.1 (Réseau) | 0.0 (Hôtes)**

A (2000) /21 = 10.1.0.0 - 10.1.7.255 | 48 IP
B (500) /23 = 10.1.8.0 - 10.1.9.255 | 12 IP
C (250) /24 = 10.1.10.0 - 10.1.10.255 | 6 IP


- **CORP 10.10.0.0/16 - 65536 IP**
**10.10 (Réseau) | 0.0 (Hôtes)**

A (800)  /22 = 10.10.0.0 - 10.10.3.255 | 224 IP
B (400)  /23 = 10.10.4.0 - 10.10.5.255 | 112 IP
C (200) /24 = 10.10.6.0 - 10.10.6.255 | 56 IP
D (100) /25 = 10.10.7.0 - 10.10.7.127 | 28 IP
E (50) /26 = 10.10.7.128 - 10.10.7.191 | 14 IP
F (10) /28 = 10.10.7.192 - 10.10.7.207 | 6 IP

- **CORP 172.31.0.0/18  - 16384 IP**
**172.31 (Réseau) | 0.0 (Hôtes)**

A (600) /22 = 172.31.0.0 - 172.31.2.89 
B (300) /23 = 172.31.2.90 - 172.34.3.135
C (150)
D (75)



FLSM = Fixed Length Sub Mask = ce qu'on na a la maison
VLSM = Variable Length Sub Mask = fournisseur internet

FAI = Fournisseur accès internet



## **Le nombre d'échange sur la plage DHCP :**

- D = DISCOVER

- O = OFFER

- R = REQUEST

- A = ACKNOWLEDGE

---
