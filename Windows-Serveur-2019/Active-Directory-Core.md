# **Active Directory Core**

## **Création et gestion d'utilisateur Active Directory avec powershell**

    - Powershell.exe
    - Set-ItemProperty -Path "HKLM:\Software\Microsoft\Windows NT\CurrentVersion\WinLogon" -Name Shell -Value "Powershell.exe"
    - Get-NetIPConfiguration
    - New-NetIPAddress -InterfaceIndex 6 -IPAddress 192.168.1.100 -Prefixlength 24 -DefaultGateway 192.168.1.1
    - Install-windowsFeature AD-Domain-Service, RSAT-AD-AdminCenter
    - $UserPassword = ConvertTo-SecureString "Password123" -AsPlainText -Force Set-ADAccountPassword -Identity "JohnDoe" -NewPassword $UserPassword
    - Set-ADAccountPassword -Identity "JohnDoe" -NewPassword $UserPassword
    - Enable-ADAccount -Identity "JohnDoe"
    - Get-LocalUser
    - New-ADOrganizationalUnit -Name "Utilisateur" -Path "DC=tai, DC=local"
    - New-ADUser -Name "JaneDoe" -GivenName "Jane" -Surname "Doe" -SamAccountName "JaneDoe" -UserPrincipalName "jane.doe@tai.local" -Path "OU=Utilisateurs, DC=tai, DC=local" -AccountPassword ($UserPassword) -Enabled $true.
    - Set-ADUser "JaneDoe" -Title "Manager" -OfficePhone "0475889944".
    - Set-ADAccountPassword "JaneDoe" -Reset -NewPassword (ConvertTo-SecureString -AsPlainText "NouveauMot2Passe" -Force).
    - Get-ADUser -Filter * -SearchBase "OU=Utilisateurs, DC=tai, DC=local".
    - Get-ADUser -Filter 'EmailAddress -notlike "*"' -Properties EmailAddress.
    - Get-ADUser -Filter "*" -Properties Name, GivenName, SamAccountName, UserPrincipalName | Select-Object Name, GivenName, SamAccountName, UserPrincipalName | Export-Csv "C:\Windows\system32\exported_users.csv" -NoTypeInformation.
    - cat exported_users.csv.


## **Gestion d'Active Directory avec powershell**

    -  Get-ADUser -Identity JohnDoe -Properties DisplayName, SamAccountName, Department | Select-Object DisplayName, SamAccount, Department
    -  Get-ADUser -Filter 'Surname -like "Doe"' | Select-Object Name
    -  Get-ADUser -Filter 'Department -eq "Utilisateur"' | Select-Object Name, SameAccountName, Department | Export-Csv -Path "Utilisateurs_Users.csv" -NoTypeInformation
    -  Cat Utilisateur_Users.csv.
    -  Get-ADUser -Filter 'PasswordNeverExpires -eq $true'  | Select-Object Name
    -  Get-ADUser -Filter 'Enabled -eq $false' | Select-Object Name
    - $LastMonth = (Get-Date).AddMonths(-1)
    - Get-ADUser -Filter 'whenCreated -ge $LastMonth' | Select-Object Name
    - $FeatureName = "RSAT.ActiveDirectory.DS-LDS.Tools~~~~0.0.1.0"
    - if (-not(Get-WindowsCapability -Online | Where-Object Name -like $FeatureName)) {Add-WindowsCapability -Online -Name $FeatureName}
    - Get-ADUser -Filter * -Properties LastLogonDate | Select-Object Name, LastLogonDate | Export-Csv -Path "UserLastLogon.csv" -NoTypeInformation
    
    Import-Module ActiveDirectory
    $Users = Get-ADUser -Filter * -Properties "PasswordLastSet", "PasswordNeverExpires"
    $Users | Where-Object {$_.PasswordNeverExpires -ed $False -and ($_.PasswordLastSet).AddDays(90) -lt (Get-Date).AddDays(7)} | Select-Object Name
    
    $CurrentDate = Get-Date
    $ExpireSoon = $CurrentDate.AddDays(5)
    Get-ADUser -Filter * -Properties "msDS-UserPasswordExpiryTimeComputed" |
    Where-Object { [datetime]::FromFileTime($_."msDS-
    UserPasswordExpiryTimeComputed") -lt $ExpireSoon } |
    Select-Object Name
    
    - Get-ADUser -Identity "JaneDoe" -Properties * | ConvertTo-HTML | Out-File "UserInfo.html"
    $Date = (Get-Date).AddDays(-90)
    Get-ADUser -Filter {LastLogonTimestamp -lt $Date} -Properties LastLogonTimestamp | ForEach-Object { Disable-ADAccount -Identity $_.SamAccountName}
    
    New-ADOrganizationalUnit -Name "RH" -Path "DC=tai, DC=local"
    New-ADOrganizationalUnit -Name "Utilisateurs" -Path "DC=tai, DC=local"
    New-ADOrganizationalUnit -Name "RH" -Path "DC=tai, DC=local"
    New-ADOrganizationalUnit -Name "IT" -Path "DC=tai, DC=local"
    New-ADOrganizationalUnit -Name "Finance" -Path "DC=tai, DC=local"
    New-ADOrganizationalUnit -Name "Ordinateurs" -Path "DC=tai, DC=local"
    New-ADOrganizationalUnit -Name "Noobies" -Path "DC=tai, DC=local"
    New-ADOrganizationalUnit -Name "ScuderiaFerrari" -Path "DC=tai, DC=local"
    
    - New-ADGroup -Name "Groupe RH" -GroupScope Global -Path "OU=RH, DC=tai, DC=local"
    New-ADGroup -Name "Groupe RH" -GroupScope Global -Path "OU=RH, DC=tai, DC=local"
    New-ADGroup -Name "Groupe IT" -GroupScope Global -Path "OU=IT, DC=tai, DC=local"
    New-ADGroup -Name "Groupe Finance" -GroupScope Global -Path "OU=Finance, DC=tai, DC=local"
    - Remove-ADGroup -Identity "Groupe IT"
    
    New-ADUser -Name "Utilisateur1" -GivenName "Utilisateur" -Surname "1" -SamAccount "Utilisateur1" -UserProfilName "utilisateur1@tai.local -Path OU=RH, DC=tai, DC=local" -AccountPassword (ConvertTo-String "P@assw0rd" -AsPlainText -Force) -Enabled $true 
    
    New-ADUser -Name "Utilisateur2" -GivenName "Utilisateur" -Surname "2" -SamAccount "Utilisateur2" -UserProfilName "utilisateur2@tai.local -Path OU=IT, DC=tai, DC=local" -AccountPassword (ConvertTo-String "P@assw0rd" -AsPlainText -Force) -Enabled $true
    
    New-ADUser -Name "Utilisateur1" -GivenName "Utilisateur" -Surname "3" -SamAccount "Utilisateur3" -UserProfilName "utilisateur3@tai.local -Path OU=Finance, DC=tai, DC=local" -AccountPassword (ConvertTo-String "P@assw0rd" -AsPlainText -Force) -Enabled $true 
    
    New-ADUser -Name "Utilisateur2" -GivenName "Utilisateur" -Surname "4" -SamAccount "Utilisateur4" -UserProfilName "utilisateur4@tai.local -Path OU=Ordinateurs, DC=tai, DC=local" -AccountPassword (ConvertTo-String "P@assw0rd" -AsPlainText -Force) -Enabled $true
    
    New-ADUser -Name "Utilisateur5" -GivenName "Utilisateur" -Surname "5" -SamAccount "Utilisateur1" -UserProfilName "utilisateur5@tai.local -Path OU=ScuderiaFerrari, DC=tai, DC=local" -AccountPassword (ConvertTo-String "P@assw0rd" -AsPlainText -Force) -Enabled $true 
    
    Set-ADUser Utilisateur1 -Title "Manager" -OfficePhone "061122334455"
    
    Set-ADAccountPassword Utilisateur1 -NewPassword (ConvertTo-SecureString -AsPlainText "M02P@$$€" -Force)
    Move-ADObject -Identity "CN=Utilisateur1, OU=RH, DC=tai, DC=local" -TargetPath "OU=IT, DC=tai, DC=local"
    Get-ADUser -Filter 'Name -like "Utilisateur*"'
    
    Search-ADAccount -AccountInactive -ComputersOnly -TimeSpan 30
    
    Get-ADGroup -Filter * | Where-Object {(Get-ADGroupMember $_.DistinguishedName).Count -eq 0}
    New-Item -ItemType Directory -Path "C:\ADReports"
    
    Get-ADUser -Filter * -Properties * | Select-Object Name, SamAccountName, Department | Export-Csv -Path "C:\ADReports\AllUser.csv" -NoTypeInformation
    Cat  C:\ADReports\AllUser.csv
    
    Search-ADAccount -AccountInactive -UserOnly -TimeSpam 90 | Export-Csv -Path "C:\ADReports\InactiveUsers.csv" -NoTypeInformation
    Cat C:\ADReports\InactiveUsers.csv
    
    $DaysInactive = 90
    $InactiveDate = (Get-Date).AddDays(-$DaysInactive)
    $ExportPath = "C:\ADReports\InactiveUsers.csv"
    
    $InactiveUsers = Get-ADUser -Filter {LastLogonTimestamp -lt $InactiveDate -and Enabled -eq $true} -Properties LastLogonTimestamp, Name, SamAccountName
    
    # Nombre de jours d'inactivité
    $DaysInactive = 90
    
    # Date limite d'inactivité (90 jours avant aujourd'hui)
    $InactiveDate = (Get-Date).Adddays(-$DaysInactive)
    
    # Chemin d'exportation pour les comptes désactivés
    $ExportPath = "C:\ADReports\InactiveUsers.csv"
    
    # Obtenir tous les utilisateurs AD qui n'ont pas été connectés depuis
    $DaysInactive
    $InactiveUsers = Get-ADUser -Filter {LastLogonTimestamp -lt $InactiveDate -
    and Enabled -eq $true} -Properties LastLogonTimestamp, Name, SamAccountName
    
    # Désactiver et exporter les utilisateurs inactifs
    $InactiveUsers | ForEach-Object {
    # Désactiver le compte utilisateur
    Disable-ADAccount -Identity $_.SamAccountName
    
    # Exporter les détails de l'utilisateur désactivé
    $_ | Select-Object Name, SamAccountName, @{Name="LastLogonDate";
    Expression={[DateTime]::FromFileTime($_.LastLogonTimestamp)}} | Export-Csv -
    Path $ExportPath -NoTypeInformation -Append
    }
    
    Write-Host "Les comptes utilisateurs inactifs ont été désactivés et leurs
    informations exportées vers $ExportPath"
    Cat C:\ADReports\InactiveUsers.csv.
    
    # Crée une saisie de mot de passe sécuriser
    $NewPassword = Read-Host "Entrez un nouveau mot de passe" -AsSecureString
    
    # Réinitialisation de mot de passe utilisateur avec confirmation
    $Username = "JohnDoe"
    $Confirmation = Read-Host "Etes vous sûr de vouloir réinitialier le mot de passe, pour $Username ? (O/N)"
    if ($Confirmation -eq "O") {$NewPassword = Read-Host "Entrez un nouveau mot de passe pour $Username" -AsSecureSring} Set-ADAccountPassword $Username -Reset -NewPassword -PassThru
    
    # Forcer l'utilisateur à changer le mot de passe a la prochaine connexion
    Set-ADUser -Identity "JohnDoe" -ChangePasswordAtLogon $true
    
    # Combiner la réinitialisation de mot de passe a la prochaine connexion 
    $NewPassword = Read-Host "Entrez un nouveau mot de passe" -AsSecureString
    Set-ADAccountPassword JohnDoe -NewPassword $NewPassword -Reset -PassThru | Set-ADUser -ChangePasswordAtLogon $true
    
    # Vérifier la date de la dernière modification de mot de passe
    Get-ADUser JohnDoe -Properties * | select name, PasswordLastSet
    
    # Surveiller les évènements de réinitialisation de mot de passe dans un journal de sécurité
    Get-WinEvent -FilterHashtable @{LogName="Security";ID=4724} | Where-Object {$_.Properties[1].value -eq "JohnDoe"}
    
    # Calculer la date d'expiration de mot de passe d'un utilisateur
    Get-ADUser JohnDoe -Properties msDS-UserPasswordExpiryTimeComputed | Select-Object @{Name="ExpirationDate"; Expression= {[datetime]::FromFileTime($_.msDS-UserPasswordExpiryTimeComputed)}}
    
    ## Création de la Structure des Unités Organisationnelles (OU) dans Active Directory avec PowerShell
    
    # Création d'une OU principal pour un nouveau bureau
    New-ADOrganizationalUnit -Name "Dallas" -Path "DC=tai, DC=local" -Description "Dallas new office"
    
    # Ajout de conteneurs imbriquer sous la nouvelle OU
    $OUS = @("Admin", "Ordinateur", "Contact", "Groupe", "Serveur", "Service comptabilité", "Utilisateurs")
    ForEach ($OU in OUS){ NewADOrganizationalUnit -Name $OU -Patch "OU=Dallas, DC=tai, DC=local}
    Get-ADObject -Filter * -SearchBase "OU=Dallas, OU=tai, OU=local"
    
    # Désactivation de la protection contre la suppression accidentelle pour une OU
    Set-ADOrganizationalUnit -Identity "OU=Ordinateur, OU=Dallas, DC=tai, DC=local" -ProtectedFromAccidentDeletion $false
    
    # Création de groupe d'administrateur de succursale 
    New-ADGroup -Name "Administrateur_Dallas" -Description "Voici le group des admin dallas" -GroupScope Global -Path "OU=Admin, OU=Dallas, DC=tai, DC=local"
    
    # Suppression d'une OU et de son contenue
    Remove-ADOrganizationalUnit -Identity "OU=Serveur, OU=Dallas, DC=tai, DC=local" -Recursive -Confirm:$false
    
    # Trouver les propriété d'ordinateur dans Active Directory avec Powershell
    Get-ADComputer -Filter *
    


 Création d'Utilisateurs :

$users = @(
    @{Name="Utilisateur1"; GivenName="Utilisateur"; Surname="1"; SamAccountName="utilisateur1"; UPN="utilisateur1@tai.com"},
    @{Name="Utilisateur2"; GivenName="Utilisateur"; Surname="2"; SamAccountName="utilisateur2"; UPN="utilisateur2@tai.com"},
    @{Name="Utilisateur3"; GivenName="Utilisateur"; Surname="3"; SamAccountName="utilisateur3"; UPN="utilisateur3@tai.com"},
    @{Name="Utilisateur4"; GivenName="Utilisateur"; Surname="4"; SamAccountName="utilisateur4"; UPN="utilisateur4@tai.com"},
    @{Name="Utilisateur5"; GivenName="Utilisateur"; Surname="5"; SamAccountName="utilisateur5"; UPN="utilisateur5@tai.com"}
)

$users | ForEach-Object {
    New-ADUser -Name $_.Name `
               -GivenName $_.GivenName `
               -Surname $_.Surname `
               -SamAccountName $_.SamAccountName `
               -UserPrincipalName $_.UPN `
               -Path "OU=RH,DC=tai,DC=com" `
               -AccountPassword (ConvertTo-SecureString "P@ssw0rd" -AsPlainText -Force) `
               -Enabled $true
}
$users | ForEach-Object {
    Add-ADGroupMember -Identity "Groupe RH" -Members $_.SamAccountName
}

---

