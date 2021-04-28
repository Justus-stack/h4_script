
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

//tee loppuun. 

## e) Etsi loppuprojekteja ja testaa niistä yhtä.

//todo lisää tekstiä

## Lähteet

Ostechnix 2016. How to check weather details from command line in linux. luettavissa: https://ostechnix.com/check-weather-details-command-line-linux/
