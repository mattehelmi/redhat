# LinuxPalvelimet-h6-Based

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

Apache Software Foundation 2023: Getting Started
- Artikkeli kertoo Apache HTTP serverin käyttöönotosta ja perusteista
- Clientit, serverit ja URLit tärkeässä asemassa kun asennetaan Apachea
- VirtuaHosts -tiedostot sijaitsevat yleensä kansiossa ``/etc/hosts``
- Apachen HTTP palvelin konfiguroidaan tekstitiedostojen avulla
- Nettisivun sisältö voi olla staattista (mm. HTML-tiedostot) tai dynaamista (mm. javascript)
- Virheilmoitusloki on Apache palvelinylläpitäjän tärkeimpiä työkaluja

Apache Software Foundation 2023: Name-based Virtual Host Support
- Artikkeli kuvailee miten nimeen perustuvat virtuaali hostit toimivat
- Yksinkertaisempi käyttää kuin IP-osoitteeseen perustuva virtuaali host
- Ensimmäiseksi tehdään ``<VirtualHost>`` niminen blokki, jonka sisään laitetaan tarvittavat datat kuten ``ServerName`` ja ``ServerAlias``
- ServerName voisi esimerkiksi olla www.example.com ja ServerAlias example.com
- ServerName tarkoittaa, että HTTP pyynnön host osuuden täytyy täsmätä nimeen niin se voidaan hyväksyä
- ServerAlias alle listataan sanat, joilla palvelimen sivut myös löydetään

## a) Vaihda Apachelle uusi etusivu

Aloitin etusivun vaihtamisen komennolla ``sudoedit /etc/apache2/sites-available/frontpage.conf``. Edellinen komento avasi frontpage.conf tiedoston sudo oikeuksilla. Tämän jälkeen muokkasin tiedoston seuraavan näköiseksi tekstieditorilla:

![Add file: Upload](sudoedit-h6.png)

Seuraavaksi suoritin komennon ``sudo a2ensite frontpage.conf``. Edellinen komento aktivoi kaikki kansion sivut.

Tämän jälkeen annoin komennon ``sudo a2dissite 000-default.conf``. Se kytki 000-default.conf -tiedoston pois päältä. 

Näiden muutosten jälkeen käynnistin Apachen uudelleen, jotta tehdyt muutokset astuivat voimaan. Käytin komentoa ``sudo systemctl restart apache2.service``.

Viimeiseksi tein ``public_sites`` nimisen kansion käyttäjän mathias kotikansioon ja lisäsin sinne ``index.html`` tiedoston. Testasin selaimessa toimiiko uusi etusivu ja se toimi.

## b) Tee Apachen asetustiedostoon kirjoitusvirhe

Ensimmäiseksi avasin Apachen asetukset komennolla ``sudoedit /etc/apache2/sites-available/frontpage.conf``. Tein kirjoitusvirheen kirjottamalla "keijo" tiedostopolkuun. Kyseistä "keijo" -nimistä käyttäjää ei oikeasti ole. Halusin nähdä millainen virheilmoitus tästä syntyy.

![Add file: Upload](sudoedit-keijo-h6.png)

Tämän jälkeen käynnistin Apachen uudelleen, jotta muutos tulee voimaan. Käytin tähän seuraavaa komentoa ``sudo systemctl restart apache2.service``. 

Seuraavaksi kokeilin oliko etusivulle tullut muutoksia. Käytin tähän komentoa ``curl localhost``. Muutoksia oli tapahtunut, alla kuva.

![Add file: Upload](sudoedit-virhe-h6.png)

Seuraavaksi käytin komentoja ``sudo tail -1 /var/log/apache2/error.log`` ja ``sudo /usr/sbin/apache2ctl configtest``. Kyseisillä komennoilla saadaan mahdolliset virheet näkyviin. Alla kuva virheilmoituksista.

![Add file: Upload](sudoedit-virheet-h6.png)

Komennolla ``sudo tail -1 /var/log/apache2/error.log`` sain näkyviin tapahtuman virhelokin. Virhelokista silmiin osui [authz_core:error] sekä teksti "AH02630: client denied by server configuration: /home/mathias/public_sites". Tästä päättelin, että kyseessä on oikea virheilmoitus, joka johtuu väärin muotoillusta polusta.

Komento ``sudo /usr/sbin/apache2ctl configtest`` antoi seuraavan tekstin: "AH00558: apache2: Could not reliable determine the servers fully qualified domain name". Tämä virheilmoitus liittyi siis palvelimen domainiin.


## Lähteet

https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/

https://httpd.apache.org/docs/2.4/getting-started.html

https://httpd.apache.org/docs/current/vhosts/name-based.html

https://serverfault.com/questions/520195/how-does-servername-and-serveralias-work


