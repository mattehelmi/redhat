# LinuxPalvelimet-h5-HelloWeb!

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
    
## x) Kuuntele ja tiivistä

Apache Software Foundation 2023: Getting Started
- asa
- gsgsg
- gsgsgs
- fafa

Apache Software Foundation 2023: Name-based Virtual Host Support
- cacaf
- fafsasf
- affaf

## a) Vaihda Apachelle uusi etusivu

Aloitin etusivun vaihtamisen komennolla ``sudoedit /etc/apache2/sites-available/frontpage.conf``. Edellinen komento avasi frontpage.conf tiedoston sudo oikeuksilla. Tämän jälkeen muokkasin tiedoston seuraavan näköiseksi tekstieditorilla:

![Add file: Upload](sudoedit-h6.png)

Seuraavaksi suoritin komennon ``sudo a2ensite frontpage.conf``. Edellinen komento aktivoi kaikki kansion sivut.

Tämän jälkeen annoin komennon ``sudo a2dissite 000-default.conf``. Se kytki 000-default.conf -tiedoston pois päältä. 

Näiden muutosten jälkeen käynnistin Apachen uudelleen, jotta tehdyt muutokset astuivat voimaan. Käytin komentoa ``sudo systemctl restart apache2.service``.

Viimeiseksi tein ``public_sites`` nimisen kansion käyttäjän mathias kotikansioon ja lisäsin sinne ``index.html`` tiedoston. Etusivu on nyt vaihdettu onnistuneesti.

## b) Tee Apachen asetustiedostoon kirjoitusvirhe





