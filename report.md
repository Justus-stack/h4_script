
# Harjoitus 4

## a) Hei komento. Tee järjestelmään uusi "hei maailma" -komento ja asenna se orjille saltilla

Aloitin tehtävän tekemisen luomalla tekstitiedoston kotikansioon. Laitoin teksitiedoston sisään seuraavan kuvassa näkyvän sisällön. 

![kuva1](/images/kuva1.png)

tekstitiedostossa oleva #!/bin/bash millä ohjelmalla skripti ajetaan.

tiedoston sisällä olevia komentoja voidaan testata tässä vaiheessa komennolla bash ./huomenta

![kuva2](/images/kuva2.png)

seuraavaksi muutin tiedoston oikeuksia chmod komennolla. Annoin tekstitiedostolle luku- ja ajamisoikeudet komennolla:

	sudo chmod 755 huomenta

Lopukis tekstitiedosto täytyy kopioida /usr/local/bin kansioon, jotta sen voi ajaa mistä vain. Kopioinnin jälkeen ajoin komennon ja sain saman tuloksen kuin aiemmin. 

![kuva3](/images/kuva3.png)

Toimii. Tein seuraavaksi salttiin kansion huomenta ja sinne init.sls tiedoston. Kopioin myös huomenta tekstitiedoston salttiin. 

![kuva4](/images/kuva4.png)

	sudo salt '*' state.apply huomenta

![kuva5](/images/kuva5.png)

Kokeilin orjalla komentoa ja tuli sama tulos. Kuvankaappaus vielä /usr/local/bin kansiosta

![kuva6](/images/kuva6.png)



## b) Tee järjestelmään uusi komento, joka kertoo ajankohtaisia tietoja.

Tein tehtävän samaa kaavaa noudattamalla kuin edellisessä tehtävässä. tein siis tekstitiedoston, jonka nimi on moikka ja laitoin sen sisälle seuraavan sisällön: 

![kuva7](/images/kuva7.png)

Curl komennon löysin [netistä](https://ostechnix.com/check-weather-details-command-line-linux/).

Annoin oikeudet tiedostolle ja kopion sen /usr/local/bin kansioon. testasin toimivuutta ja sain oikean tulosteen. 

Tein sen jälkeen salttiin taas kansion whatsup ja sinne init.sls tiedoston. Kopion source tiedoston salttiin ja ajoin tilan. Succeeded. 

Testasin vielä komentoa orjalla. 

![kuva8](/images/kuva8.png)

## c) Tee järjestelmään uusi komento pythonilla

Tein uuden tiedoston nimeltä heipython. Python täytyy kirjoittaa python koodikielellä. Python skriptissä #! jälkeen laitetaan bashin sijaan python3

![kuva9](/images/kuva9.png)

Päivitin tiedoston oikeudet:

	sudo chmod 755 heipython

kopioin tiedoston /usr/local/bin kansioon ja kokeilin sitä. 

![kuva10](/images/kuva10.png)

Tein init.sls tiedoston samalla tavalla kuin a-kohdassa. ajoin tilan saltilla, joka onnistui. kokeilin vielä komentoa, joka toimi.

## d) Tee kansio, josta jokainen skripti kopiotuu orjille

Aloitin tehtävän tekemisen luomalla salttiin kansion bins. Tein kansiion toisen kansion bin ja init.sls tiedoston. init.sls tiedoston sisältö. 

![kuva11](/images/kuva11.png)

Laitoin alunperin vain mode: init.sls tiedostoon ja salt herjasi, että file.recurse vaatii file_mode: syntaksin. Laitoin seuraavaksi bin kansioon aiemmissa tehtävissä luodut tekstitiedostot ja kävin poistamassa ne /usr/local/bin kansiosta. Ajoin tilan:

![kuva12](/images/kuva12.png)

Komennot olivat tullut takaisin /usr/local/bin kansioon. Komennot myös toimivat.

## e) Etsi loppuprojekteja ja testaa niistä yhtä.

Ensimmäinen loppuprojekti, jota tutkiskelin oli [Arne Bäcklundin projekti](https://github.com/bgj377/Lychee-projekti) moduulista, joka helpottaa lychee sovelluksen käyttöä.

Seuraavaksi katselin [Anders Gustav Lindbladin projektityötä.](https://koodiprojektit.wordpress.com/h7-oma-projekti/) Projektityössä oli tarkoituksena tehdä moduuli, joka asentaa lamp stackin osat, luo skriptejä ja ajaa ne minioneille. 

Lopuksi törmäsin [Tommi Muhosen projektitöhön](https://tommimuhonen334781833.wordpress.com/palvelinten-hallinta-harjoitus-7/), jossa oli tarkoituksena tehdä moduuli, joka konffaa ufw, apache ja ssh sovellukset. 

Valitsin itse testattavaksi työksi Tommi Muhosen projektin, koska siinä on hyviä perusasetuksia, joista on hyötyä.

Aloitin tekemällä saltin rakenteen Tommi Muhosen tree kuvankaappauksen avulla. 

![kuva13](/images/kuva13.png)

Päätin keskittyä ufw konfiguroimiseen. Tein init.sls tiedoston ufw kansioon. Nappasin init.sls tiedoston Tommin raportissa olleesta kuvankaappauksesta:

![kuva18](/images/kuva18.png)

Testasin ajamalla tilan kahteen kertaan, joten näen, että toimiko idempotenssi. 

![kuva15](/images/kuva15.png)

![kuva16](/images/kuva16.png)

![kuva17](/images/kuva17.png)

Idempotenssi toimii testataan vielä ovatko portit auki

![kuva14](/images/kuva14.png)

ufw on päällä, portit auki ja idempotenssi toimii.

## Lähteet

Ostechnix 2016. How to check weather details from command line in linux. luettavissa: https://ostechnix.com/check-weather-details-command-line-linux/

https://github.com/bgj377/Lychee-projekti

https://koodiprojektit.wordpress.com/h7-oma-projekti/

https://tommimuhonen334781833.wordpress.com/palvelinten-hallinta-harjoitus-7/
