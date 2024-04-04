# **Déploiement MDT (Microsoft Tool)**

## **Sur le premier serveur installer** 
- Active Directory (AD DS)
- DHCP
- DNS

## **En premier lieu configurer Active Directory**

- Cliquer sur Active Directory 
- Autre (Promouvoir ce serveur en contrôler de domaine)
- Ajouter une nouvelle forêt 
- Nom de domaine racine : deploiment.local
- Suivant
- Mot de passe différent de la session
- Suivant 
- Suivant
- Suivant
- Installer
- Redémarrage de la session


## **En deuxième lieu configurer DHCP** 

- Outil
- DHCP
- Deloure serveur
- IPv4 Clique droit 
- Nouvelle étendue
- Suivant
- Nom de l'étendue (Déploiement)
- Suivant
- IP de début 192.168.1.1
- IP de fin 192.168.1.15
- Suivant
- Suivant
- Cocher la case (OUI je veux configurer ces option maintenant)
- Suivant
- Mettre la pacerelle 192.168.1.14
- Suivant
- Domaine parent : Deploiment.local
- Suivant
- Suivant
- Suivant
- Terminer

## **Configurer les option détendue**

- Clique droit configurer les option
- Cocher la case 066 
- Mettre l'adresse de pacerelle 192.168.1.14
- OK
- Cocher la case 067
- Mètre le chemin boot\x64\wdsnbp.com
- OK

- Rajouter l'option 060
- Clic droit sur Win
- Ouvrir PowerShell Admin
- Add-DhcpServeurv4OptionDefinition -ComputerNameSRV-DHCP-ADDS -Name PXEClient -Description "PXE Support" -OptionId 060 -Type String
- Dans option détendue 
- Clique droit 
- Configurer option
- Cocher la case 060
- OK

## **Déclaration des classe de fournisseur**

**Ligne de commande**

- $DhcpServerName = "SRV-DHCP-ADDS"
- $PxeServerIp = "192.168.1.2"
- $Scope = "192.168.1.0"
- Add-DhcpServerv4Class -ComputerName $DhcpServerName -Name "PXEClient - UEFI x64" Type Vendor -Data "PXEClient:arch:00007" -Description "PXEClient:arch:00007" 
- Add-DhcpServerv4Class -ComputerName $DhcpServerName -Name "PXEClient - UEFI x86" Type Vendor -Data "PXEClient:arch:00006" -Description "PXEClient:arch:00006" 
- Add-DhcpServerv4Class -ComputerName $DhcpServerName -Name "PXEClient - BIOS x86 et x64" Type Vendor -Data "PXEClient:arch:00000" -Description "PXEClient:arch:00000"

- Dans Stratégies
- Clique droit
- Nom de la Stratégies : PXEClient - BIOS x86 et x64
- Description : PXEClient - BIOS x86 et x64
- Suivant
- Ajouter
- Critère = Classe de fournisseur
- Opérateur = Est égal à
- Valeur = PXEClient - BIOS x86 et x64
- Ajouter
- OK
- Suivant
- Suivant
- Terminer

- Clic droit sur le Nom de la stratégies
- Propriété
- Option
- Cocher la case 066 
- Mettre l'adresse de pacerelle : 192.168.1.2
- OK
- Côcher la case 067
- Mètre le chemin : boot\x64\wdsnbp.com
- OK


## **Assistant Configuration de stratégie DHCP**

- Nom de la Stratégies : PXEClient - UEFI x86
- Description : PXEClient - UEFI x86
- Suivant
- Et  Ou
- Critère : Classe de fournisseur
- Opérateur : Est égal à
- Valeur : PXEClient - UEFI x86
- Suivant
- Ajouter
- OK
- Suivant
- Cocher la case 060 Valeur : PXEClient
- Suivant
- Cocher la case 066 Valeur : 192.168.1.2
- Suivant
- Cocher la case 067 Valeur : boot\x86\wdsmgfw.efi
- Suivant


- Nom de la Stratégies : PXEClient - UEFI x64
- Description : PXEClient - UEFI x64
- Suivant
- Ajouter
- Critère : Classe de fournisseur
- Opérateur : Est égalà
- Valeur :  PXEClient - UEFI x64
- Ajouter
- OK
- Suivant
- Cocher la case 060 Valeur : PXEClient
- Suivant
- Cocher la case 066 Valeur : 192.168.1.2
- Suivant
- Cocher la case 067 Valeur : boot\x64\wdsmgfw.efi
- Suivant
- Terminer

---