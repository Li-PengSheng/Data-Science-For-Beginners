<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "8796f41f566a0a8ebb72863a83d558ed",
  "translation_date": "2025-08-26T15:06:03+00:00",
  "source_file": "1-Introduction/02-ethics/README.md",
  "language_code": "cs"
}
-->
# Úvod do datové etiky

|![ Sketchnote od [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/02-Ethics.png)|
|:---:|
| Etika datové vědy - _Sketchnote od [@nitya](https://twitter.com/nitya)_ |

---

Všichni jsme datoví občané žijící v datovém světě.

Tržní trendy naznačují, že do roku 2022 bude 1 z 3 velkých organizací nakupovat a prodávat svá data prostřednictvím online [tržišť a burz](https://www.gartner.com/smarterwithgartner/gartner-top-10-trends-in-data-and-analytics-for-2020/). Jako **vývojáři aplikací** zjistíme, že je snazší a levnější integrovat poznatky založené na datech a automatizaci řízenou algoritmy do každodenních uživatelských zkušeností. Ale jak se AI stává všudypřítomnou, budeme také muset pochopit potenciální škody způsobené [zneužitím](https://www.youtube.com/watch?v=TQHs8SA1qpk) těchto algoritmů ve velkém měřítku.

Trendy také ukazují, že do roku 2025 vytvoříme a spotřebujeme více než [180 zettabajtů](https://www.statista.com/statistics/871513/worldwide-data-created/) dat. Jako **datoví vědci** získáme bezprecedentní přístup k osobním údajům. To znamená, že můžeme vytvářet behaviorální profily uživatelů a ovlivňovat rozhodování způsoby, které vytvářejí [iluzi svobodné volby](https://www.datasciencecentral.com/profiles/blogs/the-illusion-of-choice), přičemž potenciálně směřujeme uživatele k výsledkům, které preferujeme. To také vyvolává širší otázky týkající se ochrany soukromí a práv uživatelů.

Datová etika je nyní _nezbytným ochranným opatřením_ pro datovou vědu a inženýrství, které nám pomáhá minimalizovat potenciální škody a neúmyslné důsledky našich akcí založených na datech. [Gartnerův Hype Cycle pro AI](https://www.gartner.com/smarterwithgartner/2-megatrends-dominate-the-gartner-hype-cycle-for-artificial-intelligence-2020/) identifikuje relevantní trendy v oblasti digitální etiky, odpovědné AI a správy AI jako klíčové faktory pro větší megatrendy kolem _demokratizace_ a _industrializace_ AI.

![Gartnerův Hype Cycle pro AI - 2020](https://images-cdn.newscred.com/Zz1mOWJhNzlkNDA2ZTMxMWViYjRiOGFiM2IyMjQ1YmMwZQ==)

V této lekci prozkoumáme fascinující oblast datové etiky - od základních konceptů a výzev po případové studie a aplikované koncepty AI, jako je správa, které pomáhají vytvářet etickou kulturu v týmech a organizacích pracujících s daty a AI.

## [Kvíz před přednáškou](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/2) 🎯

## Základní definice

Začněme pochopením základní terminologie.

Slovo "etika" pochází z [řeckého slova "ethikos"](https://en.wikipedia.org/wiki/Ethics) (a jeho kořene "ethos"), což znamená _charakter nebo morální povaha_.

**Etika** se týká sdílených hodnot a morálních principů, které řídí naše chování ve společnosti. Etika není založena na zákonech, ale na široce přijímaných normách toho, co je "správné vs. špatné". Etické úvahy však mohou ovlivnit iniciativy v oblasti správy společností a vládní regulace, které vytvářejí větší pobídky k dodržování pravidel.

**Datová etika** je [nová větev etiky](https://royalsocietypublishing.org/doi/full/10.1098/rsta.2016.0360#sec-1), která "studuje a hodnotí morální problémy související s _daty, algoritmy a odpovídajícími praktikami_". Zde se **"data"** zaměřují na akce související s generováním, zaznamenáváním, kurátorstvím, zpracováním, šířením, sdílením a používáním, **"algoritmy"** se zaměřují na AI, agenty, strojové učení a roboty a **"praktiky"** se zaměřují na témata jako odpovědné inovace, programování, hacking a etické kodexy.

**Aplikovaná etika** je [praktická aplikace morálních úvah](https://en.wikipedia.org/wiki/Applied_ethics). Jde o proces aktivního zkoumání etických otázek v kontextu _reálných akcí, produktů a procesů_ a přijímání nápravných opatření, aby tyto zůstaly v souladu s našimi definovanými etickými hodnotami.

**Etická kultura** se týká [_operacionalizace_ aplikované etiky](https://hbr.org/2019/05/how-to-design-an-ethical-organization), aby bylo zajištěno, že naše etické principy a praktiky jsou přijímány konzistentním a škálovatelným způsobem napříč celou organizací. Úspěšné etické kultury definují etické principy na úrovni celé organizace, poskytují smysluplné pobídky k dodržování pravidel a posilují etické normy tím, že podporují a zesilují žádoucí chování na každé úrovni organizace.

## Koncepty etiky

V této sekci se budeme zabývat koncepty jako **sdílené hodnoty** (principy) a **etické výzvy** (problémy) v oblasti datové etiky - a prozkoumáme **případové studie**, které vám pomohou pochopit tyto koncepty v reálných kontextech.

### 1. Etické principy

Každá strategie datové etiky začíná definováním _etických principů_ - "sdílených hodnot", které popisují přijatelné chování a řídí souladné akce v našich datových a AI projektech. Tyto principy můžete definovat na individuální nebo týmové úrovni. Nicméně většina velkých organizací je stanovuje v rámci mise nebo rámce _etické AI_, který je definován na korporátní úrovni a důsledně prosazován napříč všemi týmy.

**Příklad:** Prohlášení o misi [Responsible AI](https://www.microsoft.com/en-us/ai/responsible-ai) společnosti Microsoft zní: _"Jsme odhodláni k rozvoji AI řízené etickými principy, které staví lidi na první místo"_ - identifikující 6 etických principů v níže uvedeném rámci:

![Responsible AI u Microsoftu](https://docs.microsoft.com/en-gb/azure/cognitive-services/personalizer/media/ethics-and-responsible-use/ai-values-future-computed.png)

Pojďme si tyto principy stručně prozkoumat. _Transparentnost_ a _odpovědnost_ jsou základní hodnoty, na kterých jsou postaveny ostatní principy - začněme tedy u nich:

* [**Odpovědnost**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) činí praktiky _zodpovědnými_ za jejich datové a AI operace a za dodržování těchto etických principů.
* [**Transparentnost**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) zajišťuje, že akce založené na datech a AI jsou _srozumitelné_ (interpretovatelné) pro uživatele, vysvětlující co a proč za rozhodnutími stojí.
* [**Spravedlnost**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1%3aprimaryr6) se zaměřuje na zajištění, že AI zachází _se všemi lidmi_ spravedlivě, řešící jakékoli systémové nebo implicitní socio-technické předsudky v datech a systémech.
* [**Spolehlivost a bezpečnost**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) zajišťuje, že AI se chová _konzistentně_ s definovanými hodnotami, minimalizující potenciální škody nebo neúmyslné důsledky.
* [**Soukromí a bezpečnost**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) se týká pochopení původu dat a poskytování _ochrany soukromí a souvisejících práv_ uživatelům.
* [**Inkluzivita**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) je o navrhování AI řešení s úmyslem, přizpůsobujících se tak, aby splňovala _širokou škálu lidských potřeb_ a schopností.

> 🚨 Zamyslete se nad tím, jak by mohlo vypadat vaše prohlášení o misi datové etiky. Prozkoumejte rámce etické AI od jiných organizací - zde jsou příklady od [IBM](https://www.ibm.com/cloud/learn/ai-ethics), [Google](https://ai.google/principles) a [Facebook](https://ai.facebook.com/blog/facebooks-five-pillars-of-responsible-ai/). Jaké sdílené hodnoty mají společné? Jak tyto principy souvisejí s AI produkty nebo průmyslem, ve kterém působí?

### 2. Etické výzvy

Jakmile máme definované etické principy, dalším krokem je vyhodnotit naše datové a AI akce, zda jsou v souladu s těmito sdílenými hodnotami. Zamyslete se nad svými akcemi ve dvou kategoriích: _sběr dat_ a _návrh algoritmů_.

Při sběru dat budou akce pravděpodobně zahrnovat **osobní údaje** nebo osobně identifikovatelné informace (PII) pro identifikovatelné živé jednotlivce. To zahrnuje [různé položky neosobních dat](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-personal-data_en), které _společně_ identifikují jednotlivce. Etické výzvy se mohou týkat _ochrany soukromí_, _vlastnictví dat_ a souvisejících témat, jako je _informovaný souhlas_ a _práva duševního vlastnictví_ uživatelů.

Při návrhu algoritmů budou akce zahrnovat sběr a kurátorství **datových sad**, poté jejich použití k trénování a nasazení **datových modelů**, které předpovídají výsledky nebo automatizují rozhodování v reálných kontextech. Etické výzvy mohou vzniknout z _předsudků v datových sadách_, problémů s _kvalitou dat_, _nespravedlnosti_ a _zkreslení_ v algoritmech - včetně některých problémů, které jsou systémové povahy.

V obou případech etické výzvy zdůrazňují oblasti, kde naše akce mohou narazit na konflikt s našimi sdílenými hodnotami. Abychom tyto obavy odhalili, zmírnili, minimalizovali nebo odstranili, musíme si klást morální otázky typu "ano/ne" týkající se našich akcí a podle potřeby přijmout nápravná opatření. Podívejme se na některé etické výzvy a morální otázky, které vyvolávají:

#### 2.1 Vlastnictví dat

Sběr dat často zahrnuje osobní údaje, které mohou identifikovat subjekty dat. [Vlastnictví dat](https://permission.io/blog/data-ownership) se týká _kontroly_ a [_práv uživatelů_](https://permission.io/blog/data-ownership) souvisejících s vytvářením, zpracováním a šířením dat.

Morální otázky, které je třeba si položit:
 * Kdo vlastní data? (uživatel nebo organizace)
 * Jaká práva mají subjekty dat? (např. přístup, výmaz, přenositelnost)
 * Jaká práva mají organizace? (např. oprava škodlivých uživatelských recenzí)

#### 2.2 Informovaný souhlas

[Informovaný souhlas](https://legaldictionary.net/informed-consent/) definuje akt, kdy uživatelé souhlasí s akcí (např. sběr dat) s _plným pochopením_ relevantních faktů, včetně účelu, potenciálních rizik a alternativ.

Otázky k prozkoumání:
 * Dal uživatel (subjekt dat) povolení ke sběru a použití dat?
 * Rozuměl uživatel účelu, pro který byla data sbírána?
 * Rozuměl uživatel potenciálním rizikům spojeným s jeho účastí?

#### 2.3 Duševní vlastnictví

[Duševní vlastnictví](https://en.wikipedia.org/wiki/Intellectual_property) se týká nehmotných výtvorů vzniklých z lidské iniciativy, které mohou mít _ekonomickou hodnotu_ pro jednotlivce nebo podniky.

Otázky k prozkoumání:
 * Měla shromážděná data ekonomickou hodnotu pro uživatele nebo podnik?
 * Má zde **uživatel** duševní vlastnictví?
 * Má zde **organizace** duševní vlastnictví?
 * Pokud tato práva existují, jak je chráníme?

#### 2.4 Ochrana soukromí

[Ochrana soukromí](https://www.northeastern.edu/graduate/blog/what-is-data-privacy/) nebo informační soukromí se týká zachování soukromí uživatelů a ochrany jejich identity ve vztahu k osobně identifikovatelným informacím.

Otázky k prozkoumání:
 * Jsou data uživatelů (osobní) zabezpečena proti hackům a únikům?
 * Jsou data uživatelů přístupná pouze oprávněným uživatelům a kontextům?
 * Je anonymita uživatelů zachována při sdílení nebo šíření dat?
 * Lze uživatele de-identifikovat z anonymizovaných datových sad?

#### 2.5 Právo být zapomenut

[Právo být zapomenut](https://en.wikipedia.org/wiki/Right_to_be_forgotten) nebo [právo na výmaz](https://www.gdpreu.org/right-to-be-forgotten/) poskytuje uživatelům dodatečnou ochranu osobních údajů. Konkrétně dává uživatelům právo požadovat smazání nebo odstranění osobních údajů z internetových vyhledávání a dalších míst, _za určitých okolností_ - což jim umožňuje nový začátek online bez toho, aby byly jejich minulé činy proti nim použity.

Otázky k prozkoumání:
 * Umožňuje systém subjektům dat požadovat výmaz?
 * Měl by odvolání souhlasu uživatele automaticky spustit výmaz?
 * Byla data shromážděna bez souhlasu nebo nezákonnými prostředky?
 * Jsme v souladu s vládními předpisy pro ochranu dat?

#### 2.6 Předsudky v datových sadách

Předsudky v datových sadách nebo [předsudky při sběru dat](http://researcharticles.com/index.php/bias-in-data-collection-in-research/) se týkají výběru _nereprezentativního_ podmnožiny dat pro vývoj algoritmů, což může vést k nespravedlivým výsledkům pro různé skupiny. Typy předsudků zahrnují výběrové nebo vzorkovací předsudky, předsudky dobrovolníků a předsudky nástrojů.

Otázky k prozkoumání:
 * Najali jsme reprezentativní soubor subjektů dat?
 * Testovali jsme naši shromážděnou nebo kurátorovanou datovou sadu na různé předsudky?
 * Můžeme zmírnit nebo odstranit jakékoli zjištěné předsudky?

#### 2.7 Kvalita dat

[Kvalita dat](https://lakefs.io/data-quality-testing/) se zaměřuje na platnost kurátorované datové sady použité k vývoji našich algoritmů, kontroluje, zda funkce a záznamy splňují požadavky na úroveň přesnosti a konzistence potřebné pro náš AI účel.

Otázky k prozkoumání:
 * Zachytili jsme platné _funkce_ pro náš případ použití?
 * Byla data zachycena _kon
[Algorithmická spravedlnost](https://towardsdatascience.com/what-is-algorithm-fairness-3182e161cf9f) zkoumá, zda návrh algoritmu systematicky nediskriminuje specifické podskupiny subjektů dat, což může vést k [potenciálním škodám](https://docs.microsoft.com/en-us/azure/machine-learning/concept-fairness-ml) v _alokaci_ (kdy jsou zdroje odepřeny nebo zadrženy této skupině) a _kvalitě služeb_ (kdy AI není tak přesná pro některé podskupiny jako pro jiné).

Otázky k zamyšlení:
 * Hodnotili jsme přesnost modelu pro různé podskupiny a podmínky?
 * Zkoumali jsme systém kvůli možným škodám (např. stereotypizaci)?
 * Můžeme upravit data nebo znovu natrénovat modely, abychom zmírnili identifikované škody?

Prozkoumejte zdroje, jako jsou [kontrolní seznamy spravedlnosti AI](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4t6dA), abyste se dozvěděli více.

#### 2.9 Zkreslení dat

[Zkreslení dat](https://www.sciencedirect.com/topics/computer-science/misrepresentation) se týká otázky, zda komunikujeme poznatky z poctivě hlášených dat klamavým způsobem, abychom podpořili požadovaný narativ.

Otázky k zamyšlení:
 * Zveřejňujeme neúplná nebo nepřesná data?
 * Vizualizujeme data způsobem, který vede k zavádějícím závěrům?
 * Používáme selektivní statistické techniky k manipulaci s výsledky?
 * Existují alternativní vysvětlení, která mohou nabídnout jiný závěr?

#### 2.10 Svobodná volba
[Iluze svobodné volby](https://www.datasciencecentral.com/profiles/blogs/the-illusion-of-choice) nastává, když "architektury volby" systému používají algoritmy rozhodování k ovlivnění lidí, aby přijali preferovaný výsledek, zatímco jim zdánlivě dávají možnosti a kontrolu. Tyto [temné vzory](https://www.darkpatterns.org/) mohou způsobit sociální a ekonomické škody uživatelům. Protože rozhodnutí uživatelů ovlivňují profily chování, tyto akce mohou potenciálně řídit budoucí volby, které mohou zesílit nebo rozšířit dopad těchto škod.

Otázky k zamyšlení:
 * Rozuměl uživatel důsledkům svého rozhodnutí?
 * Byl uživatel informován o (alternativních) možnostech a jejich výhodách a nevýhodách?
 * Může uživatel později zvrátit automatizované nebo ovlivněné rozhodnutí?

### 3. Případové studie

Abychom uvedli tyto etické výzvy do kontextu reálného světa, je užitečné podívat se na případové studie, které zdůrazňují potenciální škody a důsledky pro jednotlivce a společnost, pokud jsou tyto etické problémy přehlíženy.

Zde je několik příkladů:

| Etická výzva | Případová studie | 
|--- |--- |
| **Informovaný souhlas** | 1972 - [Studie syfilis v Tuskegee](https://en.wikipedia.org/wiki/Tuskegee_Syphilis_Study) - Afroameričtí muži, kteří se studie zúčastnili, byli slibováni bezplatnou lékařskou péči, _ale byli podvedeni_ výzkumníky, kteří jim neřekli o jejich diagnóze ani o dostupnosti léčby. Mnoho subjektů zemřelo a jejich partneři nebo děti byli ovlivněni; studie trvala 40 let. | 
| **Ochrana dat** |  2007 - [Netflix data prize](https://www.wired.com/2007/12/why-anonymous-data-sometimes-isnt/) poskytla výzkumníkům _10M anonymizovaných hodnocení filmů od 50K zákazníků_, aby pomohla zlepšit doporučovací algoritmy. Výzkumníci však byli schopni propojit anonymizovaná data s osobně identifikovatelnými daty v _externích datových sadách_ (např. komentáře na IMDb) - efektivně "de-anonymizovali" některé předplatitele Netflixu.|
| **Sběr dat s předsudky**  | 2013 - Město Boston [vyvinulo Street Bump](https://www.boston.gov/transportation/street-bump), aplikaci, která umožnila občanům hlásit výmoly, čímž město získalo lepší údaje o silnicích pro identifikaci a opravu problémů. Nicméně [lidé z nižších příjmových skupin měli menší přístup k autům a telefonům](https://hbr.org/2013/04/the-hidden-biases-in-big-data), což činilo jejich problémy na silnicích neviditelnými v této aplikaci. Vývojáři spolupracovali s akademiky na _problémech spravedlivého přístupu a digitálních rozdílů_. |
| **Algoritmická spravedlnost**  | 2018 - MIT [Gender Shades Study](http://gendershades.org/overview.html) hodnotila přesnost AI produktů pro klasifikaci pohlaví, odhalila mezery v přesnosti pro ženy a osoby jiné barvy pleti. [Apple Card z roku 2019](https://www.wired.com/story/the-apple-card-didnt-see-genderand-thats-the-problem/) se zdála nabízet méně úvěru ženám než mužům. Oba případy ilustrují problémy algoritmické zaujatosti vedoucí k socio-ekonomickým škodám.|
| **Zkreslení dat** | 2020 - [Ministerstvo zdravotnictví státu Georgia zveřejnilo grafy COVID-19](https://www.vox.com/covid-19-coronavirus-us-response-trump/2020/5/18/21262265/georgia-covid-19-cases-declining-reopening), které se zdály zavádět občany ohledně trendů potvrzených případů s nechronologickým uspořádáním na ose x. To ilustruje zkreslení prostřednictvím vizualizačních triků. |
| **Iluze svobodné volby** | 2020 - Vzdělávací aplikace [ABCmouse zaplatila 10M USD za urovnání stížnosti FTC](https://www.washingtonpost.com/business/2020/09/04/abcmouse-10-million-ftc-settlement/), kde rodiče byli uvězněni v placení za předplatné, které nemohli zrušit. To ilustruje temné vzory v architekturách volby, kde byli uživatelé ovlivněni k potenciálně škodlivým rozhodnutím. |
| **Ochrana dat a práva uživatelů** | 2021 - Facebook [Únik dat](https://www.npr.org/2021/04/09/986005820/after-data-breach-exposes-530-million-facebook-says-it-will-not-notify-users) odhalil data 530M uživatelů, což vedlo k urovnání ve výši 5B USD s FTC. Nicméně odmítl informovat uživatele o úniku, čímž porušil práva uživatelů na transparentnost a přístup k datům. |

Chcete prozkoumat více případových studií? Podívejte se na tyto zdroje:
* [Ethics Unwrapped](https://ethicsunwrapped.utexas.edu/case-studies) - etické dilemata napříč různými odvětvími. 
* [Kurz etiky datové vědy](https://www.coursera.org/learn/data-science-ethics#syllabus) - přehled klíčových případových studií.
* [Kde se věci pokazily](https://deon.drivendata.org/examples/) - kontrolní seznam Deon s příklady.

> 🚨 Zamyslete se nad případovými studiemi, které jste viděli - zažili jste nebo byli ovlivněni podobnou etickou výzvou ve svém životě? Dokážete si vzpomenout na alespoň jednu další případovou studii, která ilustruje jednu z etických výzev, o kterých jsme diskutovali v této sekci?

## Aplikovaná etika

Diskutovali jsme o etických konceptech, výzvách a případových studiích v kontextu reálného světa. Ale jak začít _aplikovat_ etické principy a praktiky ve svých projektech? A jak _zavést_ tyto praktiky pro lepší řízení? Pojďme prozkoumat některá řešení z praxe:

### 1. Profesní kodexy

Profesní kodexy nabízejí jednu možnost, jak organizace mohou "motivovat" členy k podpoře jejich etických principů a poslání. Kodexy jsou _morálními pokyny_ pro profesionální chování, které pomáhají zaměstnancům nebo členům činit rozhodnutí v souladu s principy jejich organizace. Jsou však účinné pouze tehdy, pokud členové dobrovolně dodržují; mnoho organizací však nabízí další odměny a sankce, aby motivovaly členy k dodržování.

Příklady zahrnují:

 * [Oxford Munich](http://www.code-of-ethics.org/code-of-conduct/) Etický kodex
 * [Data Science Association](http://datascienceassn.org/code-of-conduct.html) Kodex chování (vytvořen 2013)
 * [ACM Code of Ethics and Professional Conduct](https://www.acm.org/code-of-ethics) (od roku 1993)

> 🚨 Jste členem profesní organizace pro inženýry nebo datové vědce? Prozkoumejte jejich web, zda definují profesní kodex etiky. Co říká o jejich etických principech? Jak motivují členy k dodržování kodexu?

### 2. Etické kontrolní seznamy

Zatímco profesní kodexy definují požadované _etické chování_ od praktikujících, mají [známé limity](https://resources.oreilly.com/examples/0636920203964/blob/master/of_oaths_and_checklists.md) v prosazování, zejména u rozsáhlých projektů. Místo toho mnoho odborníků na datovou vědu [doporučuje kontrolní seznamy](https://resources.oreilly.com/examples/0636920203964/blob/master/of_oaths_and_checklists.md), které mohou **propojit principy s praxí** deterministickým a akceschopným způsobem.

Kontrolní seznamy převádějí otázky na úkoly "ano/ne", které lze zavést do standardních pracovních postupů při vydávání produktů.

Příklady zahrnují:
 * [Deon](https://deon.drivendata.org/) - obecný kontrolní seznam etiky dat vytvořený na základě [doporučení z průmyslu](https://deon.drivendata.org/#checklist-citations) s nástrojem příkazového řádku pro snadnou integraci.
 * [Kontrolní seznam auditu ochrany soukromí](https://cyber.harvard.edu/ecommerce/privacyaudit.html) - poskytuje obecné pokyny pro nakládání s informacemi z právního a sociálního hlediska.
 * [Kontrolní seznam spravedlnosti AI](https://www.microsoft.com/en-us/research/project/ai-fairness-checklist/) - vytvořený odborníky na AI na podporu zavádění a integrace kontrol spravedlnosti do vývojových cyklů AI.
 * [22 otázek pro etiku v datech a AI](https://medium.com/the-organization/22-questions-for-ethics-in-data-and-ai-efb68fd19429) - otevřenější rámec, strukturovaný pro počáteční zkoumání etických problémů v návrhu, implementaci a organizačních kontextech.

### 3. Etické regulace

Etika se týká definování sdílených hodnot a dobrovolného dělání správných věcí. **Soulad** se týká _dodržování zákona_, pokud je definován. **Řízení** obecně pokrývá všechny způsoby, jakými organizace fungují, aby prosazovaly etické principy a dodržovaly stanovené zákony.

Dnes řízení probíhá ve dvou formách v rámci organizací. Za prvé, jde o definování **etických principů AI** a zavádění praktik pro jejich přijetí napříč všemi projekty souvisejícími s AI v organizaci. Za druhé, jde o dodržování všech vládou nařízených **regulací ochrany dat** pro regiony, ve kterých organizace působí.

Příklady regulací ochrany dat a soukromí:

 * `1974`, [US Privacy Act](https://www.justice.gov/opcl/privacy-act-1974) - reguluje _federální vládní_ sběr, použití a zveřejňování osobních informací.
 * `1996`, [US Health Insurance Portability & Accountability Act (HIPAA)](https://www.cdc.gov/phlp/publications/topic/hipaa.html) - chrání osobní zdravotní údaje.
 * `1998`, [US Children's Online Privacy Protection Act (COPPA)](https://www.ftc.gov/enforcement/rules/rulemaking-regulatory-reform-proceedings/childrens-online-privacy-protection-rule) - chrání soukromí dat dětí mladších 13 let.
 * `2018`, [General Data Protection Regulation (GDPR)](https://gdpr-info.eu/) - poskytuje práva uživatelů, ochranu dat a soukromí.
 * `2018`, [California Consumer Privacy Act (CCPA)](https://www.oag.ca.gov/privacy/ccpa) dává spotřebitelům více _práv_ nad jejich (osobními) daty.
 * `2021`, Čína [Zákon o ochraně osobních údajů](https://www.reuters.com/world/china/china-passes-new-personal-data-privacy-law-take-effect-nov-1-2021-08-20/) právě schválila, čímž vytvořila jednu z nejsilnějších regulací online ochrany soukromí na světě.

> 🚨 Evropská unie definovala GDPR (General Data Protection Regulation), který zůstává jednou z nejvlivnějších regulací ochrany dat dnes. Věděli jste, že také definuje [8 práv uživatelů](https://www.freeprivacypolicy.com/blog/8-user-rights-gdpr) na ochranu digitálního soukromí a osobních dat občanů? Zjistěte, co to jsou a proč jsou důležitá.

### 4. Etická kultura

Je třeba poznamenat, že stále existuje nehmotná mezera mezi _souladem_ (děláním dostatečného pro splnění "litery zákona") a řešením [systémových problémů](https://www.coursera.org/learn/data-science-ethics/home/week/4) (jako je zkostnatělost, informační asymetrie a distribuční nespravedlnost), které mohou urychlit zneužití AI.

To druhé vyžaduje [spolupráci na definování etických kultur](https://towardsdatascience.com/why-ai-ethics-requires-a-culture-driven-approach-26f451afa29f), které budují emocionální spojení a konzistentní sdílené hodnoty _napříč organizacemi_ v průmyslu. To volá po více [formalizovaných kulturách etiky dat](https://www.codeforamerica.org/news/formalizing-an-ethical-data-culture/) v organizacích - umožňující _komukoli_ [zatáhnout za Andon šňůru](https://en.wikipedia.org/wiki/Andon_(manufacturing)) (aby včas upozornil na etické problémy) a učinit _etické hodnocení_ (např. při náboru) klíčovým kritériem pro formování týmů v projektech AI.

---
## [Kvíz po přednášce](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/3) 🎯
## Přehled & Samostudium 

Kurzy a knihy pomáhají pochopit základní etické koncepty a výzvy, zatímco případové studie a nástroje pomáhají s aplikovanými etickými praktikami v reálných kontextech. Zde je několik zdrojů, kde začít.

* [Strojové učení pro začátečníky](https://github.com/microsoft/ML-For-Beginners/blob/main/1-Introduction/3-fairness/README.md) - lekce o spravedlnosti od Microsoftu.
* [Principy odpovědné AI](https://docs.microsoft.com/en-us/learn/modules/responsible-ai-principles/) - bezplatná vzdělávací cesta od Microsoft Learn.
* [Etika a datová věda](https://resources.oreilly.com/examples/0636920203964) - EBook od O'Reilly (M. Loukides, H. Mason a kol.)
* [Etika datové vědy](https://www.coursera.org/learn/data-science-ethics#syllabus) - online kurz od University of Michigan.
* [Etika v praxi](https://ethicsunwrapped.utexas.edu/case-studies) - případové studie od University of Texas.

# Zadání

[Vypracujte případovou studii o etice dat](assignment.md)

---

**Prohlášení**:  
Tento dokument byl přeložen pomocí služby pro automatický překlad [Co-op Translator](https://github.com/Azure/co-op-translator). Ačkoli se snažíme o přesnost, mějte prosím na paměti, že automatické překlady mohou obsahovat chyby nebo nepřesnosti. Původní dokument v jeho původním jazyce by měl být považován za autoritativní zdroj. Pro důležité informace se doporučuje profesionální lidský překlad. Neodpovídáme za žádná nedorozumění nebo nesprávné interpretace vyplývající z použití tohoto překladu.