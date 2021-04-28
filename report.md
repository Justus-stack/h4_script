
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

Kokeilin orjalla komentoa ja tuli sama tulos. 

## b) whatsup.sh. Tee järjestelmään uusi komento, joka kertoo ajankohtaisia tietoja.

//todo lisää tekstiä
