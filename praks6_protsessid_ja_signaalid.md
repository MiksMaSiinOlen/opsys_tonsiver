# Praktikum 6 - protsessid ja signaalid
Autor: Uku Tonsiver

Kuuendas praktikumis saime tuttavaks, mis asjad on protsessid, kuidas neile signaale saata ja kuidas nende sisendeid ja väljundeid käsitseda.

Vastused praktikumi küsimustele:

1.
![aesytogfhjesfdg](https://user-images.githubusercontent.com/92918498/210869983-96848b54-bc16-4315-ae74-5dad1117d16b.jpg)

2.
![dsrtstadfsf](https://user-images.githubusercontent.com/92918498/210870042-c115cbae-4a09-4256-bec3-6d8d4faaa045.jpg)

3.
Käsk soovitud väljundi saamiseks: ```ps -axu | grep daemon | tr -s " " | cut -d" " -f11-```
![uifjdoijaoidlakfmd](https://user-images.githubusercontent.com/92918498/210870500-b058538d-308c-4c85-af83-cefdc116aaa7.jpg)

4.
Käsk soovitud väljundi ekraanile kuvamiseks: ```ip a | gerp enp0s3 | grep inet | tr -s " " | cut -d" " -f3```<br>
Käsk soovitud väljundi faili ipaddress.txt kirjutamiseks: ```ip a | gerp enp0s3 | grep inet | tr -s " " | cut -d" " -f3 >ipaddress.txt```
![artsgafderytuliukt](https://user-images.githubusercontent.com/92918498/210872725-ea1fdabd-d371-49a4-80d3-4142aab0dcc8.jpg)
