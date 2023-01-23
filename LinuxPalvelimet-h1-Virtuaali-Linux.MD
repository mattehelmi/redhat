# LinuxPalvelimet-h1-Virtuaali-Linux

# x) Tiivistelmä raportin kirjoittamisesta

- Raportin tulee olla toistettava ja siitä pitää käydä ilmi toteutusympäristö
- Raportin täytyy olla mahdollisimman täsmällinen mm. kellonaikojen suhteen
- Raportin pitää olla helppolukuinen ja selkeä
- Lähteisiin pitää viitata, aina kun mahdollista
- Raportissa ei saa plagioida, käyttää luvatta kuvia tai sepittää valheita

# a) Linuxin asentaminen virtuaalikoneeseen

## Käyttöjärjestelmä ja rauta
- MacOS Catalina v. 10.15.7
- MacBook Pro (Retina, 15-inch, early 2013)

## Ennakkoa
Minulla oli entuudestaan VirtualBox asennettuna kannettavassa, joten sitä ei tarvinnut ladata ja asentaa erikseen. Käytän tällä kurssilla vanhempaa macbookia, sillä VirtualBoxia ei ole toistaiseksi saatavilla uusille M1-Macbookeille.

## Debianin lataaminen ja asennus
Tässä tehtävässä seurasin suoraan Teron tekemiä ohjeita, ja se oli myös varmasti tarkoituskin.
- Latasin Debianin ISO:n suoraan Teron nettisivulta (https://terokarvinen.com/2021/install-debian-on-virtualbox/)
- Tein uuden virtuaalikoneen ohjeiden mukaan VirtualBoxiin ja lisäsin sinne Debianin
- Valitsin VirtualBoxissa kaikki samat kohdat, mitkä olivat ohjeissa
- Kun kaikki tarvittavat kohdat oli täytetty VirtualBoxissa, käynnistin Debianin ensimmäistä kertaa
- Valitsin Debianin Live asennuksen, koska niin suositeltiin ohjeissa
- Tämän jälkeen Debian avautui ensimmäistä kertaa niin sanottuun päänäkymään
- Kokeilin käynnistää Firefoxin, koska halusin selvittää pääseekö virtuaalikoneella nettiin (kyllä pääsi)
- Kun kaikki vaikutti toimivan hyvin, päätin aloittaa järjestelmän asennuksen työpöydän ohjelmasta 'Install Debian'
- Tässä kohtaa seurasin ohjeita tarkkaan ja täytin kaikki oikeat kohdat
- Asennus viimeisteltiin vahvalla salasanalla, jonka jälkeen järjestelmä asensi kaikki loput tarvittavat osat
- Asennuksen jälkeen käynnistin koneen uudestaan
- Uudelleen käynnistyksen jälkeen pääsin ensimmäistä kertaa kirjautumaan omilla tunnuksilla sisään järjestelmään
- Tämän jälkeen kokeilin uudestaan, että netti toimii eli avasin Firefoxin ja testasin pääsenkö Googlen etusivulle (kyllä pääsin)
- Kun kaikki näytti toimivan niin kuin pitikin, avasin päätteen eli Terminalin ohjeiden mukaan
- Terminaliin kirjoitin ohjeiden mukaan seuraavat asiat: "sudo apt-get update", "sudo apt-get -y dist-upgrade", "sudo apt-get -y install ufw" ja "sudo ufw enable"
- Yllä olevat lauseet päivittivät kaiken mahdollisen Debianissa ja lisäsivät palomuurin päälle
- Tämän jälkeen käynnistin tietokoneen taas uudestaan
- Seuraavaksi asensin Guest Additionsin, jonka tarkoitus on asentaa oikeat ajurit, jotta näytön resoluutio paranee
- Seurasin edelleen ohjeita ja sain ajurit asennettua ja näytön resoluutio muuttui "normaaliksi"
- Nyt minulla on täysin toimiva Debian virtuaalikoneessa

## Ajankäyttö
Tehtävää nopeutti huomattavasti se, että olin jo entuudestaan käyttänyt VirtualBoxia ja asentanut sille muutaman eri linux-käyttöjärjestelmän. Aikaa koko prosessiin kului noin 30 minuuttia. Tähän tehtävään en pilko tarkempia aikoja, sillä tehtävä oli mielestäni sen verran yksinkertainen. Kun asiat muuttuvat teknisemmiksi niin tulen kirjoittamaan kellonajat tarkkaan ylös.

## Lähteet
Karvinen, T. 2023. Install Debian on Virtualbox - Updated 2023. https://terokarvinen.com/2021/install-debian-on-virtualbox/








