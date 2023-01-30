# LinuxPalvelimet-h4-Tukki!

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
    

## x) Lue ja tiivistä



## a) Tukki - Analysoi yksi esimerkkirivi kustakin lokista

- /var/log/syslog
![Add file: Upload](syslog.png)
``Päivämäärä, tietokoneen nimi, ohjelman nimi (ja pid?), mitä ohjelma tekee.``

Anacron on aikataulutusohjelma ja tämä loki kertoo, että cron.daily on käynnistynyt. En löytänyt nopealla googlauksella tarkoittaako [4307] anacronin perässä prosessin tunnistenumeroa.

- /var/log/auth.log
![Add file: Upload](auth.png)
``Päivämäärä, tietokoneen nimi ja root-oikeudet(sudo), käyttäjän nimi, mitä on tehty ja millä oikeuksilla.`` 

Yllä oleva kuva näyttää, että olen sudo-oikeuksilla avannut ``/var/log/auth.log`` lokin.

- /var/log/apache2/access.log
![Add file: Upload](access.png)
``Apachen ip-osoite, päivämäärä, mitä on tehty ja onko se onnistunut, selain, käyttöjärjestelmä, gecko?, selain?``

Avasin lokin komennolla ``sudo tail -10 /var/log/apache2/access.log``. Tämä on Apache HTTP serverin luoma lokitiedosto, joka käsittelee kaikki apache serverin kutsut. Tämä lokirivi muodostui kun kävin Mozilla Firefoxin kautta apachen http serverillä. Tämä oli onnistunut toimenpide ja luku "200" yllä olevassa kuvassa kertoo sen. En ollut varma mitä "Gecko" tarkoitti.

- /var/log/apache2/error.log
![Add file: Upload](error.png)


## b) Aiheuta lokiin kaksi eri tapahtumaa ja analysoi rivit yksityiskohtaisesti

1. Onnistunut toimenpide

![Add file: Upload](loki1.png)

Avasin Mozilla -selaimen ja kirjoitin hakukenttään "localhost". Tämän jälkeen menin linuxin komentoriville ja kirjoitin seuraavan komennon ``sudo tail -10 /var/log/apache2/access.log``. 

2. Epäonnistunut toimenpide

![Add file: Upload](loki2.png)

Avasin Mozilla -selaimen ja kirjoitin hakukenttään "localhost/random". Selaimeen tuli teksti "404 Not Found". Tämän jälkeen menin linuxin komentoriville ja kirjoitin seuraavan komennon ``sudo tail -10 /var/log/apache2/access.log``. 

## Lähteet
