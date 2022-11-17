# Praktikum 10 - Skriptimine Linuxis
Autor: Uku Tonsiver

Praktikumi ülesannete lahendused:

3. Skripitfaili nimi on esimene.sh
```
#!/bin/sh

echo "Sisesta nimi:"
read nimi
echo "Sisesta eriala:"
read eriala
echo "Sisesta martikli number:"
read number

echo "Nimi: $nimi"
echo "Eriala: $eriala"
echo "Matrikli number: $number"
```

![asdfhuyrts](https://user-images.githubusercontent.com/92918498/202482678-b1bf29ed-33fc-448d-bfd7-ab6f44ae0e3f.jpg)

4. Skriptifaili nimi on teine.sh
```
#!/bin/bash

echo "Sisesta laiend A:"
read A
echo "Sisesta laiend B:"
read B

for fail in $(ls)
do
    if [ ${fail##*.} = $A ]
    then
        mv "${fail}" "${fail/%$A/$B}"
    fi
done
```

![sdfghjhgfds](https://user-images.githubusercontent.com/92918498/202491003-d14cb076-65fe-46a1-bfd3-0570cffd7a64.jpg)

5. Skriptifaili nimi on kolmas.sh
```
#!/bin/bash

IFS=$'\n'

for prot in $(ps -A)
do
    nimi=$(echo " "$prot | tr -s ' ' | cut -d ' ' -f5)
    pid=$(echo " "$prot | tr -s ' ' | cut -d ' ' -f2)
    if [ "$nimi" = "$1" ]
    then
        echo "PID: $pid"
        echo "Protsessi nimi: $nimi"
    fi
done
```

![sdfghh](https://user-images.githubusercontent.com/92918498/202500370-e639ab61-8215-428e-a850-14421b5f5353.jpg)

6. Skriptifaili nimi on neljas.sh
```
#!/bin/bash

astenda() {
    if [ "$2" -eq 1 ]
    then
        echo "$1"
    else
        astendaja=$(($2 - 1))
        uus=$(astenda $1 $astendaja)
        echo $(($1 * uus))
    fi
}

a=$(astenda 9 5)

echo $a
```

![styuiutydrae](https://user-images.githubusercontent.com/92918498/202505521-219b030d-b259-42f7-9a4b-59d0c361d55b.jpg)
