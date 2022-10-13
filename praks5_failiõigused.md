# Praktikum 5 - Failiõigused Linuxis
Autor: Uku Tonsiver

Viiendas praktikumis uurisime, millised on õigused failide ja kaustade nägemiseks, muutmiseks, kustutamiseks, jooksutamiseks. See praktikum keskendus just Unixi baasil operatsioonisüsteemidele.

Vastused praktikumi küsimustele:

1. a) r; b) r; c) w, x; d) w

2. Peale 'execute' õiguse läheb vaja veel ka 'read' õigust, sest süsteem peab käivitamiseks kõigepealt skriptifaili lugema.

3. Linuxis peab iga kasutaja kuuluma vähemalt ühte gruppi. Et seda nõuet täita ning samas kasutajate privaatsust tagada, luuakse vaikimisi igale kasutajale temanimeline grupp, mille ainus liige on see sama kasutaja.
4. Vajalik on r õigus. 
