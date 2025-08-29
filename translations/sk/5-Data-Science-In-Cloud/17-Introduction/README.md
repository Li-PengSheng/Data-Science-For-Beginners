<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "408c55cab2880daa4e78616308bd5db7",
  "translation_date": "2025-08-26T16:07:15+00:00",
  "source_file": "5-Data-Science-In-Cloud/17-Introduction/README.md",
  "language_code": "sk"
}
-->
# Úvod do dátovej vedy v cloude

|![ Sketchnote od [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/17-DataScience-Cloud.png)|
|:---:|
| Dátová veda v cloude: Úvod - _Sketchnote od [@nitya](https://twitter.com/nitya)_ |

V tejto lekcii sa naučíte základné princípy cloudu, zistíte, prečo môže byť pre vás zaujímavé využívať cloudové služby na realizáciu vašich projektov dátovej vedy, a pozrieme sa na niekoľko príkladov projektov dátovej vedy realizovaných v cloude.

## [Kvíz pred prednáškou](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/32)

## Čo je cloud?

Cloud, alebo cloud computing, je poskytovanie širokej škály výpočtových služieb na báze platby za použitie, ktoré sú hostované na infraštruktúre cez internet. Služby zahŕňajú riešenia ako úložisko, databázy, siete, softvér, analytiku a inteligentné služby.

Zvyčajne rozlišujeme verejný, súkromný a hybridný cloud nasledovne:

* Verejný cloud: verejný cloud je vlastnený a prevádzkovaný treťou stranou, poskytovateľom cloudových služieb, ktorý dodáva svoje výpočtové zdroje cez internet verejnosti.
* Súkromný cloud: označuje cloudové výpočtové zdroje používané výlučne jednou firmou alebo organizáciou, pričom služby a infraštruktúra sú udržiavané na súkromnej sieti.
* Hybridný cloud: hybridný cloud je systém, ktorý kombinuje verejné a súkromné cloudy. Používatelia si zvolia dátové centrum na mieste, pričom umožňujú spúšťanie dát a aplikácií na jednom alebo viacerých verejných cloudoch.

Väčšina cloudových výpočtových služieb spadá do troch kategórií: infraštruktúra ako služba (IaaS), platforma ako služba (PaaS) a softvér ako služba (SaaS).

* Infraštuktúra ako služba (IaaS): používatelia si prenajímajú IT infraštruktúru, ako sú servery a virtuálne stroje (VM), úložisko, siete, operačné systémy.
* Platforma ako služba (PaaS): používatelia si prenajímajú prostredie na vývoj, testovanie, doručovanie a správu softvérových aplikácií. Nemusia sa starať o nastavenie alebo správu základnej infraštruktúry serverov, úložísk, sietí a databáz potrebných na vývoj.
* Softvér ako služba (SaaS): používatelia získavajú prístup k softvérovým aplikáciám cez internet, na požiadanie a zvyčajne na základe predplatného. Nemusia sa starať o hosting a správu softvérovej aplikácie, základnej infraštruktúry alebo údržby, ako sú aktualizácie softvéru a bezpečnostné záplaty.

Medzi najväčších poskytovateľov cloudu patria Amazon Web Services, Google Cloud Platform a Microsoft Azure.

## Prečo si vybrať cloud pre dátovú vedu?

Vývojári a IT profesionáli si vyberajú prácu s cloudom z mnohých dôvodov, vrátane nasledujúcich:

* Inovácie: môžete poháňať svoje aplikácie integráciou inovatívnych služieb vytvorených poskytovateľmi cloudu priamo do svojich aplikácií.
* Flexibilita: platíte iba za služby, ktoré potrebujete, a môžete si vybrať z širokej škály služieb. Zvyčajne platíte podľa potreby a prispôsobujete svoje služby podľa svojich vyvíjajúcich sa potrieb.
* Rozpočet: nemusíte robiť počiatočné investície na nákup hardvéru a softvéru, nastavenie a prevádzku dátových centier na mieste, a môžete jednoducho platiť za to, čo používate.
* Škálovateľnosť: vaše zdroje sa môžu prispôsobiť potrebám vášho projektu, čo znamená, že vaše aplikácie môžu využívať viac alebo menej výpočtového výkonu, úložiska a šírky pásma, prispôsobujúc sa externým faktorom v danom čase.
* Produktivita: môžete sa sústrediť na svoje podnikanie namiesto trávenia času úlohami, ktoré môže spravovať niekto iný, ako je správa dátových centier.
* Spoľahlivosť: cloud computing ponúka niekoľko spôsobov, ako nepretržite zálohovať vaše dáta, a môžete si nastaviť plány obnovy po havárii, aby ste udržali svoje podnikanie a služby v chode aj v čase krízy.
* Bezpečnosť: môžete ťažiť z politík, technológií a kontrol, ktoré posilňujú bezpečnosť vášho projektu.

Toto sú niektoré z najbežnejších dôvodov, prečo sa ľudia rozhodujú používať cloudové služby. Teraz, keď máme lepšie pochopenie toho, čo je cloud a aké sú jeho hlavné výhody, pozrime sa konkrétnejšie na prácu dátových vedcov a vývojárov pracujúcich s dátami a na to, ako im cloud môže pomôcť s viacerými výzvami, ktorým môžu čeliť:

* Ukladanie veľkého množstva dát: namiesto nákupu, správy a ochrany veľkých serverov môžete svoje dáta ukladať priamo v cloude, s riešeniami ako Azure Cosmos DB, Azure SQL Database a Azure Data Lake Storage.
* Vykonávanie integrácie dát: integrácia dát je nevyhnutnou súčasťou dátovej vedy, ktorá vám umožňuje prejsť od zberu dát k prijímaniu opatrení. Služby integrácie dát ponúkané v cloude vám umožňujú zbierať, transformovať a integrovať dáta z rôznych zdrojov do jedného dátového skladu, s Data Factory.
* Spracovanie dát: spracovanie obrovského množstva dát vyžaduje veľa výpočtového výkonu, a nie každý má prístup k dostatočne výkonným strojom, čo je dôvod, prečo sa mnohí rozhodnú priamo využiť obrovský výpočtový výkon cloudu na spúšťanie a nasadzovanie svojich riešení.
* Používanie analytických služieb: cloudové služby ako Azure Synapse Analytics, Azure Stream Analytics a Azure Databricks vám pomáhajú premeniť vaše dáta na použiteľné poznatky.
* Používanie služieb strojového učenia a dátovej inteligencie: namiesto začínania od nuly môžete používať algoritmy strojového učenia ponúkané poskytovateľom cloudu, so službami ako AzureML. Môžete tiež používať kognitívne služby, ako je prevod reči na text, text na reč, počítačové videnie a ďalšie.

## Príklady dátovej vedy v cloude

Poďme si to priblížiť na niekoľkých scenároch.

### Analýza sentimentu na sociálnych sieťach v reálnom čase
Začneme scenárom, ktorý je často študovaný ľuďmi začínajúcimi so strojovým učením: analýza sentimentu na sociálnych sieťach v reálnom čase.

Predstavte si, že prevádzkujete spravodajský web a chcete využiť živé dáta na pochopenie toho, o aký obsah by mohli mať vaši čitatelia záujem. Aby ste to zistili, môžete vytvoriť program, ktorý vykonáva analýzu sentimentu v reálnom čase na dátach zverejnených na Twitteri, na témy, ktoré sú pre vašich čitateľov relevantné.

Kľúčové ukazovatele, na ktoré sa budete pozerať, sú objem tweetov na konkrétne témy (hashtagy) a sentiment, ktorý sa určuje pomocou analytických nástrojov vykonávajúcich analýzu sentimentu na špecifikované témy.

Kroky potrebné na vytvorenie tohto projektu sú nasledovné:

* Vytvorte event hub na streamovanie vstupov, ktorý bude zbierať dáta z Twitteru.
* Nakonfigurujte a spustite aplikáciu klienta Twitter, ktorá bude volať Twitter Streaming API.
* Vytvorte Stream Analytics úlohu.
* Špecifikujte vstup a dotaz úlohy.
* Vytvorte výstupný cieľ a špecifikujte výstup úlohy.
* Spustite úlohu.

Celý proces si môžete pozrieť v [dokumentácii](https://docs.microsoft.com/azure/stream-analytics/stream-analytics-twitter-sentiment-analysis-trends?WT.mc_id=academic-77958-bethanycheum&ocid=AID30411099).

### Analýza vedeckých článkov
Pozrime sa na ďalší príklad projektu, ktorý vytvoril [Dmitry Soshnikov](http://soshnikov.com), jeden z autorov tohto kurzu.

Dmitry vytvoril nástroj, ktorý analyzuje články o COVID-e. Preskúmaním tohto projektu uvidíte, ako môžete vytvoriť nástroj, ktorý extrahuje poznatky z vedeckých článkov, získava poznatky a pomáha výskumníkom efektívne sa orientovať v rozsiahlych zbierkach článkov.

Pozrime sa na rôzne kroky použité na tento účel:
* Extrahovanie a predspracovanie informácií pomocou [Text Analytics for Health](https://docs.microsoft.com/azure/cognitive-services/text-analytics/how-tos/text-analytics-for-health?WT.mc_id=academic-77958-bethanycheum&ocid=AID3041109).
* Použitie [Azure ML](https://azure.microsoft.com/services/machine-learning?WT.mc_id=academic-77958-bethanycheum&ocid=AID3041109) na paralelizáciu spracovania.
* Ukladanie a dotazovanie informácií pomocou [Cosmos DB](https://azure.microsoft.com/services/cosmos-db?WT.mc_id=academic-77958-bethanycheum&ocid=AID3041109).
* Vytvorenie interaktívneho dashboardu na prieskum a vizualizáciu dát pomocou Power BI.

Celý proces si môžete pozrieť na [Dmitryho blogu](https://soshnikov.com/science/analyzing-medical-papers-with-azure-and-text-analytics-for-health/).

Ako vidíte, cloudové služby môžeme využiť mnohými spôsobmi na realizáciu dátovej vedy.

## Poznámka pod čiarou

Zdroje:
* https://azure.microsoft.com/overview/what-is-cloud-computing?ocid=AID3041109  
* https://docs.microsoft.com/azure/stream-analytics/stream-analytics-twitter-sentiment-analysis-trends?ocid=AID3041109  
* https://soshnikov.com/science/analyzing-medical-papers-with-azure-and-text-analytics-for-health/  

## Kvíz po prednáške

[Kvíz po prednáške](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/33)

## Zadanie

[Prieskum trhu](assignment.md)

---

**Upozornenie**:  
Tento dokument bol preložený pomocou služby AI prekladu [Co-op Translator](https://github.com/Azure/co-op-translator). Aj keď sa snažíme o presnosť, prosím, berte na vedomie, že automatizované preklady môžu obsahovať chyby alebo nepresnosti. Pôvodný dokument v jeho pôvodnom jazyku by mal byť považovaný za autoritatívny zdroj. Pre kritické informácie sa odporúča profesionálny ľudský preklad. Nie sme zodpovední za akékoľvek nedorozumenia alebo nesprávne interpretácie vyplývajúce z použitia tohto prekladu.