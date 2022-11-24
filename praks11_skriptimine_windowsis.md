# Praktikum 11 - Skriptimine Windowsis
Autor: Uku Tonsiver

Üheteistkümnendas praktikumis õppisime skripte looma ja jooksutama Windowsis. Kasutasime selleks Powershell ISE tekstiredaktorit. Skriptide loomine on kasulik arvutile keerulisemate juhiste andmiseks.

Loodud skriptifaili sisu:
```
# kirjutan faili asukoha muutujasse, et ei peaks iga kord eraldi välja kirjutama
$path = "C:\Users\Uku\väljund.txt"


# 1.

# -Append, et uus informatsioon lisataks faili juurde, mitte ei kirjutataks iga kord kogu faili üle
"1." | Out-File $path -Append

$masin = hostname
"Masina nimi: $masin" | Out-File $path -Append

$psVersioon = $PSVersionTable.PSVersion
"Powershelli versioon: $psVersioon" | Out-File $path -Append

# select: valib vaid meile olulise info
# Convert-String: teeb väljundi natuke silmale ilusamaks
$winVersioon = Get-ComputerInfo | select WindowsProductName | Convert-String -Example @{before="{WindowsProductName=asi}"; after="asi"}
"Windowsi versioon: $winVersioon" | Out-File $path -Append


# 2.
# ei osanud kahjuks välja mõelda, kuidas võrgu maski leida

# reavahetus, et ülesanded lihtsamini eristatavad oleks
"`n2." | Out-File $path -Append

# Trim(): eemaldab väljundist soovimatud tühjad read
"IP-aadress:"| Out-File $path -Append
$ip = Get-WmiObject Win32_NetworkAdapterConfiguration -Filter "IPEnabled='True'" | Select-Object IPAddress | Out-String | Convert-String -Example @{before="{asi}"; after="asi"}
$ip.Trim() | Out-File $path -Append

"`nGateway:"| Out-File $path -Append
$gateway = Get-WmiObject Win32_NetworkAdapterConfiguration -Filter "IPEnabled='True'" | Select-Object DefaultIPGateway | Out-String | Convert-String -Example @{before="{asi}"; after="asi"}
$gateway.Trim() | Out-File $path -Append

"`nDHCP lubatud:"| Out-File $path -Append
$dhcp = Get-WmiObject Win32_NetworkAdapterConfiguration -Filter "IPEnabled='True'" | Select-Object DHCPEnabled | Out-String
$dhcp.Trim() | Out-File $path -Append

"`nMAC-aadress:"| Out-File $path -Append
$mac = Get-WmiObject Win32_NetworkAdapterConfiguration -Filter "IPEnabled='True'" | Select-Object MACAddress | Out-String
$mac.Trim() | Out-File $path -Append


# 3.

"`n3." | Out-File $path -Append

"Info protsessori kohta:"| Out-File $path -Append
$protsessor = Get-CimInstance -ClassName Win32_Processor | Out-String
$protsessor.Trim() | Out-File $path -Append

"`nPõhimälu kogus (baitides):"| Out-File $path -Append
$ram = Get-WmiObject Win32_ComputerSystem | Select-Object TotalPhysicalMemory | Out-String
$ram.Trim() | Out-File $path -Append


# 4

"`n4." | Out-File $path -Append

"Graafikakaardi nimi:"| Out-File $path -Append
$graafikakaart = Get-WmiObject Win32_VideoController | Select-Object Description | Out-String
$graafikakaart.Trim() | Out-File $path -Append

"`nGraafikakaardi draiveri versioon:"| Out-File $path -Append
$driverVersioon = Get-WmiObject Win32_VideoController | Select-Object DriverVersion | Out-String
$driverVersioon.Trim() | Out-File $path -Append

"`nGraafikakaardi kuupäev:"| Out-File $path -Append
$kaardiKuupaev = Get-WmiObject Win32_VideoController | Select-Object DriverDate | Out-String
$kaardiKuupaev.Trim() | Out-File $path -Append

"`nEkraani lahutus:"| Out-File $path -Append
$lahutus = Get-WmiObject Win32_VideoController | Select-Object VideoModeDescription | Out-String
$lahutus.Trim() | Out-File $path -Append


# 5

"`n5." | Out-File $path -Append

"Partitsioonitabel:" | Out-File $path -Append
$partitsioonid = Get-Partition | Out-String
$partitsioonid.Trim() | Out-File $path -Append

"`nVaba ruum C: kettal (baitides):" | Out-File $path -Append
$vabaRuum = Get-Volume -DriveLetter C | Select-Object SizeRemaining | Out-String
$vabaRuum.Trim() | Out-File $path -Append


# 6

"`n6." | Out-File $path -Append

"Info PCI siinil asuvate draiverite kohta:" | Out-File $path -Append
$pci = Get-WmiObject Win32_PnpSignedDriver | Where-Object {$_.DeviceID -like „PCI*“} | Select-Object Description, Manufacturer, DriverVersion | Out-String
$pci.Trim() | Out-File $path -Append


# 7

"`n7." | Out-File $path -Append

"Info arvuti kasutajate kohta:" | Out-File $path -Append
$kasutajad = Get-WmiObject Win32_UserAccount | Select Name, Description, LocalAccount, Disabled | Out-String
$kasutajad.Trim() | Out-File $path -Append


# 8

"`n8." | Out-File $path -Append

"Hetkel käimas olevate protsesside arv:" | Out-File $path -Append
$protsesse = Get-Process | Measure-Object | Select-Object Count | Out-String
$protsesse.Trim() | Out-File $path -Append


# 9

"`n9." | Out-File $path -Append

"10 viimasena käivitatud protsessi:" | Out-File $path -Append
$viimased10 = Get-Process | Sort-Object StartTime | Select -Last 10 | Select-Object ProcessName, Id, StartTime | Out-String
$viimased10.Trim() | Out-File $path -Append


# 10

"`n10." | Out-File $path -Append

"Kuupäev ja kellaaeg:" | Out-File $path -Append
$aeg = Get-Date | Out-String
$aeg.Trim() | Out-File $path -Append
```
