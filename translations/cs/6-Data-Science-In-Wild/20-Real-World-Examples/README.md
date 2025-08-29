<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "67076ed50f54e7d26ba1ba378d6078f1",
  "translation_date": "2025-08-26T15:46:43+00:00",
  "source_file": "6-Data-Science-In-Wild/20-Real-World-Examples/README.md",
  "language_code": "cs"
}
-->
# Data Science v reálném světě

| ![ Sketchnote od [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/20-DataScience-RealWorld.png) |
| :--------------------------------------------------------------------------------------------------------------: |
|               Data Science v reálném světě - _Sketchnote od [@nitya](https://twitter.com/nitya)_               |

Jsme téměř na konci této vzdělávací cesty!

Začali jsme definicemi data science a etiky, prozkoumali různé nástroje a techniky pro analýzu a vizualizaci dat, přezkoumali životní cyklus data science a podívali se na škálování a automatizaci pracovních postupů data science pomocí cloudových služeb. Možná si teď říkáte: _"Jak přesně mohu všechny tyto poznatky aplikovat v reálném světě?"_

V této lekci prozkoumáme reálné aplikace data science napříč průmyslem a ponoříme se do konkrétních příkladů v oblasti výzkumu, digitálních humanitních věd a udržitelnosti. Podíváme se na příležitosti studentských projektů a zakončíme užitečnými zdroji, které vám pomohou pokračovat ve vaší vzdělávací cestě!

## Kvíz před přednáškou

[Kvíz před přednáškou](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/38)

## Data Science + průmysl

Díky demokratizaci AI je pro vývojáře nyní snazší navrhovat a integrovat rozhodování řízené AI a poznatky založené na datech do uživatelských zkušeností a vývojových pracovních postupů. Zde je několik příkladů, jak je data science "aplikována" v reálných aplikacích napříč průmyslem:

 * [Google Flu Trends](https://www.wired.com/2015/10/can-learn-epic-failure-google-flu-trends/) využíval data science k propojení vyhledávacích dotazů s trendy chřipky. Přestože měl tento přístup své nedostatky, upozornil na možnosti (a výzvy) predikcí ve zdravotnictví založených na datech.

 * [Predikce tras UPS](https://www.technologyreview.com/2018/11/21/139000/how-ups-uses-ai-to-outsmart-bad-weather/) - popisuje, jak UPS využívá data science a strojové učení k predikci optimálních tras pro doručování s ohledem na povětrnostní podmínky, dopravní situaci, termíny doručení a další faktory.

 * [Vizualizace tras taxíků v NYC](http://chriswhong.github.io/nyctaxi/) - data získaná pomocí [zákonů o svobodném přístupu k informacím](https://chriswhong.com/open-data/foil_nyc_taxi/) pomohla vizualizovat denní provoz taxíků v NYC, což nám umožňuje pochopit, jak se pohybují po městě, kolik vydělávají a jak dlouho trvají jednotlivé jízdy během 24 hodin.

 * [Uber Data Science Workbench](https://eng.uber.com/dsw/) - využívá data (o místech vyzvednutí a vysazení, délce jízdy, preferovaných trasách atd.) shromážděná z milionů jízd Uberu *denně* k vytvoření analytického nástroje, který pomáhá s cenotvorbou, bezpečností, detekcí podvodů a navigačními rozhodnutími.

 * [Sportovní analytika](https://towardsdatascience.com/scope-of-analytics-in-sports-world-37ed09c39860) - zaměřuje se na _prediktivní analytiku_ (analýza týmů a hráčů - viz [Moneyball](https://datasciencedegree.wisconsin.edu/blog/moneyball-proves-importance-big-data-big-ideas/) - a řízení fanoušků) a _vizualizaci dat_ (dashboardy týmů a fanoušků, hry atd.) s aplikacemi jako skauting talentů, sportovní sázení a řízení zásob/areálů.

 * [Data Science v bankovnictví](https://data-flair.training/blogs/data-science-in-banking/) - zdůrazňuje hodnotu data science ve finančním sektoru s aplikacemi od modelování rizik a detekce podvodů po segmentaci zákazníků, predikce v reálném čase a doporučovací systémy. Prediktivní analytika také podporuje klíčová opatření, jako jsou [kreditní skóre](https://dzone.com/articles/using-big-data-and-predictive-analytics-for-credit).

 * [Data Science ve zdravotnictví](https://data-flair.training/blogs/data-science-in-healthcare/) - zdůrazňuje aplikace jako lékařské zobrazování (např. MRI, rentgen, CT), genomiku (sekvenování DNA), vývoj léků (hodnocení rizik, predikce úspěšnosti), prediktivní analytiku (péče o pacienty a logistika zásob), sledování a prevence nemocí atd.

![Aplikace Data Science v reálném světě](../../../../translated_images/data-science-applications.4e5019cd8790ebac2277ff5f08af386f8727cac5d30f77727c7090677e6adb9c.cs.png) Zdroj obrázku: [Data Flair: 6 Amazing Data Science Applications ](https://data-flair.training/blogs/data-science-applications/)

Obrázek ukazuje další oblasti a příklady aplikace technik data science. Chcete prozkoumat další aplikace? Podívejte se na sekci [Přehled a samostudium](../../../../6-Data-Science-In-Wild/20-Real-World-Examples) níže.

## Data Science + výzkum

| ![ Sketchnote od [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/20-DataScience-Research.png) |
| :---------------------------------------------------------------------------------------------------------------: |
|              Data Science & výzkum - _Sketchnote od [@nitya](https://twitter.com/nitya)_              |

Zatímco reálné aplikace se často zaměřují na průmyslové případy ve velkém měřítku, aplikace a projekty ve _výzkumu_ mohou být užitečné ze dvou hledisek:

* _příležitosti k inovacím_ - zkoumání rychlého prototypování pokročilých konceptů a testování uživatelských zkušeností pro aplikace nové generace.
* _výzvy při nasazení_ - zkoumání potenciálních škod nebo neúmyslných důsledků technologií data science v reálných kontextech.

Pro studenty mohou tyto výzkumné projekty poskytnout jak příležitosti k učení, tak ke spolupráci, což může zlepšit jejich porozumění tématu a rozšířit povědomí a zapojení s relevantními lidmi nebo týmy pracujícími v oblastech zájmu. Jak tedy výzkumné projekty vypadají a jaký mohou mít dopad?

Podívejme se na jeden příklad - [MIT Gender Shades Study](http://gendershades.org/overview.html) od Joy Buolamwini (MIT Media Labs) s [významným výzkumným článkem](http://proceedings.mlr.press/v81/buolamwini18a/buolamwini18a.pdf) spoluautorky Timnit Gebru (tehdy v Microsoft Research), který se zaměřil na:

 * **Co:** Cílem výzkumného projektu bylo _vyhodnotit přítomnost zaujatosti v algoritmech a datových sadách pro automatizovanou analýzu obličejů_ na základě pohlaví a typu pleti.
 * **Proč:** Analýza obličejů se používá v oblastech jako vymáhání práva, letištní bezpečnost, náborové systémy a další - kontexty, kde nepřesné klasifikace (např. kvůli zaujatosti) mohou způsobit ekonomické a sociální škody dotčeným jednotlivcům nebo skupinám. Porozumění (a eliminace nebo zmírnění) zaujatosti je klíčem k férovosti při používání.
 * **Jak:** Výzkumníci si uvědomili, že stávající benchmarky používaly převážně subjekty se světlejší pletí, a vytvořili novou datovou sadu (1000+ obrázků), která byla _vyváženější_ podle pohlaví a typu pleti. Tato datová sada byla použita k vyhodnocení přesnosti tří produktů pro klasifikaci pohlaví (od Microsoftu, IBM a Face++).

Výsledky ukázaly, že přestože celková přesnost klasifikace byla dobrá, existoval znatelný rozdíl v chybovosti mezi různými podskupinami - s **nesprávným určením pohlaví** častějším u žen nebo osob s tmavší pletí, což naznačuje zaujatost.

**Klíčové výsledky:** Zvýšení povědomí o tom, že data science potřebuje více _reprezentativních datových sad_ (vyvážené podskupiny) a více _inkluzivních týmů_ (různorodé zázemí), aby bylo možné rozpoznat a eliminovat nebo zmírnit takové zaujatosti dříve v AI řešeních. Výzkumné úsilí, jako je toto, je také klíčové pro definování principů a postupů pro _zodpovědnou AI_ v mnoha organizacích, aby se zlepšila férovost jejich AI produktů a procesů.

**Chcete se dozvědět o relevantních výzkumných aktivitách v Microsoftu?**

* Podívejte se na [výzkumné projekty Microsoftu](https://www.microsoft.com/research/research-area/artificial-intelligence/?facet%5Btax%5D%5Bmsr-research-area%5D%5B%5D=13556&facet%5Btax%5D%5Bmsr-content-type%5D%5B%5D=msr-project) v oblasti umělé inteligence.
* Prozkoumejte studentské projekty z [Microsoft Research Data Science Summer School](https://www.microsoft.com/en-us/research/academic-program/data-science-summer-school/).
* Podívejte se na projekt [Fairlearn](https://fairlearn.org/) a iniciativy [Responsible AI](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1%3aprimaryr6).

## Data Science + humanitní vědy

| ![ Sketchnote od [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/20-DataScience-Humanities.png) |
| :---------------------------------------------------------------------------------------------------------------: |
|              Data Science & digitální humanitní vědy - _Sketchnote od [@nitya](https://twitter.com/nitya)_              |

Digitální humanitní vědy [byly definovány](https://digitalhumanities.stanford.edu/about-dh-stanford) jako "soubor praktik a přístupů kombinujících výpočetní metody s humanitním bádáním". [Projekty Stanfordu](https://digitalhumanities.stanford.edu/projects) jako _"rebooting history"_ a _"poetic thinking"_ ilustrují propojení mezi [digitálními humanitními vědami a data science](https://digitalhumanities.stanford.edu/digital-humanities-and-data-science) - zdůrazňují techniky jako analýza sítí, vizualizace informací, prostorová a textová analýza, které nám mohou pomoci znovu prozkoumat historické a literární datové sady a získat nové poznatky a perspektivy.

*Chcete prozkoumat a rozšířit projekt v této oblasti?*

Podívejte se na ["Emily Dickinson and the Meter of Mood"](https://gist.github.com/jlooper/ce4d102efd057137bc000db796bfd671) - skvělý příklad od [Jen Looper](https://twitter.com/jenlooper), který se ptá, jak můžeme pomocí data science znovu prozkoumat známou poezii a přehodnotit její význam a přínos její autorky v nových kontextech. Například, _můžeme předpovědět roční období, ve kterém byla báseň napsána, analýzou jejího tónu nebo sentimentu_ - a co nám to říká o stavu mysli autorky během daného období?

K zodpovězení této otázky následujeme kroky životního cyklu data science:
 * [`Získávání dat`](https://gist.github.com/jlooper/ce4d102efd057137bc000db796bfd671#acquiring-the-dataset) - sběr relevantní datové sady pro analýzu. Možnosti zahrnují použití API (např. [Poetry DB API](https://poetrydb.org/index.html)) nebo scraping webových stránek (např. [Project Gutenberg](https://www.gutenberg.org/files/12242/12242-h/12242-h.htm)) pomocí nástrojů jako [Scrapy](https://scrapy.org/).
 * [`Čištění dat`](https://gist.github.com/jlooper/ce4d102efd057137bc000db796bfd671#clean-the-data) - vysvětluje, jak lze text formátovat, čistit a zjednodušovat pomocí základních nástrojů jako Visual Studio Code a Microsoft Excel.
 * [`Analýza dat`](https://gist.github.com/jlooper/ce4d102efd057137bc000db796bfd671#working-with-the-data-in-a-notebook) - vysvětluje, jak můžeme nyní importovat datovou sadu do "notebooků" pro analýzu pomocí Python knihoven (jako pandas, numpy a matplotlib) k organizaci a vizualizaci dat.
 * [`Analýza sentimentu`](https://gist.github.com/jlooper/ce4d102efd057137bc000db796bfd671#sentiment-analysis-using-cognitive-services) - vysvětluje, jak můžeme integrovat cloudové služby jako Text Analytics, pomocí nástrojů s nízkým kódem jako [Power Automate](https://flow.microsoft.com/en-us/) pro automatizované pracovní postupy zpracování dat.

Pomocí tohoto pracovního postupu můžeme zkoumat sezónní vlivy na sentiment básní a pomoci nám vytvořit vlastní pohledy na autorku. Vyzkoušejte si to sami - a poté rozšiřte notebook o další otázky nebo vizualizujte data novými způsoby!

> Můžete použít některé nástroje z [Digital Humanities toolkit](https://github.com/Digital-Humanities-Toolkit) k prozkoumání těchto otázek.

## Data Science + udržitelnost

| ![ Sketchnote od [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/20-DataScience-Sustainability.png) |
| :---------------------------------------------------------------------------------------------------------------: |
|              Data Science & udržitelnost - _Sketchnote od [@nitya](https://twitter.com/nitya)_              |

[Agenda 2030 pro udržitelný rozvoj](https://sdgs.un.org/2030agenda) - přijatá všemi členy OSN v roce 2015 - identifikuje 17 cílů, včetně těch, které se zaměřují na **ochranu planety** před degradací a dopady změny klimatu. Iniciativa [Microsoft Sustainability](https://www.microsoft.com/en-us/sustainability) podporuje tyto cíle zkoumáním způsobů, jak mohou technologická řešení podpořit a budovat udržitelnější budoucnost se [zaměřením na 4 cíle](https://dev.to/azure/a-visual-guide-to-sustainable-software-engineering-53hh) - být uhlíkově negativní, vodně pozitivní, bez odpadu a biodiverzní do roku 2030.

Řešení těchto výzev ve škálovatelném a včasném měřítku vyžaduje myšlení v měřítku cloudu - a velká data. Iniciativa [Planetary Computer](https://planetarycomputer.microsoft.com/) poskytuje 4 komponenty, které pomáhají datovým vědcům a vývojářům v tomto úsilí:

 * [Katalog dat](https://planetarycomputer.microsoft.com/catalog) - s petabajty dat o zemských systémech (zdarma a hostováno na Azure).
 * [Planetary API](https://planetarycomputer.microsoft.com/docs/reference/stac/) - pomáhá uživatelům vyhledávat relevantní data napříč prostorem a časem.
 * [Hub](https://planetarycomputer.microsoft.com/docs/overview/environment/) - spravované prostředí pro vědce ke zpracování masivních geodatových sad.
 * [Aplikace](https://planetarycomputer.microsoft.com/applications) - ukázky případů použití a nástrojů pro udržitelné poznatky.
**Projekt Planetary Computer je aktuálně v náhledu (k září 2021)** - zde je návod, jak začít přispívat k řešením udržitelnosti pomocí datové vědy.

* [Požádejte o přístup](https://planetarycomputer.microsoft.com/account/request) a začněte s průzkumem a propojením s ostatními.
* [Prozkoumejte dokumentaci](https://planetarycomputer.microsoft.com/docs/overview/about), abyste porozuměli podporovaným datovým sadám a API.
* Pro inspiraci na aplikační nápady prozkoumejte aplikace jako [Ecosystem Monitoring](https://analytics-lab.org/ecosystemmonitoring/).

Přemýšlejte o tom, jak můžete využít vizualizaci dat k odhalení nebo zdůraznění relevantních poznatků v oblastech, jako je změna klimatu a odlesňování. Nebo přemýšlejte o tom, jak lze poznatky využít k vytvoření nových uživatelských zážitků, které motivují ke změně chování směrem k udržitelnějšímu životnímu stylu.

## Datová věda + studenti

Mluvili jsme o aplikacích v reálném světě v průmyslu a výzkumu a prozkoumali příklady aplikací datové vědy v digitálních humanitních vědách a udržitelnosti. Jak si tedy můžete jako začátečníci v datové vědě budovat dovednosti a sdílet své znalosti?

Zde je několik příkladů studentských projektů v oblasti datové vědy, které vás mohou inspirovat.

* [MSR Data Science Summer School](https://www.microsoft.com/en-us/research/academic-program/data-science-summer-school/#!projects) s GitHub [projekty](https://github.com/msr-ds3), které zkoumají témata jako:
   - [Rasová zaujatost při použití síly policií](https://www.microsoft.com/en-us/research/video/data-science-summer-school-2019-replicating-an-empirical-analysis-of-racial-differences-in-police-use-of-force/) | [Github](https://github.com/msr-ds3/stop-question-frisk)
   - [Spolehlivost systému metra v NYC](https://www.microsoft.com/en-us/research/video/data-science-summer-school-2018-exploring-the-reliability-of-the-nyc-subway-system/) | [Github](https://github.com/msr-ds3/nyctransit)
* [Digitalizace materiální kultury: Zkoumání socioekonomických rozložení v Sirkapu](https://claremont.maps.arcgis.com/apps/Cascade/index.html?appid=bdf2aef0f45a4674ba41cd373fa23afc) - od [Ornella Altunyan](https://twitter.com/ornelladotcom) a týmu z Claremontu, s využitím [ArcGIS StoryMaps](https://storymaps.arcgis.com/).

## 🚀 Výzva

Vyhledejte články, které doporučují projekty datové vědy vhodné pro začátečníky - například [těchto 50 témat](https://www.upgrad.com/blog/data-science-project-ideas-topics-beginners/), [těchto 21 nápadů na projekty](https://www.intellspot.com/data-science-project-ideas) nebo [těchto 16 projektů se zdrojovým kódem](https://data-flair.training/blogs/data-science-project-ideas/), které můžete rozebrat a znovu sestavit. Nezapomeňte také blogovat o svých učebních cestách a sdílet své poznatky s námi všemi.

## Kvíz po přednášce

[Kvíz po přednášce](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/39)

## Přehled a samostudium

Chcete prozkoumat více případů použití? Zde je několik relevantních článků:
* [17 aplikací a příkladů datové vědy](https://builtin.com/data-science/data-science-applications-examples) - červenec 2021
* [11 úchvatných aplikací datové vědy v reálném světě](https://myblindbird.com/data-science-applications-real-world/) - květen 2021
* [Datová věda v reálném světě](https://towardsdatascience.com/data-science-in-the-real-world/home) - sbírka článků
* Datová věda v: [vzdělávání](https://data-flair.training/blogs/data-science-in-education/), [zemědělství](https://data-flair.training/blogs/data-science-in-agriculture/), [financích](https://data-flair.training/blogs/data-science-in-finance/), [filmech](https://data-flair.training/blogs/data-science-at-movies/) a dalších oblastech.

## Zadání

[Prozkoumejte datovou sadu Planetary Computer](assignment.md)

---

**Prohlášení**:  
Tento dokument byl přeložen pomocí služby pro automatický překlad [Co-op Translator](https://github.com/Azure/co-op-translator). Přestože se snažíme o přesnost, mějte prosím na paměti, že automatické překlady mohou obsahovat chyby nebo nepřesnosti. Původní dokument v jeho původním jazyce by měl být považován za autoritativní zdroj. Pro důležité informace doporučujeme profesionální lidský překlad. Neodpovídáme za žádné nedorozumění nebo nesprávné interpretace vyplývající z použití tohoto překladu.