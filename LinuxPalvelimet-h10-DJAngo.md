# LinuxPalvelimet-h10-DJAngo

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
    
# A) Tietokantasovellus
Itsellä ei ollut juuri kokemusta djangosta ennen tätä kurssia, joten siitä syystä seurasin Teron tekemiä ohjeita (https://terokarvinen.com/2022/django-instant-crm-tutorial/) hyvin tarkasti. 

Tehtävän aloitusaika 9:35.

Ensimmäiseksi ladataan virtualenv ja uusimmat python versiot. Tässä vaiheessa tehdään myös ``env/`` -niminen kansio, jonne paketit ladataan.

    $ sudo apt-get -y install virtualenv
    $ virtualenv --system-site-packages -p python3 env/
    
Seuraavaksi kokeillaan käyttää virtuaaliympäristöä.

    $ source env/bin/activate
    
![Add file: Upload](django1-h10.png)

Yllä olevasta kuvasta huomaa, että virtuaaliympäristö toimii oikein ja asennus onnistui, sillä ``(env)`` näkyy promptissa.

Seuraavaksi tehdään pip -kansio virtuaaliympäristön sisään. 

    $ which pip
    /home/tero/env/bin/pip

Tämän jälkeen ladataan Djangon uusin versio pipin avulla. Ensin kuitenkin listataan Python-paketti tekstitiedostoon.

    $ nano requirements.txt # "django"
    
    $ cat requirements.txt
    django
    
    pip install -r requirements
    
![Add file: Upload](django2-h10.png)

Yllä olevasta kuvasta näkee, että Djangon uusin versio on asennettu (4.1.7).

Seuraavaksi tehdään projektikansio ja kokeillaan toimiiko se. 

    $ django-admin startproject massecom
    
    $ cd massecom
    $ ./manage.py runserver # development server
    
![Add file: Upload](django3-h10.png)

Yllä olevasta kuvasta näkee, että Djangon asennus onnistui.

Seuraavaksi päivitetään tietokanta ja tehdään admin -käyttäjälle oma sivu seuraavilla komennoilla.

    $ ./manage.py makemigrations
    $ ./manage.py migrate

    $ ./manage.py createsuperuser
    
![Add file: Upload](django4-h10.png)

Yllä olevasta kuvasta näkee, että admin -sivu toimii ja pystyn kirjautumaan admin -käyttäjänä sisään.

Seuraavaksi tein uuden käyttäjän nimeltä "testipetteri" ja kokeilin kirjautua hänen tunnuksillaan sisälle. Se onnistui niin kuin alla näkyvästä kuvasta huomaa.

![Add file: Upload](django5-h10.png)

Seuraavaksi teen tuotetietokannan seuraavalla komennolla.

    $ ./manage.py startapp products

Tämän jälkeen muokkasin massecomin asetuksia ja lisään sinne kohdan 'products'

    INSTALLED_APPS = [
        'django.contrib.admin',
        'django.contrib.auth',
        'django.contrib.contenttypes',
        'django.contrib.sessions',
        'django.contrib.messages',
        'django.contrib.staticfiles',
        'products', # lisäsin tämän kohdan
    ]

Seuraavaksi lisätään malleja äsken tehtyyn 'products' tietokantaan.

    $ nano products/models.py
    
    from django.db import models
    
    class Product(models.Model):
        name = models.CharField(max_length=300)
        
Tämän jälkeen ajetaan muutokset seuraavilla komennoilla.

    $ ./manage.py makemigrations
    $ ./manage.py migrate

Seuraavaksi rekisteröidään uusi tietokanta ``admin/``, jotta se on nähtävissä .

    $ nano products/admin.py
    
    from django.contrib import admin
    from . import models
    admin.site.register(models.Product)

Seuraavaksi kokeillaan toimiiko uusi tuotetietokanta. Ajetaan seuraava komento.

    $ ./manage.py runserver
    
![Add file: Upload](django6-h10.png)

Yllä olevasta kuvasta näkee, että "Products" -niminen kategoria on lisätty onnistuneesti sivulle.

Viimeiseksi muutin tuotteiden nimet näkyviin. Se onnistui seuraavilla komennoilla ja muutoksilla.

    $ nano products/models.py
    
    from django.db import models

    class Product(models.Model):
    name = models.CharField(max_length=160)

    def __str__(self):		# new
        return self.name	# new

Katsotaan onnistuiko nimien muuttaminen oikeiksi tuotenimiksi.

![Add file: Upload](django7-h10.png)

Tuotenimet ovat oikein, joten nimien päivitys onnistui.

Tehtävän lopetusaika 12:27

## Lähteet

https://terokarvinen.com/2023/linux-palvelimet-2023-alkukevat/

https://terokarvinen.com/2022/django-instant-crm-tutorial/
