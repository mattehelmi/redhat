# LinuxPalvelimet-h11-Prod

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
    
# A) Tuotantoasennus

Tehtävän aloitusaika 14:02.

Aloitin tehtävän asentamalla Apachen virtuaalikoneelle alla näkyvillä komennoilla.

    $ sudo apt-get update
    $ sudo apt-get -y install apache2
    
Alla näkyvästä kuvasta huomaa, että asennus onnistui sillä ``localhost`` -komento selaimessa tuotti toivotun tuloksen.

![Add file: Upload](prod1-h11.png)

Tämän jälkeen vaihdoin testisivulle tekstin ``Testitesti``. Se taphtui alla näkyvällä komennolla.

    $ echo "Testitesti"|sudo tee /var/www/html/index.html
    
Tekstin vaihtaminen onnistui, testasin sen ``curl`` komennolla. Alla kuva.

![Add file: Upload](prod2-h11.png)

Seuraavaksi lisäsin hakemistopolun ja kansiot ja muutin esimerkkitekstiä alla näkyvillä komennoilla.

    $ mkdir -p publicwsgi/masacom/static/
    $ echo "Staattinen sivu."|tee publicwsgi/teroco/static/index.html
    
Seuraavaksi lisäsin uuden virtuaalihostin (eng. VirtualHost) ja muutin tiedoston sisällön oikeaksi.

    $ sudoedit /etc/apache2/sites-available/teroco.conf
    
    <VirtualHost *:80>
	      Alias /static/ /home/mathias/publicwsgi/masacom/static/
	      <Directory /home/mathias/publicwsgi/masacom/static/>
		        Require all granted
	      </Directory>
    </VirtualHost>


## Lähteet

https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/

https://terokarvinen.com/2022/deploy-django/
