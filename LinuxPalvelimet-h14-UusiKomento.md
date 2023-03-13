# LinuxPalvelimet-h14-UusiKomento

## Mathias Helminen

## Rauta
    Mallin nimi:            MacBook Pro (Retina, 15-inch, Early 2013)
    Prosessorin nimi:       Quad-Core Intel Core i7
    Prosessorin nopeus:     2,7GHz
    Prosessorien määrä:     1
    Ydinten kokonaismäärä:  4
    Muisti (RAM):           16 Gt 1600 MHz DDR3
    Tallennustila:          500 Gt
    Näytönohjain:           Intel HD Graphics 4000
    Järjestelmän versio:    macOS Catalina 10.15.7
    Kernel-versio:          Darwin 19.6.0
    Virtuaalikone:          Oracle VirtualBox, Version 6.1.40
    
Tehtävien aloitusaika klo 10:24.

## A) Uusi komento Bashilla
Aloitin tehtävän luomalla kansion "Skriptit". Sen sisälle tein tiedoston nimeltään "pwdls". Muokkasin tiedoston sisältöä ja lisäsin sinne Bashia. "Pwd" komento näyttää tiedostopolun ja "ls" listaa tiedostot, jotka ovat sen hetkisessä kansiossa. Kopioin tiedostopolun niin, että kaikilla käyttäjillä on pääsy siihen. Lopuksi annoin kaikille käyttäjille oikeuden ajaa tiedostoa. 

    $ mkdir Skriptit
    $ cd Skriptit
    $ nano pwdls
    #! /usr/bin/bash
    pwd
    ls
    
    $ chmod a+x pwdls
    $ cp /home/mathias/Skriptit/pwdls /usr/local/bin

Tämän jälkeen vaihdoin käyttäjää ja kokeilin voiko toinen käyttäjä ajaa tiedoston onnistuneesti.

    $ su test1
    $ pwdls
    
![Add file: Upload](uusikomento1-h14.png)

Testi onnistui testikäyttäjällä, joten siitä voi päätellä, että uusi komento toimii niin kuin pitääkin.

## B) Uusi komento Pythonilla



![Add file: Upload](helloworld6-h13.png)

## C) Uusi komento monelle tiedostolle


![Add file: Upload](helloworld6-h13.png)

## Lähteet

https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/

