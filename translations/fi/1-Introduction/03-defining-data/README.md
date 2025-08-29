<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "356d12cffc3125db133a2d27b827a745",
  "translation_date": "2025-08-26T21:38:48+00:00",
  "source_file": "1-Introduction/03-defining-data/README.md",
  "language_code": "fi"
}
-->
# Määritellään dataa

|![ Sketchnote by [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/03-DefiningData.png)|
|:---:|
|Datan määrittely - _Sketchnote by [@nitya](https://twitter.com/nitya)_ |

Data on faktoja, tietoa, havaintoja ja mittauksia, joita käytetään löytöjen tekemiseen ja perusteltujen päätösten tukemiseen. Datapiste on yksittäinen datayksikkö datasetissä, joka on kokoelma datapisteitä. Datasetit voivat olla eri muodoissa ja rakenteissa, ja ne perustuvat yleensä niiden lähteeseen eli siihen, mistä data on peräisin. Esimerkiksi yrityksen kuukausitulot voivat olla taulukkolaskentatiedostossa, mutta älykellon tuntikohtaiset syketiedot voivat olla [JSON](https://stackoverflow.com/a/383699)-muodossa. On yleistä, että data-analyytikot työskentelevät erilaisten datatyyppien kanssa samassa datasetissä.

Tämä oppitunti keskittyy datan tunnistamiseen ja luokitteluun sen ominaisuuksien ja lähteiden perusteella.

## [Esiluentavisa](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/4)
## Miten dataa kuvataan

### Raakadata
Raakadata on dataa, joka on peräisin lähteestään alkuperäisessä muodossaan eikä sitä ole analysoitu tai järjestetty. Jotta datasetistä saataisiin selkoa, se täytyy järjestää sellaiseen muotoon, joka on ymmärrettävissä sekä ihmisille että teknologialle, jota käytetään sen jatkoanalysointiin. Datasetin rakenne kuvaa, miten se on järjestetty, ja se voidaan luokitella rakenteelliseksi, rakenteettomaksi ja puolirakenteelliseksi. Näiden rakenteiden tyypit vaihtelevat lähteen mukaan, mutta ne kuuluvat lopulta johonkin näistä kolmesta kategoriasta.

### Kvantitatiivinen data
Kvantitatiivinen data on datasetin numeerisia havaintoja, joita voidaan yleensä analysoida, mitata ja käyttää matemaattisesti. Esimerkkejä kvantitatiivisesta datasta ovat: maan väkiluku, henkilön pituus tai yrityksen neljännesvuosittaiset tulot. Lisäanalyysin avulla kvantitatiivista dataa voitaisiin käyttää esimerkiksi ilmanlaatuindeksin (AQI) kausitrendien löytämiseen tai arvioimaan ruuhka-ajan liikenteen todennäköisyyttä tavallisena työpäivänä.

### Kvalitatiivinen data
Kvalitatiivinen data, joka tunnetaan myös kategorisena datana, on dataa, jota ei voida mitata objektiivisesti kuten kvantitatiivista dataa. Se on yleensä subjektiivista dataa, joka kuvaa jonkin asian laatua, kuten tuotetta tai prosessia. Joskus kvalitatiivinen data on numeerista, mutta sitä ei yleensä käytetä matemaattisesti, kuten puhelinnumerot tai aikaleimat. Esimerkkejä kvalitatiivisesta datasta ovat: videokommentit, auton merkki ja malli tai lähimpien ystäviesi lempiväri. Kvalitatiivista dataa voitaisiin käyttää esimerkiksi ymmärtämään, mistä tuotteista kuluttajat pitävät eniten, tai tunnistamaan suosittuja avainsanoja työhakemuksista.

### Rakenteellinen data
Rakenteellinen data on dataa, joka on järjestetty riveihin ja sarakkeisiin, joissa jokaisella rivillä on sama sarakejoukko. Sarakkeet edustavat tietyn tyyppistä arvoa ja ne tunnistetaan nimellä, joka kuvaa, mitä arvo edustaa, kun taas rivit sisältävät varsinaiset arvot. Sarakkeilla on usein tiettyjä sääntöjä tai rajoituksia arvoille, jotta varmistetaan, että arvot edustavat saraketta oikein. Esimerkiksi kuvittele asiakastaulukko, jossa jokaisella rivillä täytyy olla puhelinnumero, eikä puhelinnumerot saa sisältää aakkosmerkkejä. Puhelinnumerosarakkeeseen voidaan soveltaa sääntöjä, jotta se ei koskaan ole tyhjä ja sisältää vain numeroita.

Rakenteellisen datan etuna on, että se voidaan järjestää siten, että se voidaan yhdistää muuhun rakenteelliseen dataan. Koska data on kuitenkin suunniteltu järjestettäväksi tietyllä tavalla, sen rakenteen muuttaminen voi vaatia paljon työtä. Esimerkiksi jos asiakastaulukkoon lisätään sähköpostisarakke, joka ei voi olla tyhjä, täytyy selvittää, miten nämä arvot lisätään olemassa oleviin asiakasriveihin datasetissä.

Esimerkkejä rakenteellisesta datasta: taulukkolaskentatiedostot, relaatiotietokannat, puhelinnumerot, tiliotteet.

### Rakenteeton data
Rakenteeton data ei yleensä sovi riveihin tai sarakkeisiin eikä sisällä muotoa tai sääntöjä, joita noudattaa. Koska rakenteettomalla datalla on vähemmän rajoituksia rakenteelleen, uuden tiedon lisääminen on helpompaa verrattuna rakenteelliseen dataan. Jos esimerkiksi anturi, joka tallentaa ilmanpaineen tietoja kahden minuutin välein, saa päivityksen, joka mahdollistaa lämpötilan mittaamisen ja tallentamisen, olemassa olevaa dataa ei tarvitse muokata, jos se on rakenteetonta. Tämä voi kuitenkin tehdä tällaisen datan analysoinnista tai tutkimisesta hitaampaa. Esimerkiksi tutkija, joka haluaa löytää anturin datasta edellisen kuukauden keskilämpötilan, mutta huomaa, että anturi on tallentanut joihinkin tietoihin "e" merkiksi siitä, että se oli rikki, mikä tarkoittaa, että data on puutteellista.

Esimerkkejä rakenteettomasta datasta: tekstitiedostot, tekstiviestit, videotiedostot.

### Puolirakenteellinen data
Puolirakenteellisellä datalla on piirteitä, jotka tekevät siitä yhdistelmän rakenteellista ja rakenteetonta dataa. Se ei yleensä noudata rivi- ja sarakemuotoa, mutta se on järjestetty tavalla, jota pidetään rakenteellisena, ja se voi noudattaa kiinteää muotoa tai sääntöjä. Rakenne vaihtelee lähteiden välillä, kuten hyvin määritellystä hierarkiasta joustavampaan muotoon, joka mahdollistaa uuden tiedon helpon integroinnin. Metadata on indikaattoreita, jotka auttavat päättämään, miten data on järjestetty ja tallennettu, ja niillä on erilaisia nimiä datatyypistä riippuen. Joitakin yleisiä metadatan nimiä ovat tagit, elementit, entiteetit ja attribuutit. Esimerkiksi tyypillisessä sähköpostiviestissä on aihe, runko ja vastaanottajat, ja se voidaan järjestää sen mukaan, kenelle tai milloin se on lähetetty.

Esimerkkejä puolirakenteellisestä datasta: HTML, CSV-tiedostot, JavaScript Object Notation (JSON).

## Datan lähteet

Datalähde on alkuperäinen sijainti, jossa data on luotu tai missä se "asuu", ja se vaihtelee sen mukaan, miten ja milloin se on kerätty. Käyttäjien tuottamaa dataa kutsutaan primääridataksi, kun taas sekundääridata tulee lähteestä, joka on kerännyt dataa yleiseen käyttöön. Esimerkiksi ryhmä tutkijoita, jotka keräävät havaintoja sademetsässä, olisi primääridataa, ja jos he päättävät jakaa sen muiden tutkijoiden kanssa, se olisi sekundääridataa niille, jotka sitä käyttävät.

Tietokannat ovat yleinen lähde ja ne käyttävät tietokannan hallintajärjestelmää datan isännöintiin ja ylläpitoon, jossa käyttäjät käyttävät komentoja, joita kutsutaan kyselyiksi, datan tutkimiseen. Tiedostot datalähteinä voivat olla ääni-, kuva- ja videotiedostoja sekä taulukkolaskentatiedostoja, kuten Excel. Internetlähteet ovat yleinen sijainti datan isännöintiin, jossa tietokantoja ja tiedostoja voi löytyä. Sovellusohjelmointirajapinnat, jotka tunnetaan myös nimellä API:t, mahdollistavat ohjelmoijien luoda tapoja jakaa dataa ulkoisille käyttäjille internetin kautta, kun taas web-scraping-prosessi poimii dataa verkkosivulta. [Oppitunnit datan käsittelystä](../../../../../../../../../2-Working-With-Data) keskittyvät siihen, miten käyttää erilaisia datalähteitä.

## Yhteenveto

Tässä oppitunnissa opimme:

- Mitä data on
- Miten dataa kuvataan
- Miten dataa luokitellaan ja kategorisoidaan
- Mistä dataa voi löytää

## 🚀 Haaste

Kaggle on erinomainen lähde avoimille dataseteille. Käytä [dataset-hakutyökalua](https://www.kaggle.com/datasets) löytääksesi mielenkiintoisia datasettejä ja luokittele 3-5 datasettiä seuraavien kriteerien mukaan:

- Onko data kvantitatiivista vai kvalitatiivista?
- Onko data rakenteellista, rakenteetonta vai puolirakenteellista?

## [Jälkiluentavisa](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/5)

## Kertaus ja itseopiskelu

- Tämä Microsoft Learn -yksikkö, nimeltään [Classify your Data](https://docs.microsoft.com/en-us/learn/modules/choose-storage-approach-in-azure/2-classify-data), sisältää yksityiskohtaisen erittelyn rakenteellisesta, puolirakenteellisesta ja rakenteettomasta datasta.

## Tehtävä

[Datasetin luokittelu](assignment.md)

---

**Vastuuvapauslauseke**:  
Tämä asiakirja on käännetty käyttämällä tekoälypohjaista käännöspalvelua [Co-op Translator](https://github.com/Azure/co-op-translator). Vaikka pyrimme tarkkuuteen, huomioithan, että automaattiset käännökset voivat sisältää virheitä tai epätarkkuuksia. Alkuperäinen asiakirja sen alkuperäisellä kielellä tulisi pitää ensisijaisena lähteenä. Kriittisen tiedon osalta suositellaan ammattimaista ihmiskäännöstä. Emme ole vastuussa väärinkäsityksistä tai virhetulkinnoista, jotka johtuvat tämän käännöksen käytöstä.