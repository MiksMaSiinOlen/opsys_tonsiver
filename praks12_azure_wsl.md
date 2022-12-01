# Praktikum 12 - Azure VM ja WSL
Autor: Uku Tonsiver

Vastused praktikumi küsimustele:

A

1. Kolm suurimat pilveteenuste pakkujat on Amazon Web Services, Microsoft Azure ja Google Cloud Platform.

2. 
I Pilves andmeid säilitades saab neile lihtsasti ligi pääseda erinevatest masinatest erinevatest kohtadest.

II Tavainimese perspektiivist on andmeid pilves majutades majutusruum praktiliselt piiramatu.

III Pilveteenuste pakkujad pakuvad võimalusi andmeid dubleerida, et ennetada mingisuguse õnnetuse korral andmete kaotamist.

IV Pilveteenustes on andmed (enamasti) krüpteeritud, mis loob parema turvalisuse.

V Kuna pilves andmeid hoides maksab klient ainult kasutatud ruumi eest, on see tihti odavam kui füüsiliste andmekandjate kasutamine, mille korral klient maksab ka kasutamata jäänud ruumi eest.

3. 
I Pilveteenuse kasutamine ei ole tark idee, kui on teada, et on tihti vaja teenust kasutada internetita või väga aeglase internetiga situatsioonis.

II Kui füüsilised andmekandjad on juba varem olemas ja ei ole suurt vajadust teenuseid erinevatest masinatest kätte saada, ei ole tark pilveteenuste peale lisaks raha kulutada.

III Kuna pilveteenused võivad aeg-ajalt (kuigi väga harva) maas olla, siis kui mingit teenust on kriitiliselt vajalik 24/7 kätte saada, on targem seda füüsiliselt majutada (või vähemalt rohkem kui ühes pilves).

4. IAAS tüüpi pilveteenus hoolitseb riistvara, networkingu ja virtualisatsiooni eest (infrastruktuuri eest), platvorm (operatsioonisüsteem, runtime, middleware) ja tarkvara (rakendused ja nendega seostuvad andmed) jäetakse kasutaja tegeleda. IAAS teenus on spbilik näiteks pilves virtuaalmasina kasutamiseks. PAAS tüüpi pilveteenus hoolitseb lisaks infrastruktuurile ka platvormi eest ja kasutaja õlule jääb vaid tarkvara. PAAS on eriti sobilik just arendajatele, kes saavad pilves rakendusi arendada muretsemata nendega kaasneva infrastruktuuri ja platvormi pärast. SAAS tüüpi pilveteenuse korral on nii infrastruktuur, platvorm kui tarkvara kõik pilves hoiustatud. SAAS on sobilik igapäevaste lihtsate teenuste jaoks, näiteks on SAAS pilveteenused Google Docs, Microsoft Office 365 jne.

5. IAAS teenust pakub Eestis näiteks Riigipilv ja ka Tartu Ülikool.

6. Resource Group on sisuliselt andmestruktuur, mis hoiab endas kuidagi omavahel seotud Resource objekte. See, milliseid Resource objekte koos gruppidesse panna, ei ole üheselt määratud ja oleneb kasutaja vajadustest.

7. Subscription on üks nii-nimetatud ruum Azure pilveteenuses. Eraldi Subscriptionites saab hoida erinevaid andmeid ja kasutada erinevaid teenuseid, ilma, et Subscriptionid omavahel suhtleks. Näiteks võib erinevate projektide arendamist teha erinevates Subscriptionides.

8. Resource on üldine nimetus asjale, mida pilves hoiustatake.

9. 
![asdffgdas](https://user-images.githubusercontent.com/92918498/205139430-dfd29b3d-08d3-4be4-9117-bad68ca2d3aa.jpg)

10.
![sadhjtsrae](https://user-images.githubusercontent.com/92918498/205139455-15d69a98-0f54-406d-b33f-038038e4516a.jpg)

11.
![asuklkjtrae](https://user-images.githubusercontent.com/92918498/205141634-1bc36515-cd95-429c-98e5-c059418ff24f.jpg)

12. 
I SSH tehnoloogiat kasutades saab saata käske Linuxi serveritele või arvutitele.
II HTTPRequest abil saab internetist andmeid üles korjata.
III Terminalis saab mängida NetHack arvutimängu.

13.
![szdrtfygjgyftdrsd](https://user-images.githubusercontent.com/92918498/205146714-3e5761e0-d60e-4367-b153-1a79d4509e7b.jpg)

14. NB! Lisasin skriptifaili 'accident' kausta ja kirjutasin 'paroolid.txt' faili ka sinna. Kui soovite skriptifaili ja paroolide faili teises kaustas hoida, peab skripti lisaks kirjutama kaustade vahel navigeerimise käsud.
```
#!/bin/bash

touch paroolid.txt

for fail in *.md
do
  if [ -s $fail ]
  then
    while read rida
    do
      echo $rida >> paroolid.txt
    done < $fail
  fi
done
```
