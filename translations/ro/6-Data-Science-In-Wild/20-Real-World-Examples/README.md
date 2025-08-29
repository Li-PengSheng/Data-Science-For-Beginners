<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "67076ed50f54e7d26ba1ba378d6078f1",
  "translation_date": "2025-08-26T15:49:14+00:00",
  "source_file": "6-Data-Science-In-Wild/20-Real-World-Examples/README.md",
  "language_code": "ro"
}
-->
# Știința Datelor în Lumea Reală

| ![ Sketchnote realizat de [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/20-DataScience-RealWorld.png) |
| :--------------------------------------------------------------------------------------------------------------: |
|               Știința Datelor în Lumea Reală - _Sketchnote realizat de [@nitya](https://twitter.com/nitya)_               |

Suntem aproape de finalul acestei călătorii de învățare!

Am început cu definițiile științei datelor și eticii, am explorat diverse instrumente și tehnici pentru analiza și vizualizarea datelor, am revizuit ciclul de viață al științei datelor și am analizat scalarea și automatizarea fluxurilor de lucru ale științei datelor cu ajutorul serviciilor de cloud computing. Așadar, probabil te întrebi: _"Cum pot aplica toate aceste cunoștințe în contexte reale?"_

În această lecție, vom explora aplicațiile reale ale științei datelor în diverse industrii și vom analiza exemple specifice din cercetare, științele umaniste digitale și sustenabilitate. Vom discuta despre oportunitățile pentru proiecte studențești și vom încheia cu resurse utile pentru a-ți continua călătoria de învățare!

## Chestionar Pre-Lecție

[Chestionar pre-lecție](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/38)

## Știința Datelor + Industrie

Datorită democratizării AI, dezvoltatorii găsesc acum mai ușor să proiecteze și să integreze decizii bazate pe AI și perspective bazate pe date în experiențele utilizatorilor și fluxurile de lucru de dezvoltare. Iată câteva exemple despre cum este aplicată știința datelor în aplicații reale din industrie:

 * [Google Flu Trends](https://www.wired.com/2015/10/can-learn-epic-failure-google-flu-trends/) a utilizat știința datelor pentru a corela termenii de căutare cu tendințele gripei. Deși abordarea a avut defecte, a crescut conștientizarea asupra posibilităților (și provocărilor) predicțiilor bazate pe date în domeniul sănătății.

 * [Predicțiile de rutare UPS](https://www.technologyreview.com/2018/11/21/139000/how-ups-uses-ai-to-outsmart-bad-weather/) - explică modul în care UPS folosește știința datelor și învățarea automată pentru a prezice rutele optime de livrare, luând în considerare condițiile meteorologice, traficul, termenele de livrare și altele.

 * [Vizualizarea rutelor taxiurilor din NYC](http://chriswhong.github.io/nyctaxi/) - datele colectate prin [Legile privind Libertatea Informației](https://chriswhong.com/open-data/foil_nyc_taxi/) au ajutat la vizualizarea unei zile din viața taxiurilor din NYC, ajutându-ne să înțelegem cum navighează prin orașul aglomerat, câți bani câștigă și durata curselor pe parcursul unei perioade de 24 de ore.

 * [Uber Data Science Workbench](https://eng.uber.com/dsw/) - folosește date (despre locațiile de preluare și destinație, durata curselor, rutele preferate etc.) colectate din milioane de curse Uber *zilnic* pentru a construi un instrument de analiză a datelor care ajută la stabilirea prețurilor, siguranță, detectarea fraudelor și luarea deciziilor de navigare.

 * [Analiza sportivă](https://towardsdatascience.com/scope-of-analytics-in-sports-world-37ed09c39860) - se concentrează pe _analiza predictivă_ (analiza echipelor și jucătorilor - gândiți-vă la [Moneyball](https://datasciencedegree.wisconsin.edu/blog/moneyball-proves-importance-big-data-big-ideas/) - și managementul fanilor) și _vizualizarea datelor_ (tablouri de bord pentru echipe și fani, jocuri etc.) cu aplicații precum scouting-ul de talente, pariurile sportive și managementul inventarului/locațiilor.

 * [Știința Datelor în Bănci](https://data-flair.training/blogs/data-science-in-banking/) - evidențiază valoarea științei datelor în industria financiară, cu aplicații care variază de la modelarea riscurilor și detectarea fraudelor, la segmentarea clienților, predicții în timp real și sisteme de recomandare. Analiza predictivă susține, de asemenea, măsuri critice precum [scorurile de credit](https://dzone.com/articles/using-big-data-and-predictive-analytics-for-credit).

 * [Știința Datelor în Sănătate](https://data-flair.training/blogs/data-science-in-healthcare/) - evidențiază aplicații precum imagistica medicală (de exemplu, RMN, radiografii, tomografii), genomica (secvențierea ADN-ului), dezvoltarea de medicamente (evaluarea riscurilor, predicția succesului), analiza predictivă (îngrijirea pacienților și logistica aprovizionării), urmărirea și prevenirea bolilor etc.

![Aplicații ale Științei Datelor în Lumea Reală](../../../../translated_images/data-science-applications.4e5019cd8790ebac2277ff5f08af386f8727cac5d30f77727c7090677e6adb9c.ro.png) Credit Imagine: [Data Flair: 6 Amazing Data Science Applications ](https://data-flair.training/blogs/data-science-applications/)

Figura arată alte domenii și exemple de aplicare a tehnicilor de știința datelor. Vrei să explorezi alte aplicații? Consultă secțiunea [Review & Self Study](../../../../6-Data-Science-In-Wild/20-Real-World-Examples) de mai jos.

## Știința Datelor + Cercetare

| ![ Sketchnote realizat de [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/20-DataScience-Research.png) |
| :---------------------------------------------------------------------------------------------------------------: |
|              Știința Datelor & Cercetare - _Sketchnote realizat de [@nitya](https://twitter.com/nitya)_              |

Deși aplicațiile din lumea reală se concentrează adesea pe cazuri de utilizare din industrie la scară largă, aplicațiile și proiectele de _cercetare_ pot fi utile din două perspective:

* _oportunități de inovație_ - explorarea prototipurilor rapide ale conceptelor avansate și testarea experiențelor utilizatorilor pentru aplicațiile generației următoare.
* _provocări de implementare_ - investigarea potențialelor daune sau consecințe neintenționate ale tehnologiilor de știința datelor în contexte reale.

Pentru studenți, aceste proiecte de cercetare pot oferi atât oportunități de învățare, cât și de colaborare, care îți pot îmbunătăți înțelegerea subiectului și îți pot lărgi conștientizarea și implicarea cu persoane sau echipe relevante care lucrează în domenii de interes. Cum arată proiectele de cercetare și cum pot avea impact?

Să analizăm un exemplu - [Studiul MIT Gender Shades](http://gendershades.org/overview.html) realizat de Joy Buolamwini (MIT Media Labs) cu un [articol de cercetare semnificativ](http://proceedings.mlr.press/v81/buolamwini18a/buolamwini18a.pdf) co-autor cu Timnit Gebru (pe atunci la Microsoft Research) care s-a concentrat pe:

 * **Ce:** Obiectivul proiectului de cercetare a fost să _evalueze prejudecățile prezente în algoritmii și seturile de date pentru analiza facială automată_ pe baza genului și tipului de piele.
 * **De ce:** Analiza facială este utilizată în domenii precum aplicarea legii, securitatea aeroportuară, sistemele de angajare și altele - contexte în care clasificările inexacte (de exemplu, din cauza prejudecăților) pot cauza daune economice și sociale potențiale persoanelor sau grupurilor afectate. Înțelegerea (și eliminarea sau atenuarea) prejudecăților este esențială pentru echitate în utilizare.
 * **Cum:** Cercetătorii au recunoscut că reperele existente utilizau predominant subiecți cu piele mai deschisă și au creat un nou set de date (peste 1000 de imagini) care era _mai echilibrat_ în funcție de gen și tip de piele. Setul de date a fost utilizat pentru a evalua acuratețea a trei produse de clasificare a genului (de la Microsoft, IBM și Face++).

Rezultatele au arătat că, deși acuratețea generală a clasificării era bună, exista o diferență notabilă în ratele de eroare între diversele subgrupuri - cu **clasificări greșite** mai frecvente pentru femei sau persoane cu piele mai închisă, indicând prezența prejudecăților.

**Rezultate cheie:** Studiul a crescut conștientizarea asupra faptului că știința datelor are nevoie de _seturi de date mai reprezentative_ (subgrupuri echilibrate) și de _echipe mai incluzive_ (cu diverse medii) pentru a recunoaște și elimina sau atenua astfel de prejudecăți mai devreme în soluțiile AI. Eforturile de cercetare precum acesta sunt, de asemenea, esențiale pentru ca multe organizații să definească principii și practici pentru _AI responsabilă_ pentru a îmbunătăți echitatea în produsele și procesele lor AI.

**Vrei să afli despre eforturile de cercetare relevante la Microsoft?**

* Consultă [Proiectele de Cercetare Microsoft](https://www.microsoft.com/research/research-area/artificial-intelligence/?facet%5Btax%5D%5Bmsr-research-area%5D%5B%5D=13556&facet%5Btax%5D%5Bmsr-content-type%5D%5B%5D=msr-project) în domeniul Inteligenței Artificiale.
* Explorează proiectele studențești din cadrul [Școlii de Vară Microsoft Research Data Science](https://www.microsoft.com/en-us/research/academic-program/data-science-summer-school/).
* Consultă proiectul [Fairlearn](https://fairlearn.org/) și inițiativele [AI Responsabil](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1%3aprimaryr6).

## Știința Datelor + Științele Umaniste

| ![ Sketchnote realizat de [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/20-DataScience-Humanities.png) |
| :---------------------------------------------------------------------------------------------------------------: |
|              Știința Datelor & Științele Umaniste Digitale - _Sketchnote realizat de [@nitya](https://twitter.com/nitya)_              |

Științele Umaniste Digitale [au fost definite](https://digitalhumanities.stanford.edu/about-dh-stanford) drept "o colecție de practici și abordări care combină metode computaționale cu cercetarea umanistă". [Proiectele Stanford](https://digitalhumanities.stanford.edu/projects) precum _"rebooting history"_ și _"poetic thinking"_ ilustrează legătura dintre [Științele Umaniste Digitale și Știința Datelor](https://digitalhumanities.stanford.edu/digital-humanities-and-data-science) - subliniind tehnici precum analiza rețelelor, vizualizarea informațiilor, analiza spațială și textuală care ne pot ajuta să revizităm seturi de date istorice și literare pentru a obține noi perspective și înțelegeri.

*Vrei să explorezi și să extinzi un proiect în acest domeniu?*

Consultă ["Emily Dickinson și Metrul Stării de Spirit"](https://gist.github.com/jlooper/ce4d102efd057137bc000db796bfd671) - un exemplu excelent de la [Jen Looper](https://twitter.com/jenlooper) care întreabă cum putem folosi știința datelor pentru a revizita poezia familiară și a reevalua semnificația acesteia și contribuțiile autorului în noi contexte. De exemplu, _putem prezice anotimpul în care a fost scrisă o poezie analizând tonul sau sentimentul acesteia_ - și ce ne spune acest lucru despre starea de spirit a autorului în perioada respectivă?

Pentru a răspunde la această întrebare, urmăm pașii ciclului de viață al științei datelor:
 * [`Achiziția Datelor`](https://gist.github.com/jlooper/ce4d102efd057137bc000db796bfd671#acquiring-the-dataset) - pentru a colecta un set de date relevant pentru analiză. Opțiunile includ utilizarea unui API (de exemplu, [Poetry DB API](https://poetrydb.org/index.html)) sau extragerea paginilor web (de exemplu, [Project Gutenberg](https://www.gutenberg.org/files/12242/12242-h/12242-h.htm)) folosind instrumente precum [Scrapy](https://scrapy.org/).
 * [`Curățarea Datelor`](https://gist.github.com/jlooper/ce4d102efd057137bc000db796bfd671#clean-the-data) - explică modul în care textul poate fi formatat, curățat și simplificat folosind instrumente de bază precum Visual Studio Code și Microsoft Excel.
 * [`Analiza Datelor`](https://gist.github.com/jlooper/ce4d102efd057137bc000db796bfd671#working-with-the-data-in-a-notebook) - explică modul în care putem importa setul de date în "Notebooks" pentru analiză folosind pachete Python (precum pandas, numpy și matplotlib) pentru a organiza și vizualiza datele.
 * [`Analiza Sentimentului`](https://gist.github.com/jlooper/ce4d102efd057137bc000db796bfd671#sentiment-analysis-using-cognitive-services) - explică modul în care putem integra servicii cloud precum Text Analytics, folosind instrumente low-code precum [Power Automate](https://flow.microsoft.com/en-us/) pentru fluxuri de lucru automate de procesare a datelor.

Folosind acest flux de lucru, putem explora impactul anotimpurilor asupra sentimentului poeziilor și ne putem forma propriile perspective asupra autorului. Încearcă-l și tu - apoi extinde notebook-ul pentru a pune alte întrebări sau pentru a vizualiza datele în moduri noi!

> Poți folosi unele dintre instrumentele din [trusa de instrumente pentru Științele Umaniste Digitale](https://github.com/Digital-Humanities-Toolkit) pentru a urmări aceste direcții de cercetare.

## Știința Datelor + Sustenabilitate

| ![ Sketchnote realizat de [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/20-DataScience-Sustainability.png) |
| :---------------------------------------------------------------------------------------------------------------: |
|              Știința Datelor & Sustenabilitate - _Sketchnote realizat de [@nitya](https://twitter.com/nitya)_              |

[Agenda 2030 pentru Dezvoltare Durabilă](https://sdgs.un.org/2030agenda) - adoptată de toți membrii Națiunilor Unite în 2015 - identifică 17 obiective, inclusiv cele care se concentrează pe **Protejarea Planetei** de degradare și impactul schimbărilor climatice. Inițiativa [Microsoft Sustainability](https://www.microsoft.com/en-us/sustainability) sprijină aceste obiective explorând moduri în care soluțiile tehnologice pot susține și construi un viitor mai sustenabil, cu un [focalizare pe 4 obiective](https://dev.to/azure/a-visual-guide-to-sustainable-software-engineering-53hh) - să fie negative în privința carbonului, pozitive în privința apei, fără deșeuri și biodiversificate până în 2030.

Abordarea acestor provocări într-un mod scalabil și oportun necesită gândire la scară cloud - și date la scară largă. Inițiativa [Planetary Computer](https://planetarycomputer.microsoft.com/) oferă 4 componente pentru a ajuta oamenii de știință și dezvoltatorii de date în acest efort:

 * [Catalogul de Date](https://planetarycomputer.microsoft.com/catalog) - cu petabytes de date despre Sistemele Terestre (gratuite și găzduite pe Azure).
 * [Planetary API](https://planetarycomputer.microsoft.com/docs/reference/stac/) - pentru a ajuta utilizatorii să caute date relevante în funcție de spațiu și timp.
 * [Hub](https://planetarycomputer.microsoft.com/docs/overview/environment/) - mediu gestionat pentru oamenii de știință pentru a procesa seturi masive de date geospațiale.
 * [Aplicații](https://planetarycomputer.microsoft.com/applications) - prezintă cazuri de utilizare și instrumente pentru perspective asupra sustenabilității.
**Proiectul Planetary Computer este în faza de previzualizare (din septembrie 2021)** - iată cum poți începe să contribui la soluții de sustenabilitate folosind știința datelor.

* [Solicită acces](https://planetarycomputer.microsoft.com/account/request) pentru a începe explorarea și a te conecta cu colegii.
* [Explorează documentația](https://planetarycomputer.microsoft.com/docs/overview/about) pentru a înțelege seturile de date și API-urile suportate.
* Explorează aplicații precum [Ecosystem Monitoring](https://analytics-lab.org/ecosystemmonitoring/) pentru inspirație în dezvoltarea de idei de aplicații.

Gândește-te cum poți utiliza vizualizarea datelor pentru a expune sau amplifica perspective relevante în domenii precum schimbările climatice și defrișările. Sau gândește-te cum pot fi utilizate aceste perspective pentru a crea noi experiențe pentru utilizatori care să motiveze schimbări comportamentale pentru un stil de viață mai sustenabil.

## Știința Datelor + Studenți

Am discutat despre aplicații reale în industrie și cercetare și am explorat exemple de aplicații de știința datelor în domeniul umanistic digital și sustenabilitate. Deci, cum îți poți dezvolta abilitățile și împărtăși expertiza ta ca începător în știința datelor?

Iată câteva exemple de proiecte studențești în știința datelor pentru a te inspira.

 * [Școala de Vară MSR Data Science](https://www.microsoft.com/en-us/research/academic-program/data-science-summer-school/#!projects) cu [proiecte](https://github.com/msr-ds3) pe GitHub care explorează subiecte precum:
    - [Bias rasial în utilizarea forței de către poliție](https://www.microsoft.com/en-us/research/video/data-science-summer-school-2019-replicating-an-empirical-analysis-of-racial-differences-in-police-use-of-force/) | [Github](https://github.com/msr-ds3/stop-question-frisk)
    - [Fiabilitatea sistemului de metrou din NYC](https://www.microsoft.com/en-us/research/video/data-science-summer-school-2018-exploring-the-reliability-of-the-nyc-subway-system/) | [Github](https://github.com/msr-ds3/nyctransit)
 * [Digitalizarea Culturii Materiale: Explorarea distribuțiilor socio-economice în Sirkap](https://claremont.maps.arcgis.com/apps/Cascade/index.html?appid=bdf2aef0f45a4674ba41cd373fa23afc) - de la [Ornella Altunyan](https://twitter.com/ornelladotcom) și echipa sa de la Claremont, folosind [ArcGIS StoryMaps](https://storymaps.arcgis.com/).

## 🚀 Provocare

Caută articole care recomandă proiecte de știința datelor prietenoase pentru începători - cum ar fi [aceste 50 de domenii](https://www.upgrad.com/blog/data-science-project-ideas-topics-beginners/) sau [aceste 21 de idei de proiecte](https://www.intellspot.com/data-science-project-ideas) sau [aceste 16 proiecte cu cod sursă](https://data-flair.training/blogs/data-science-project-ideas/) pe care le poți analiza și adapta. Și nu uita să scrii pe blog despre călătoria ta de învățare și să împărtășești perspectivele tale cu noi toți.

## Test de evaluare după prelegere

[Test de evaluare după prelegere](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/39)

## Recapitulare & Studiu Individual

Vrei să explorezi mai multe cazuri de utilizare? Iată câteva articole relevante:
 * [17 Aplicații și Exemple de Știința Datelor](https://builtin.com/data-science/data-science-applications-examples) - iulie 2021
 * [11 Aplicații Uimitoare ale Științei Datelor în Lumea Reală](https://myblindbird.com/data-science-applications-real-world/) - mai 2021
 * [Știința Datelor în Lumea Reală](https://towardsdatascience.com/data-science-in-the-real-world/home) - Colecție de articole
 * Știința Datelor în: [Educație](https://data-flair.training/blogs/data-science-in-education/), [Agricultură](https://data-flair.training/blogs/data-science-in-agriculture/), [Finanțe](https://data-flair.training/blogs/data-science-in-finance/), [Filme](https://data-flair.training/blogs/data-science-at-movies/) și altele.

## Temă

[Explorează un set de date Planetary Computer](assignment.md)

---

**Declinare de responsabilitate**:  
Acest document a fost tradus folosind serviciul de traducere AI [Co-op Translator](https://github.com/Azure/co-op-translator). Deși ne străduim să asigurăm acuratețea, vă rugăm să fiți conștienți că traducerile automate pot conține erori sau inexactități. Documentul original în limba sa natală ar trebui considerat sursa autoritară. Pentru informații critice, se recomandă traducerea profesională realizată de un specialist uman. Nu ne asumăm responsabilitatea pentru eventualele neînțelegeri sau interpretări greșite care pot apărea din utilizarea acestei traduceri.