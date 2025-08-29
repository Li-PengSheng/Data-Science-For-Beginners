<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "870a0086adbc313a8eea5489bdcb2522",
  "translation_date": "2025-08-26T14:28:51+00:00",
  "source_file": "2-Working-With-Data/05-relational-databases/README.md",
  "language_code": "hu"
}
-->
# Adatok kezelése: Relációs adatbázisok

|![ Sketchnote by [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/05-RelationalData.png)|
|:---:|
| Adatok kezelése: Relációs adatbázisok - _Sketchnote készítette: [@nitya](https://twitter.com/nitya)_ |

Valószínűleg már használtál korábban táblázatot információk tárolására. Volt egy sorokból és oszlopokból álló készleted, ahol a sorok tartalmazták az információkat (vagy adatokat), az oszlopok pedig leírták az információkat (ezeket néha metaadatoknak is nevezik). A relációs adatbázisok erre az alapelvre épülnek: táblázatokban oszlopok és sorok segítségével tárolják az adatokat, lehetővé téve, hogy az információ több táblázat között legyen elosztva. Ez lehetővé teszi, hogy bonyolultabb adatokat kezelj, elkerüld az adatok duplikációját, és rugalmasan vizsgáld az adatokat. Nézzük meg közelebbről a relációs adatbázisok alapfogalmait.

## [Előadás előtti kvíz](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/8)

## Minden a táblázatokkal kezdődik

A relációs adatbázisok alapját a táblázatok képezik. Akárcsak a táblázatkezelő programokban, egy tábla oszlopok és sorok gyűjteménye. A sorok tartalmazzák az adatokat vagy információkat, amelyeket kezelni szeretnénk, például egy város nevét vagy a csapadékmennyiséget. Az oszlopok leírják, hogy milyen adatokat tárolnak.

Kezdjük azzal, hogy létrehozunk egy táblát a városokkal kapcsolatos információk tárolására. Kezdhetjük például a nevükkel és az országukkal. Ezt így tárolhatnánk egy táblázatban:

| Város    | Ország         |
| -------- | ------------- |
| Tokió    | Japán         |
| Atlanta  | Egyesült Államok |
| Auckland | Új-Zéland     |

Figyeld meg, hogy az oszlopnevek, mint például **város**, **ország** és **népesség**, leírják a tárolt adatokat, és minden sor egy városról tartalmaz információt.

## Az egyetlen tábla megközelítés hiányosságai

Valószínűleg a fenti tábla ismerősnek tűnik számodra. Most adjunk hozzá néhány további adatot a növekvő adatbázisunkhoz – például az éves csapadékmennyiséget (milliméterben). Koncentráljunk a 2018-as, 2019-es és 2020-as évekre. Ha Tokióra vonatkozóan adnánk hozzá adatokat, az valahogy így nézne ki:

| Város  | Ország | Év   | Mennyiség |
| ------ | ------ | ---- | --------- |
| Tokió  | Japán  | 2020 | 1690      |
| Tokió  | Japán  | 2019 | 1874      |
| Tokió  | Japán  | 2018 | 1445      |

Mit veszel észre a táblázatunkon? Talán feltűnik, hogy a város nevét és országát újra és újra megismételjük. Ez elég sok tárhelyet foglalhat, és nagyrészt felesleges, hiszen Tokiónak csak egy neve van, ami minket érdekel.

Rendben, próbáljunk ki valami mást. Adjunk hozzá új oszlopokat minden évhez:

| Város    | Ország         | 2018 | 2019 | 2020 |
| -------- | ------------- | ---- | ---- | ---- |
| Tokió    | Japán         | 1445 | 1874 | 1690 |
| Atlanta  | Egyesült Államok | 1779 | 1111 | 1683 |
| Auckland | Új-Zéland     | 1386 | 942  | 1176 |

Bár ezzel elkerüljük a sorok duplikációját, más problémákat hozunk létre. Módosítanunk kellene a táblázat szerkezetét minden új év hozzáadásakor. Emellett, ahogy az adataink növekednek, az évek oszlopként való tárolása megnehezíti az adatok lekérdezését és számítását.

Ezért van szükségünk több táblára és kapcsolatokra. Az adatok szétválasztásával elkerülhetjük a duplikációt, és nagyobb rugalmasságot érhetünk el az adatok kezelésében.

## A kapcsolatok fogalma

Térjünk vissza az adatainkhoz, és határozzuk meg, hogyan szeretnénk szétválasztani őket. Tudjuk, hogy a városok nevét és országát szeretnénk tárolni, így ez valószínűleg egy táblában működik a legjobban.

| Város    | Ország         |
| -------- | ------------- |
| Tokió    | Japán         |
| Atlanta  | Egyesült Államok |
| Auckland | Új-Zéland     |

De mielőtt létrehoznánk a következő táblát, ki kell találnunk, hogyan hivatkozzunk az egyes városokra. Szükségünk van valamilyen azonosítóra, ID-re vagy (technikai adatbázis kifejezéssel élve) elsődleges kulcsra. Az elsődleges kulcs egy olyan érték, amely egy adott sort azonosít egy táblában. Bár ez alapulhat maga az érték (például a város neve), szinte mindig egy szám vagy más azonosító kell, hogy legyen. Nem szeretnénk, hogy az azonosító valaha is megváltozzon, mert az megszakítaná a kapcsolatot. A legtöbb esetben az elsődleges kulcs vagy azonosító automatikusan generált szám lesz.

> ✅ Az elsődleges kulcsot gyakran PK-ként rövidítik.

### városok

| város_id | Város    | Ország         |
| -------- | -------- | ------------- |
| 1        | Tokió    | Japán         |
| 2        | Atlanta  | Egyesült Államok |
| 3        | Auckland | Új-Zéland     |

> ✅ Észreveheted, hogy az "id" és az "elsődleges kulcs" kifejezéseket felváltva használjuk ebben a leckében. Ezek a fogalmak a DataFrame-ekre is vonatkoznak, amelyeket később fogsz felfedezni. A DataFrame-ek nem használják az "elsődleges kulcs" terminológiát, de hasonlóan viselkednek.

Miután létrehoztuk a városok táblát, tároljuk a csapadékmennyiséget. Ahelyett, hogy a város teljes információját duplikálnánk, használhatjuk az azonosítót. Biztosítanunk kell azt is, hogy az újonnan létrehozott táblának is legyen egy *id* oszlopa, mivel minden táblának kell, hogy legyen egy azonosítója vagy elsődleges kulcsa.

### csapadék

| csapadék_id | város_id | Év   | Mennyiség |
| ----------- | -------- | ---- | --------- |
| 1           | 1        | 2018 | 1445      |
| 2           | 1        | 2019 | 1874      |
| 3           | 1        | 2020 | 1690      |
| 4           | 2        | 2018 | 1779      |
| 5           | 2        | 2019 | 1111      |
| 6           | 2        | 2020 | 1683      |
| 7           | 3        | 2018 | 1386      |
| 8           | 3        | 2019 | 942       |
| 9           | 3        | 2020 | 1176      |

Figyeld meg a **város_id** oszlopot az újonnan létrehozott **csapadék** táblában. Ez az oszlop olyan értékeket tartalmaz, amelyek a **városok** tábla azonosítóira hivatkoznak. Technikai relációs adatbázis kifejezéssel élve ezt **idegen kulcsnak** nevezzük; ez egy másik tábla elsődleges kulcsa. Egyszerűen gondolj rá úgy, mint egy hivatkozásra vagy mutatóra. A **város_id** 1 Tokióra hivatkozik.

> [!NOTE] Az idegen kulcsot gyakran FK-ként rövidítik.

## Az adatok lekérdezése

Miután az adatainkat két táblába szétválasztottuk, felmerülhet a kérdés, hogyan kérdezzük le őket. Ha relációs adatbázist használunk, például MySQL-t, SQL Servert vagy Oracle-t, egy Structured Query Language (SQL) nevű nyelvet használhatunk. Az SQL (néha "szíkvöl"-nek ejtik) egy szabványos nyelv, amelyet adatok lekérdezésére és módosítására használnak relációs adatbázisokban.

Az adatok lekérdezéséhez a `SELECT` parancsot használjuk. Alapvetően a **select**-tel megadjuk, hogy mely oszlopokat szeretnénk látni, és a **from**-mal megadjuk, hogy melyik táblából származnak. Ha például csak a városok nevét szeretnénk megjeleníteni, a következőt használhatjuk:

```sql
SELECT city
FROM cities;

-- Output:
-- Tokyo
-- Atlanta
-- Auckland
```

A `SELECT`-ben soroljuk fel az oszlopokat, a `FROM`-ban pedig a táblákat.

> [NOTE] Az SQL szintaxis nem érzékeny a kis- és nagybetűkre, tehát a `select` és a `SELECT` ugyanazt jelenti. Azonban az adatbázis típusától függően az oszlopok és táblák neve érzékeny lehet a kis- és nagybetűkre. Ezért jó gyakorlat mindig úgy kezelni mindent a programozásban, mintha érzékeny lenne a kis- és nagybetűkre. Az SQL lekérdezések írásakor általános szokás, hogy a kulcsszavakat nagybetűvel írjuk.

A fenti lekérdezés az összes várost megjeleníti. Tegyük fel, hogy csak az Új-Zélandon található városokat szeretnénk megjeleníteni. Szükségünk van valamilyen szűrőre. Az SQL kulcsszava erre a `WHERE`, vagyis "ahol valami igaz".

```sql
SELECT city
FROM cities
WHERE country = 'New Zealand';

-- Output:
-- Auckland
```

## Adatok összekapcsolása

Eddig egyetlen táblából kérdeztünk le adatokat. Most szeretnénk az adatokat a **városok** és a **csapadék** táblákból összekapcsolni. Ezt *összekapcsolásnak* nevezzük. Lényegében egy varratot hozunk létre a két tábla között, és összeillesztjük az értékeket egy-egy oszlopból mindkét táblában.

Példánkban a **város_id** oszlopot fogjuk összeilleszteni a **csapadék** és a **városok** táblákban. Ez összekapcsolja a csapadékmennyiséget a megfelelő várossal. Az általunk végrehajtott összekapcsolás típusa egy úgynevezett *belső* összekapcsolás lesz, ami azt jelenti, hogy ha bármelyik sor nem illeszkedik a másik táblában lévő adatokhoz, akkor nem jelenik meg. Esetünkben minden városhoz tartozik csapadékadat, így minden meg fog jelenni.

Kérdezzük le a 2019-es év csapadékmennyiségét az összes városra vonatkozóan.

Ezt lépésenként fogjuk megtenni. Az első lépés az adatok összekapcsolása az oszlopok varratainak megadásával – a korábban kiemelt **város_id** oszlopokkal.

```sql
SELECT cities.city
    rainfall.amount
FROM cities
    INNER JOIN rainfall ON cities.city_id = rainfall.city_id
```

Kiemeltük a két oszlopot, amelyeket szeretnénk, és azt, hogy a táblákat a **város_id** alapján szeretnénk összekapcsolni. Most hozzáadhatjuk a `WHERE` utasítást, hogy csak a 2019-es évet szűrjük ki.

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

## Összefoglalás

A relációs adatbázisok lényege, hogy az információkat több táblába osztják szét, amelyeket aztán megjelenítés és elemzés céljából újra összehoznak. Ez nagyfokú rugalmasságot biztosít a számítások elvégzéséhez és az adatok manipulálásához. Megismerkedtél a relációs adatbázisok alapfogalmaival, és azzal, hogyan lehet összekapcsolni két táblát.

## 🚀 Kihívás

Számos relációs adatbázis érhető el az interneten. Fedezd fel az adatokat az itt tanult készségek segítségével.

## Előadás utáni kvíz

## [Előadás utáni kvíz](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/9)

## Áttekintés és önálló tanulás

Számos forrás érhető el a [Microsoft Learn](https://docs.microsoft.com/learn?WT.mc_id=academic-77958-bethanycheum) oldalon, amelyek segítségével tovább mélyítheted az SQL és a relációs adatbázisok fogalmaival kapcsolatos ismereteidet.

- [Relációs adatok fogalmainak ismertetése](https://docs.microsoft.com//learn/modules/describe-concepts-of-relational-data?WT.mc_id=academic-77958-bethanycheum)
- [Első lépések a Transact-SQL-lel](https://docs.microsoft.com//learn/paths/get-started-querying-with-transact-sql?WT.mc_id=academic-77958-bethanycheum) (A Transact-SQL az SQL egy változata)
- [SQL tartalom a Microsoft Learn oldalon](https://docs.microsoft.com/learn/browse/?products=azure-sql-database%2Csql-server&expanded=azure&WT.mc_id=academic-77958-bethanycheum)

## Feladat

[Feladat címe](assignment.md)

---

**Felelősség kizárása**:  
Ez a dokumentum az AI fordítási szolgáltatás [Co-op Translator](https://github.com/Azure/co-op-translator) segítségével lett lefordítva. Bár törekszünk a pontosságra, kérjük, vegye figyelembe, hogy az automatikus fordítások hibákat vagy pontatlanságokat tartalmazhatnak. Az eredeti dokumentum az eredeti nyelvén tekintendő hiteles forrásnak. Kritikus információk esetén javasolt professzionális emberi fordítást igénybe venni. Nem vállalunk felelősséget semmilyen félreértésért vagy téves értelmezésért, amely a fordítás használatából eredhet.