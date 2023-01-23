# LinuxPalvelimet-h2-Komentaja-Pingviini

## Micro-editorin asennus
Asensin Micro-editorin Debianin komentorivin kautta seuraavalla komennolla: 'sudo apt-get -y install micro'.

![Add file: Upload](micro-install.png)

## Lshw:n asennus ja raudan listaus
Minulla ei ollut lshw:ta asennettuna, joten asensin sen virtuaalikoneelleni komentorivin kautta seuraavalla komennolla: 'sudo apt-get install lshw'.

![Add file: Upload](lshw-install.png)

Kun lshw oli asennettu niin listasin käyttämäni raudan komennolla: 'sudo lshw -short -sanitize'.

![Add file: Upload](KoneenRauta.png)

Komento 'sudo lshw -short -sanitize' listaa tarkat tiedot käyttämästä raudasta. Listaus on kategorisoitu neljään eri osaan: H/W path, device, class ja description. Listalta on helppo lukea tarkat tiedot raudasta jolla työskentelen. Nämä tiedot ovat oleellisia esimerkiksi vianmäärityksessä. 

## Kolmen uuden komentoriviohjelman asennus
Asensin seuraavat kolme komentoriviohjelmaa itselleni: Googler, Neofetch ja ncdu. Kaikki ohjelmat sai ladattua ja asennettua yhdellä komennolla: 'sudo apt-get -y install googler neofetch ncdu'. Seuraavaksi kuvakaappaukset ja lyhyet selitykset ohjelmista.

**Googler** on komentorivityökalu Googlen käyttöön.

![Add file: Upload](googler.png)

**Neofetch** on komentorivityökalu, joka listaa raudan ja sitä on todella helppo käyttää, sillä se listaa tiedon helposti luettavaan muotoon.

![Add file: Upload](neofetch.png)

**Ncdu** on komentorivityökalu, joka listaa raudan muistia käyttävät ohjelmat ja kansiot. 

![Add file: Upload](ncdu.png)

## Tärketä kansiot

### /
Root-kansio, joka on kaikista ylin kansio koko järjestelmässä.

![Add file: Upload](root.png)

### /home/
Sisältää kaikkien käyttäjien koti-kansiot.

![Add file: Upload](home.png)

### /home/mathias/
Käyttäjän "Mathias" koti-kansio. Käyttäjä "Mathias" tallentaa tänne kaiken lataamansa datan.

![Add file: Upload](mathias.png)

### /etc/
Tästä kansiosta löytyy kaikki järjestelmän asetukset helposti luettavassa teksti tekstimuodossa.

![Add file: Upload](etc.png)

### /media/
Tästä kansiosta löytyy ns. irrotettavat mediat kuten usb-tikut ja cd-levyt.

![Add file: Upload](media.png)

### /var/log/
Tästä kansiosta löytyy kaikki järjestelmän lokitiedostot esim. 'syslog'.

![Add file: Upload](varLog.png)

