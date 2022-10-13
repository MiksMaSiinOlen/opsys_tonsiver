# Praktikum 5 - Failiõigused Linuxis
Autor: Uku Tonsiver

Viiendas praktikumis uurisime, millised on õigused failide ja kaustade nägemiseks, muutmiseks, kustutamiseks, jooksutamiseks. See praktikum keskendus just Unixi baasil operatsioonisüsteemidele.

Vastused praktikumi küsimustele:

1. a) r; b) r; c) wx; d) w

2. Peale 'execute' õiguse läheb vaja veel ka 'read' õigust, sest süsteem peab käivitamiseks kõigepealt skriptifaili lugema.

3. Linuxis peab iga kasutaja kuuluma vähemalt ühte gruppi. Et seda nõuet täita ning samas kasutajate privaatsust tagada, luuakse vaikimisi igale kasutajale temanimeline grupp, mille ainus liige on see sama kasutaja.
4. Vajalik on r õigus. Pärast chmod käsuga r õiguse andmist saan tavakasutajana faili lugeda.
<img width="369" alt="4" src="https://user-images.githubusercontent.com/92918498/195652554-c9bfd2a6-0066-4658-9017-1d78c71f2095.png">

5. 
<img width="316" alt="5" src="https://user-images.githubusercontent.com/92918498/195660350-c22d444a-5b6f-448d-ad33-5d2dcf9276ee.png">

6. setuid ja setgid kasutamine võib tõesti vähendada süsteemi turvalisust, sest need käsud annavad protsessidele vastavalt protsessi omaniku või protsessi grupi õigused. Niimoodi võivad mõnikord kindlad õigused süsteemis sattuda valedesse kätesse.
7. peeter, opetaja
8. Õiguste loetelu lõppu on tekkinud '+' märk. See ilmselt vihjab sellele, et leidub peale omaniku veel gruppe (direktori grupp antud juhul), kellel on 'others' alla minevatest kasutajatest erinevad õigused.
<img width="371" alt="8" src="https://user-images.githubusercontent.com/92918498/195666819-f4e0d3d7-fba1-4ea4-8d7a-172761d09a92.png">

9. chattr +i parameetriga faili sisu ei saa muuta mitte keegi. Et sellist faili kustutada, peab talt selle parameetri kõigepealt eemaldama. Seda saab teha käsuga 'sudo chattr -i testfail-2'. Pärast seda saab seda faili kustutada nagu iga teist, käsuga 'rm testfail-2'.
