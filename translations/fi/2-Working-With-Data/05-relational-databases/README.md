<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "870a0086adbc313a8eea5489bdcb2522",
  "translation_date": "2025-08-26T20:50:44+00:00",
  "source_file": "2-Working-With-Data/05-relational-databases/README.md",
  "language_code": "fi"
}
-->
# Työskentely datan kanssa: Relaatiotietokannat

|![ Sketchnote by [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/05-RelationalData.png)|
|:---:|
| Työskentely datan kanssa: Relaatiotietokannat - _Sketchnote by [@nitya](https://twitter.com/nitya)_ |

Todennäköisesti olet aiemmin käyttänyt taulukkolaskentaohjelmaa tiedon tallentamiseen. Sinulla oli rivejä ja sarakkeita, joissa rivit sisälsivät tiedot (tai datan) ja sarakkeet kuvasivat tietoa (joskus kutsutaan metadataksi). Relaatiotietokanta perustuu tähän perusperiaatteeseen, jossa taulukot koostuvat riveistä ja sarakkeista, mahdollistaen tiedon jakamisen useisiin taulukoihin. Tämä mahdollistaa monimutkaisemman datan käsittelyn, päällekkäisyyksien välttämisen ja joustavuuden datan tutkimisessa. Tutustutaan relaatiotietokannan käsitteisiin.

## [Esiluennon kysely](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/8)

## Kaikki alkaa taulukoista

Relaatiotietokannan ydin on taulukot. Kuten taulukkolaskennassa, taulukko on kokoelma rivejä ja sarakkeita. Rivi sisältää datan tai tiedon, jonka kanssa haluamme työskennellä, kuten kaupungin nimi tai sademäärä. Sarakkeet kuvaavat tallennettavaa dataa.

Aloitetaan tutkimalla taulukkoa, joka tallentaa tietoa kaupungeista. Voisimme aloittaa niiden nimellä ja maalla. Voisit tallentaa tämän taulukkoon seuraavasti:

| Kaupunki | Maa           |
| -------- | ------------- |
| Tokio    | Japani        |
| Atlanta  | Yhdysvallat   |
| Auckland | Uusi-Seelanti |

Huomaa, että sarakenimet **kaupunki**, **maa** ja **väkiluku** kuvaavat tallennettavaa dataa, ja jokainen rivi sisältää tiedot yhdestä kaupungista.

## Yhden taulukon lähestymistavan puutteet

Taulukko yllä näyttää todennäköisesti melko tutulta. Lisätään nyt lisää dataa kasvavaan tietokantaamme - vuotuinen sademäärä (millimetreinä). Keskitytään vuosiin 2018, 2019 ja 2020. Jos lisäisimme tiedot Tokiosta, se voisi näyttää tältä:

| Kaupunki | Maa     | Vuosi | Määrä  |
| -------- | ------- | ----- | ------ |
| Tokio    | Japani  | 2020  | 1690   |
| Tokio    | Japani  | 2019  | 1874   |
| Tokio    | Japani  | 2018  | 1445   |

Mitä huomaat taulukostamme? Saatat huomata, että toistamme kaupungin nimen ja maan uudelleen ja uudelleen. Tämä voi viedä paljon tallennustilaa ja on suurelta osin tarpeetonta. Loppujen lopuksi Tokion nimi ei muutu.

Kokeillaan jotain muuta. Lisätään uusia sarakkeita jokaiselle vuodelle:

| Kaupunki | Maa           | 2018 | 2019 | 2020 |
| -------- | ------------- | ---- | ---- | ---- |
| Tokio    | Japani        | 1445 | 1874 | 1690 |
| Atlanta  | Yhdysvallat   | 1779 | 1111 | 1683 |
| Auckland | Uusi-Seelanti | 1386 | 942  | 1176 |

Vaikka tämä välttää rivien toistamisen, se tuo mukanaan muita haasteita. Meidän pitäisi muokata taulukon rakennetta aina, kun tulee uusi vuosi. Lisäksi, kun datamme kasvaa, vuosien käyttäminen sarakkeina tekee arvojen hakemisesta ja laskemisesta hankalampaa.

Tämän vuoksi tarvitsemme useita taulukoita ja suhteita. Jakamalla datan osiin voimme välttää päällekkäisyyksiä ja saada enemmän joustavuutta datan käsittelyyn.

## Suhteiden käsitteet

Palataan dataamme ja mietitään, miten haluamme jakaa sen. Tiedämme, että haluamme tallentaa kaupunkien nimet ja maat, joten tämä toimii todennäköisesti parhaiten yhdessä taulukossa.

| Kaupunki | Maa           |
| -------- | ------------- |
| Tokio    | Japani        |
| Atlanta  | Yhdysvallat   |
| Auckland | Uusi-Seelanti |

Mutta ennen kuin luomme seuraavan taulukon, meidän täytyy päättää, miten viittaamme jokaiseen kaupunkiin. Tarvitsemme jonkinlaisen tunnisteen, ID:n tai (teknisessä tietokantatermistössä) pääavaimen. Pääavain on arvo, jota käytetään yhden tietyn rivin tunnistamiseen taulukossa. Vaikka tämä voisi perustua itse arvoon (voisimme käyttää kaupungin nimeä esimerkiksi), sen pitäisi lähes aina olla numero tai muu tunniste. Emme halua, että ID muuttuu koskaan, sillä se rikkoisi suhteen. Useimmissa tapauksissa pääavain tai ID on automaattisesti luotu numero.

> ✅ Pääavain lyhennetään usein PK

### kaupungit

| city_id | Kaupunki | Maa           |
| ------- | -------- | ------------- |
| 1       | Tokio    | Japani        |
| 2       | Atlanta  | Yhdysvallat   |
| 3       | Auckland | Uusi-Seelanti |

> ✅ Huomaat, että käytämme termejä "id" ja "pääavain" vuorotellen tämän oppitunnin aikana. Käsitteet pätevät myös DataFrameihin, joihin tutustut myöhemmin. DataFramet eivät käytä termiä "pääavain", mutta huomaat niiden käyttäytyvän hyvin samalla tavalla.

Kun kaupunkien taulukko on luotu, tallennetaan sademäärä. Sen sijaan, että toistaisimme kaupungin täydelliset tiedot, voimme käyttää ID:tä. Meidän tulisi myös varmistaa, että juuri luodulla taulukolla on *id*-sarake, sillä kaikilla taulukoilla tulisi olla ID tai pääavain.

### sademäärä

| rainfall_id | city_id | Vuosi | Määrä  |
| ----------- | ------- | ----- | ------ |
| 1           | 1       | 2018  | 1445   |
| 2           | 1       | 2019  | 1874   |
| 3           | 1       | 2020  | 1690   |
| 4           | 2       | 2018  | 1779   |
| 5           | 2       | 2019  | 1111   |
| 6           | 2       | 2020  | 1683   |
| 7           | 3       | 2018  | 1386   |
| 8           | 3       | 2019  | 942    |
| 9           | 3       | 2020  | 1176   |

Huomaa **city_id**-sarake juuri luodussa **sademäärä**-taulukossa. Tämä sarake sisältää arvoja, jotka viittaavat **kaupungit**-taulukon ID:ihin. Teknisen relaatiodatan termeissä tätä kutsutaan **vierasavaimeksi**; se on pääavain toisesta taulukosta. Voit ajatella sitä viittauksena tai osoittimena. **city_id** 1 viittaa Tokioon.

> [!NOTE] Vierasavain lyhennetään usein FK

## Datan hakeminen

Kun datamme on jaettu kahteen taulukkoon, saatat miettiä, miten sen voi hakea. Jos käytämme relaatiotietokantaa, kuten MySQL, SQL Server tai Oracle, voimme käyttää kieltä nimeltä Structured Query Language eli SQL. SQL (joskus lausutaan "sequel") on standardikieli, jota käytetään datan hakemiseen ja muokkaamiseen relaatiotietokannassa.

Datan hakemiseen käytetään komentoa `SELECT`. Perusperiaatteena on, että **valitset** sarakkeet, jotka haluat nähdä, **taulukosta**, jossa ne sijaitsevat. Jos haluaisit näyttää vain kaupunkien nimet, voisit käyttää seuraavaa:

```sql
SELECT city
FROM cities;

-- Output:
-- Tokyo
-- Atlanta
-- Auckland
```

`SELECT` on kohta, jossa luetellaan sarakkeet, ja `FROM` on kohta, jossa luetellaan taulukot.

> [NOTE] SQL-syntaksi ei ole kirjainkoolle herkkä, eli `select` ja `SELECT` tarkoittavat samaa. Kuitenkin riippuen käyttämästäsi tietokantatyypistä sarakkeet ja taulukot voivat olla kirjainkoolle herkkiä. Tämän vuoksi on hyvä käytäntö aina käsitellä kaikkea ohjelmoinnissa kuin se olisi kirjainkoolle herkkää. Kun kirjoitat SQL-kyselyitä, yleinen tapa on kirjoittaa avainsanat kokonaan isoilla kirjaimilla.

Yllä oleva kysely näyttää kaikki kaupungit. Kuvitellaan, että haluaisimme näyttää vain Uuden-Seelannin kaupungit. Tarvitsemme jonkinlaisen suodattimen. SQL-avainsana tähän on `WHERE`, eli "missä jokin on totta".

```sql
SELECT city
FROM cities
WHERE country = 'New Zealand';

-- Output:
-- Auckland
```

## Datan yhdistäminen

Tähän asti olemme hakeneet dataa yhdestä taulukosta. Nyt haluamme yhdistää datan molemmista **kaupungit**- ja **sademäärä**-taulukoista. Tämä tehdään *yhdistämällä* ne. Käytännössä luot saumakohdan kahden taulukon välille ja yhdistät arvot sarakkeesta kummastakin taulukosta.

Esimerkissämme yhdistämme **city_id**-sarakkeen **sademäärä**-taulukossa **city_id**-sarakkeeseen **kaupungit**-taulukossa. Tämä yhdistää sademäärän sen vastaavaan kaupunkiin. Suoritamme *sisäisen* yhdistämisen, mikä tarkoittaa, että jos rivit eivät vastaa mitään toisesta taulukosta, niitä ei näytetä. Meidän tapauksessamme jokaisella kaupungilla on sademäärä, joten kaikki näytetään.

Haetaan vuoden 2019 sademäärä kaikille kaupungeille.

Teemme tämän vaiheittain. Ensimmäinen vaihe on yhdistää data ilmoittamalla saumakohdan sarakkeet - **city_id**, kuten aiemmin korostettiin.

```sql
SELECT cities.city
    rainfall.amount
FROM cities
    INNER JOIN rainfall ON cities.city_id = rainfall.city_id
```

Olemme korostaneet kaksi saraketta, jotka haluamme, ja sen, että haluamme yhdistää taulukot **city_id**:n avulla. Nyt voimme lisätä `WHERE`-lauseen suodattamaan vain vuoden 2019.

```sql
SELECT cities.city
    rainfall.amount
FROM cities
    INNER JOIN rainfall ON cities.city_id = rainfall.city_id
WHERE rainfall.year = 2019

-- Output

-- city     | amount
-- -------- | ------
-- Tokyo    | 1874
-- Atlanta  | 1111
-- Auckland |  942
```

## Yhteenveto

Relaatiotietokannat keskittyvät tiedon jakamiseen useisiin taulukoihin, jotka tuodaan takaisin yhteen näyttämistä ja analysointia varten. Tämä tarjoaa suuren joustavuuden laskelmien tekemiseen ja datan muokkaamiseen. Olet nähnyt relaatiotietokannan peruskäsitteet ja miten suorittaa yhdistäminen kahden taulukon välillä.

## 🚀 Haaste

Internetissä on lukuisia relaatiotietokantoja. Voit tutkia dataa käyttämällä yllä oppimiasi taitoja.

## Luennon jälkeinen kysely

## [Luennon jälkeinen kysely](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/9)

## Kertaus ja itseopiskelu

Microsoft Learn -sivustolla on useita resursseja, joiden avulla voit jatkaa SQL:n ja relaatiotietokannan käsitteiden tutkimista.

- [Relaatiodatan käsitteiden kuvaaminen](https://docs.microsoft.com//learn/modules/describe-concepts-of-relational-data?WT.mc_id=academic-77958-bethanycheum)
- [Aloita kyselyt Transact-SQL:llä](https://docs.microsoft.com//learn/paths/get-started-querying-with-transact-sql?WT.mc_id=academic-77958-bethanycheum) (Transact-SQL on SQL:n versio)
- [SQL-sisältö Microsoft Learnissa](https://docs.microsoft.com/learn/browse/?products=azure-sql-database%2Csql-server&expanded=azure&WT.mc_id=academic-77958-bethanycheum)

## Tehtävä

[Tehtävän otsikko](assignment.md)

---

**Vastuuvapauslauseke**:  
Tämä asiakirja on käännetty käyttämällä tekoälypohjaista käännöspalvelua [Co-op Translator](https://github.com/Azure/co-op-translator). Vaikka pyrimme tarkkuuteen, huomioithan, että automaattiset käännökset voivat sisältää virheitä tai epätarkkuuksia. Alkuperäistä asiakirjaa sen alkuperäisellä kielellä tulisi pitää ensisijaisena lähteenä. Kriittisen tiedon osalta suositellaan ammattimaista ihmiskäännöstä. Emme ole vastuussa tämän käännöksen käytöstä johtuvista väärinkäsityksistä tai virhetulkinnoista.