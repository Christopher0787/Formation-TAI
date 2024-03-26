# Notes


- **Attribution d'une ip à un vlan**
```cli
Switch(config)#int Vlan 20
Switch(config-if)#ip address 172.16.1.2 255.255.0.0
Switch(config-if)#no shut
Switch(config-if)#exit
Switch(config)#
```

- **Attribution ip à une vlan**
```cli
Router>enable
Router#
Router#configure terminal
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#interface GigabitEthernet0/0/0
Router(config-if)#ip address 192.168.3.1 255.255.255.0
Router(config-if)#ip address 192.168.3.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#
```

<img src="./Images/Capture-Packet-Tracer..png.png" alt="Capture Packet Tracer" width="100%" />

---

![Capture packet-tracer](./Images/Capture-Packet-Tracer.png)

---

```cli

Router>en
Router#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Router(config)#
```

---

- **Exemple schema mermaid**

```mermaid
graph TD;
    A[Cylindres 1 et 5] --> B(Bloc moteur);
    B --> C[Cylindres 2 et 6];
    C --> D[Cylindres 3 et 7];
    D --> E[Cylindres 4 et 8];
    E --> F{Arbre à cames};
    F --> G[Soupapes d'admission];
    F --> H[Soupapes d'échappement];
    I(Moteur V8) -->|Transmission| J;

```

