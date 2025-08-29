<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "8796f41f566a0a8ebb72863a83d558ed",
  "translation_date": "2025-08-24T21:21:19+00:00",
  "source_file": "1-Introduction/02-ethics/README.md",
  "language_code": "pl"
}
-->
# Wprowadzenie do etyki danych

|![ Sketchnote autorstwa [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/02-Ethics.png)|
|:---:|
| Etyka w nauce o danych - _Sketchnote autorstwa [@nitya](https://twitter.com/nitya)_ |

---

Wszyscy jesteśmy obywatelami danych żyjącymi w świecie zdominowanym przez dane.

Trendy rynkowe wskazują, że do 2022 roku 1 na 3 duże organizacje będzie kupować i sprzedawać swoje dane za pośrednictwem internetowych [rynków i giełd](https://www.gartner.com/smarterwithgartner/gartner-top-10-trends-in-data-and-analytics-for-2020/). Jako **deweloperzy aplikacji**, będziemy mieli łatwiejszy i tańszy dostęp do integracji wniosków opartych na danych oraz automatyzacji napędzanej algorytmami w codziennych doświadczeniach użytkowników. Jednak wraz z coraz większym rozpowszechnieniem AI, musimy również zrozumieć potencjalne szkody wynikające z [uzbrojenia](https://www.youtube.com/watch?v=TQHs8SA1qpk) takich algorytmów na dużą skalę.

Trendy wskazują również, że do 2025 roku stworzymy i skonsumujemy ponad [180 zettabajtów](https://www.statista.com/statistics/871513/worldwide-data-created/) danych. Jako **naukowcy danych**, zyskamy bezprecedensowy dostęp do danych osobowych. Oznacza to, że możemy budować profile behawioralne użytkowników i wpływać na podejmowanie decyzji w sposób, który tworzy [iluzję wolnego wyboru](https://www.datasciencecentral.com/profiles/blogs/the-illusion-of-choice), jednocześnie potencjalnie kierując użytkowników w stronę preferowanych przez nas wyników. To również rodzi szersze pytania dotyczące prywatności danych i ochrony użytkowników.

Etyka danych to teraz _niezbędne zabezpieczenia_ w nauce o danych i inżynierii, które pomagają minimalizować potencjalne szkody i niezamierzone konsekwencje naszych działań opartych na danych. [Cykl Hype Gartnera dla AI](https://www.gartner.com/smarterwithgartner/2-megatrends-dominate-the-gartner-hype-cycle-for-artificial-intelligence-2020/) identyfikuje istotne trendy w zakresie etyki cyfrowej, odpowiedzialnej AI i zarządzania AI jako kluczowe czynniki napędzające większe megatrendy wokół _demokratyzacji_ i _uprzemysłowienia_ AI.

![Cykl Hype Gartnera dla AI - 2020](https://images-cdn.newscred.com/Zz1mOWJhNzlkNDA2ZTMxMWViYjRiOGFiM2IyMjQ1YmMwZQ==)

W tej lekcji zgłębimy fascynujący obszar etyki danych - od podstawowych pojęć i wyzwań, przez studia przypadków, aż po zastosowane koncepcje AI, takie jak zarządzanie, które pomagają ustanowić kulturę etyki w zespołach i organizacjach pracujących z danymi i AI.

## [Quiz przed wykładem](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/2) 🎯

## Podstawowe definicje

Zacznijmy od zrozumienia podstawowej terminologii.

Słowo "etyka" pochodzi od [greckiego słowa "ethikos"](https://en.wikipedia.org/wiki/Ethics) (i jego rdzenia "ethos"), oznaczającego _charakter lub moralną naturę_.

**Etyka** dotyczy wspólnych wartości i zasad moralnych, które regulują nasze zachowanie w społeczeństwie. Etyka nie opiera się na prawach, ale na powszechnie akceptowanych normach tego, co jest "dobre a złe". Jednak rozważania etyczne mogą wpływać na inicjatywy w zakresie ładu korporacyjnego i regulacje rządowe, które tworzą większe zachęty do przestrzegania zasad.

**Etyka danych** to [nowa gałąź etyki](https://royalsocietypublishing.org/doi/full/10.1098/rsta.2016.0360#sec-1), która "bada i ocenia problemy moralne związane z _danymi, algorytmami i odpowiadającymi im praktykami_". Tutaj **"dane"** koncentrują się na działaniach związanych z generowaniem, rejestrowaniem, kuracją, przetwarzaniem, rozpowszechnianiem, udostępnianiem i użytkowaniem, **"algorytmy"** skupiają się na AI, agentach, uczeniu maszynowym i robotach, a **"praktyki"** dotyczą takich tematów jak odpowiedzialna innowacja, programowanie, hacking i kodeksy etyczne.

**Etyka stosowana** to [praktyczne zastosowanie rozważań moralnych](https://en.wikipedia.org/wiki/Applied_ethics). Jest to proces aktywnego badania kwestii etycznych w kontekście _działań, produktów i procesów w rzeczywistym świecie_ oraz podejmowania działań korygujących, aby upewnić się, że pozostają one zgodne z określonymi wartościami etycznymi.

**Kultura etyczna** dotyczy [_operacjonalizacji_ etyki stosowanej](https://hbr.org/2019/05/how-to-design-an-ethical-organization), aby upewnić się, że nasze zasady i praktyki etyczne są przyjmowane w sposób spójny i skalowalny w całej organizacji. Udane kultury etyczne definiują zasady etyczne na poziomie organizacyjnym, zapewniają znaczące zachęty do przestrzegania zasad i wzmacniają normy etyczne, zachęcając i promując pożądane zachowania na każdym poziomie organizacji.

## Koncepcje etyczne

W tej sekcji omówimy koncepcje takie jak **wspólne wartości** (zasady) i **wyzwania etyczne** (problemy) w etyce danych - oraz przeanalizujemy **studia przypadków**, które pomogą zrozumieć te koncepcje w kontekstach rzeczywistych.

### 1. Zasady etyczne

Każda strategia etyki danych zaczyna się od zdefiniowania _zasad etycznych_ - "wspólnych wartości", które opisują akceptowalne zachowania i kierują działaniami zgodnymi z przepisami w naszych projektach związanych z danymi i AI. Możesz je zdefiniować na poziomie indywidualnym lub zespołowym. Jednak większość dużych organizacji określa je w ramach misji lub struktury _etycznego AI_, która jest definiowana na poziomie korporacyjnym i konsekwentnie egzekwowana we wszystkich zespołach.

**Przykład:** Misja [Odpowiedzialnego AI](https://www.microsoft.com/en-us/ai/responsible-ai) Microsoftu brzmi: _"Jesteśmy zaangażowani w rozwój AI napędzanej zasadami etycznymi, które stawiają ludzi na pierwszym miejscu"_ - identyfikując 6 zasad etycznych w poniższym frameworku:

![Odpowiedzialne AI w Microsoft](https://docs.microsoft.com/en-gb/azure/cognitive-services/personalizer/media/ethics-and-responsible-use/ai-values-future-computed.png)

Przyjrzyjmy się krótko tym zasadom. _Przejrzystość_ i _odpowiedzialność_ są podstawowymi wartościami, na których opierają się inne zasady - zacznijmy więc od nich:

* [**Odpowiedzialność**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) sprawia, że praktycy są _odpowiedzialni_ za swoje działania związane z danymi i AI oraz za zgodność z tymi zasadami etycznymi.
* [**Przejrzystość**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) zapewnia, że działania związane z danymi i AI są _zrozumiałe_ (interpretowalne) dla użytkowników, wyjaśniając, co i dlaczego stoi za decyzjami.
* [**Sprawiedliwość**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1%3aprimaryr6) - koncentruje się na zapewnieniu, że AI traktuje _wszystkich ludzi_ sprawiedliwie, eliminując systemowe lub ukryte uprzedzenia w danych i systemach.
* [**Niezawodność i bezpieczeństwo**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) - zapewnia, że AI działa _spójnie_ z określonymi wartościami, minimalizując potencjalne szkody lub niezamierzone konsekwencje.
* [**Prywatność i bezpieczeństwo**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) - dotyczy zrozumienia pochodzenia danych i zapewnienia _prywatności danych oraz związanych z tym ochron_ użytkownikom.
* [**Inkluzywność**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) - dotyczy projektowania rozwiązań AI z zamiarem dostosowania ich do _szerokiego zakresu ludzkich potrzeb_ i możliwości.

> 🚨 Zastanów się, jaka mogłaby być twoja misja etyki danych. Zbadaj ramy etycznego AI innych organizacji - oto przykłady od [IBM](https://www.ibm.com/cloud/learn/ai-ethics), [Google](https://ai.google/principles) i [Facebook](https://ai.facebook.com/blog/facebooks-five-pillars-of-responsible-ai/). Jakie wspólne wartości mają? Jak te zasady odnoszą się do produktów AI lub branży, w której działają?

### 2. Wyzwania etyczne

Gdy mamy zdefiniowane zasady etyczne, kolejnym krokiem jest ocena naszych działań związanych z danymi i AI, aby sprawdzić, czy są zgodne z tymi wspólnymi wartościami. Pomyśl o swoich działaniach w dwóch kategoriach: _zbieranie danych_ i _projektowanie algorytmów_.

W przypadku zbierania danych działania prawdopodobnie będą dotyczyć **danych osobowych** lub danych umożliwiających identyfikację osób (PII) dla możliwych do zidentyfikowania żyjących osób. Obejmuje to [różnorodne elementy danych nieosobowych](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-personal-data_en), które _łącznie_ identyfikują osobę. Wyzwania etyczne mogą dotyczyć _prywatności danych_, _własności danych_ i powiązanych tematów, takich jak _świadoma zgoda_ i _prawa własności intelektualnej_ użytkowników.

W przypadku projektowania algorytmów działania będą obejmować zbieranie i kurację **zbiorów danych**, a następnie ich wykorzystanie do trenowania i wdrażania **modeli danych**, które przewidują wyniki lub automatyzują decyzje w rzeczywistych kontekstach. Wyzwania etyczne mogą wynikać z _uprzedzeń w zbiorach danych_, _problemów z jakością danych_, _niesprawiedliwości_ i _fałszywego przedstawienia_ w algorytmach - w tym niektórych problemów o charakterze systemowym.

W obu przypadkach wyzwania etyczne wskazują obszary, w których nasze działania mogą być sprzeczne z naszymi wspólnymi wartościami. Aby wykryć, złagodzić, zminimalizować lub wyeliminować te obawy, musimy zadawać moralne pytania "tak/nie" dotyczące naszych działań, a następnie podejmować odpowiednie działania korygujące. Przyjrzyjmy się niektórym wyzwaniom etycznym i moralnym pytaniom, które one rodzą:

#### 2.1 Własność danych

Zbieranie danych często obejmuje dane osobowe, które mogą identyfikować podmioty danych. [Własność danych](https://permission.io/blog/data-ownership) dotyczy _kontroli_ i [_praw użytkowników_](https://permission.io/blog/data-ownership) związanych z tworzeniem, przetwarzaniem i rozpowszechnianiem danych.

Moralne pytania, które musimy zadać:
 * Kto jest właścicielem danych? (użytkownik czy organizacja)
 * Jakie prawa mają podmioty danych? (np. dostęp, usunięcie, przenoszenie)
 * Jakie prawa mają organizacje? (np. poprawianie złośliwych recenzji użytkowników)

#### 2.2 Świadoma zgoda

[Świadoma zgoda](https://legaldictionary.net/informed-consent/) definiuje akt zgody użytkowników na działanie (np. zbieranie danych) z _pełnym zrozumieniem_ istotnych faktów, w tym celu, potencjalnych ryzyk i alternatyw.

Pytania do rozważenia:
 * Czy użytkownik (podmiot danych) wyraził zgodę na zbieranie i wykorzystanie danych?
 * Czy użytkownik rozumiał cel, dla którego dane zostały zebrane?
 * Czy użytkownik rozumiał potencjalne ryzyka wynikające z jego udziału?

#### 2.3 Własność intelektualna

[Własność intelektualna](https://en.wikipedia.org/wiki/Intellectual_property) odnosi się do niematerialnych wytworów wynikających z ludzkiej inicjatywy, które mogą _mieć wartość ekonomiczną_ dla osób lub firm.

Pytania do rozważenia:
 * Czy zebrane dane miały wartość ekonomiczną dla użytkownika lub firmy?
 * Czy **użytkownik** ma tutaj własność intelektualną?
 * Czy **organizacja** ma tutaj własność intelektualną?
 * Jeśli te prawa istnieją, jak je chronimy?

#### 2.4 Prywatność danych

[Prywatność danych](https://www.northeastern.edu/graduate/blog/what-is-data-privacy/) lub prywatność informacji odnosi się do zachowania prywatności użytkownika i ochrony jego tożsamości w odniesieniu do danych umożliwiających identyfikację.

Pytania do rozważenia:
 * Czy dane użytkowników (osobowe) są zabezpieczone przed atakami i wyciekami?
 * Czy dane użytkowników są dostępne tylko dla autoryzowanych użytkowników i kontekstów?
 * Czy anonimowość użytkowników jest zachowana, gdy dane są udostępniane lub rozpowszechniane?
 * Czy użytkownik może zostać zidentyfikowany z anonimowych zbiorów danych?

#### 2.5 Prawo do bycia zapomnianym

[Prawo do bycia zapomnianym](https://en.wikipedia.org/wiki/Right_to_be_forgotten) lub [Prawo do usunięcia](https://www.gdpreu.org/right-to-be-forgotten/) zapewnia użytkownikom dodatkową ochronę danych osobowych. Daje użytkownikom prawo do żądania usunięcia lub wycofania danych osobowych z wyszukiwarek internetowych i innych miejsc, _w określonych okolicznościach_ - umożliwiając im nowy start online bez obciążenia przeszłymi działaniami.

Pytania do rozważenia:
 * Czy system pozwala podmiotom danych na żądanie usunięcia danych?
 * Czy wycofanie zgody użytkownika powinno automatycznie uruchamiać usunięcie danych?
 * Czy dane zostały zebrane bez zgody lub w sposób niezgodny z prawem?
 * Czy jesteśmy zgodni z regulacjami rządowymi dotyczącymi prywatności danych?

#### 2.6 Uprzedzenia w zbiorach danych

Uprzedzenia w zbiorach danych lub [uprzedzenia w zbieraniu danych](http://researcharticles.com/index.php/bias-in-data-collection-in-research/) dotyczą wyboru _niereprezentatywnego_ podzbioru danych do rozwoju algorytmu, co może prowadzić do niesprawiedliwych wyników dla różnych grup. Rodzaje uprzedzeń obejmują uprzedzenia selekcyjne, uprzedzenia ochotników i uprzedzenia narzędziowe.

Pytania do rozważenia:
 * Czy zrekrutowaliśmy reprezentatywny zestaw podmiotów danych?
 * Czy przetestowaliśmy nasz zebrany lub kuratorowany zbiór danych pod kątem różnych uprzedzeń?
 * Czy możemy złagodzić lub usunąć wykryte uprzedzenia?

#### 2.7 Jakość danych

[Jakość danych](https://lakefs.io/data-quality-testing/) odnosi się do ważności kuratorowanego zbioru danych używanego do rozwoju naszych algorytmów, sprawdzając, czy cechy i rekordy spełniają wymagania dotyczące poziomu dokładności i spójności potrzebnego do naszego celu AI.

Pytania do rozważenia:
 * Czy uchwyciliśmy ważne _cechy_ dla naszego przypadku użycia?
 * Czy
[Algorithmiczna Sprawiedliwość](https://towardsdatascience.com/what-is-algorithm-fairness-3182e161cf9f) sprawdza, czy projekt algorytmu systematycznie dyskryminuje określone podgrupy osób, co prowadzi do [potencjalnych szkód](https://docs.microsoft.com/en-us/azure/machine-learning/concept-fairness-ml) w zakresie _alokacji_ (gdzie zasoby są odmawiane lub wstrzymywane dla tej grupy) oraz _jakości usług_ (gdzie AI jest mniej dokładne dla niektórych podgrup w porównaniu do innych).

Pytania do rozważenia:
 * Czy oceniliśmy dokładność modelu dla różnych podgrup i warunków?
 * Czy przeanalizowaliśmy system pod kątem potencjalnych szkód (np. stereotypizacji)?
 * Czy możemy zmodyfikować dane lub ponownie wytrenować modele, aby zminimalizować zidentyfikowane szkody?

Odkryj zasoby, takie jak [listy kontrolne AI Fairness](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4t6dA), aby dowiedzieć się więcej.

#### 2.9 Wprowadzanie w błąd

[Wprowadzanie w błąd w danych](https://www.sciencedirect.com/topics/computer-science/misrepresentation) dotyczy pytania, czy komunikujemy wnioski z uczciwie zgromadzonych danych w sposób zwodniczy, aby wspierać pożądany przekaz.

Pytania do rozważenia:
 * Czy raportujemy niekompletne lub niedokładne dane?
 * Czy wizualizujemy dane w sposób prowadzący do mylących wniosków?
 * Czy stosujemy wybiórcze techniki statystyczne, aby manipulować wynikami?
 * Czy istnieją alternatywne wyjaśnienia, które mogą prowadzić do innych wniosków?

#### 2.10 Iluzja wolnego wyboru
[Iluzja wolnego wyboru](https://www.datasciencecentral.com/profiles/blogs/the-illusion-of-choice) pojawia się, gdy "architektury wyboru" systemu wykorzystują algorytmy decyzyjne, aby skłonić ludzi do podjęcia preferowanego wyniku, jednocześnie dając im pozory opcji i kontroli. Te [ciemne wzorce](https://www.darkpatterns.org/) mogą powodować szkody społeczne i ekonomiczne dla użytkowników. Ponieważ decyzje użytkowników wpływają na profile behawioralne, te działania mogą potencjalnie napędzać przyszłe wybory, wzmacniając lub przedłużając skutki tych szkód.

Pytania do rozważenia:
 * Czy użytkownik rozumiał konsekwencje podjęcia tej decyzji?
 * Czy użytkownik był świadomy (alternatywnych) opcji oraz ich zalet i wad?
 * Czy użytkownik może cofnąć automatyczną lub wymuszoną decyzję później?

### 3. Studia przypadków

Aby umieścić te wyzwania etyczne w kontekście rzeczywistym, warto przyjrzeć się studiom przypadków, które podkreślają potencjalne szkody i konsekwencje dla jednostek i społeczeństwa, gdy naruszenia etyki są ignorowane.

Oto kilka przykładów:

| Wyzwanie etyczne | Studium przypadku  | 
|--- |--- |
| **Świadoma zgoda** | 1972 - [Badanie kiły w Tuskegee](https://en.wikipedia.org/wiki/Tuskegee_Syphilis_Study) - Afroamerykańscy mężczyźni uczestniczący w badaniu zostali zwiedzeni obietnicą darmowej opieki medycznej, podczas gdy badacze nie poinformowali ich o diagnozie ani o dostępności leczenia. Wielu uczestników zmarło, a ich partnerzy lub dzieci zostali dotknięci; badanie trwało 40 lat. | 
| **Prywatność danych** |  2007 - [Nagroda Netflixa za dane](https://www.wired.com/2007/12/why-anonymous-data-sometimes-isnt/) udostępniła badaczom _10 milionów zanonimizowanych ocen filmów od 50 tysięcy klientów_, aby poprawić algorytmy rekomendacji. Jednak badacze byli w stanie powiązać zanonimizowane dane z danymi osobowymi w _zewnętrznych zbiorach danych_ (np. komentarze na IMDb), skutecznie "deanonimizując" niektórych subskrybentów Netflixa.|
| **Stronniczość w zbieraniu danych**  | 2013 - Miasto Boston [opracowało Street Bump](https://www.boston.gov/transportation/street-bump), aplikację pozwalającą obywatelom zgłaszać dziury w drogach, co miało dostarczyć lepszych danych o drogach. Jednak [osoby z niższych grup dochodowych miały mniejszy dostęp do samochodów i telefonów](https://hbr.org/2013/04/the-hidden-biases-in-big-data), co sprawiło, że ich problemy drogowe były niewidoczne w tej aplikacji. Twórcy współpracowali z akademikami, aby rozwiązać problemy z _równym dostępem i cyfrowymi podziałami_ w celu zapewnienia sprawiedliwości. |
| **Sprawiedliwość algorytmiczna**  | 2018 - Badanie MIT [Gender Shades](http://gendershades.org/overview.html) oceniło dokładność produktów AI klasyfikujących płeć, ujawniając luki w dokładności dla kobiet i osób o innym kolorze skóry. [Karta Apple z 2019 roku](https://www.wired.com/story/the-apple-card-didnt-see-genderand-thats-the-problem/) wydawała się oferować mniejsze limity kredytowe kobietom niż mężczyznom. Oba przypadki ilustrują problemy z uprzedzeniami algorytmicznymi prowadzącymi do szkód społeczno-ekonomicznych.|
| **Wprowadzanie w błąd w danych** | 2020 - [Departament Zdrowia Publicznego w Georgii opublikował wykresy COVID-19](https://www.vox.com/covid-19-coronavirus-us-response-trump/2020/5/18/21262265/georgia-covid-19-cases-declining-reopening), które wydawały się wprowadzać obywateli w błąd co do trendów w potwierdzonych przypadkach poprzez niechronologiczne uporządkowanie osi x. To ilustruje wprowadzanie w błąd za pomocą trików wizualizacyjnych. |
| **Iluzja wolnego wyboru** | 2020 - Aplikacja edukacyjna [ABCmouse zapłaciła 10 milionów dolarów w ramach ugody z FTC](https://www.washingtonpost.com/business/2020/09/04/abcmouse-10-million-ftc-settlement/), gdzie rodzice byli zmuszani do opłacania subskrypcji, których nie mogli anulować. To ilustruje ciemne wzorce w architekturach wyboru, gdzie użytkownicy byli skłaniani do potencjalnie szkodliwych decyzji. |
| **Prywatność danych i prawa użytkowników** | 2021 - [Wyciek danych z Facebooka](https://www.npr.org/2021/04/09/986005820/after-data-breach-exposes-530-million-facebook-says-it-will-not-notify-users) ujawnił dane 530 milionów użytkowników, co skutkowało ugodą z FTC na kwotę 5 miliardów dolarów. Jednak Facebook odmówił powiadomienia użytkowników o wycieku, naruszając ich prawa dotyczące przejrzystości danych i dostępu. |

Chcesz poznać więcej studiów przypadków? Sprawdź te zasoby:
* [Ethics Unwrapped](https://ethicsunwrapped.utexas.edu/case-studies) - dylematy etyczne w różnych branżach. 
* [Kurs etyki w nauce o danych](https://www.coursera.org/learn/data-science-ethics#syllabus) - omówienie kluczowych studiów przypadków.
* [Gdzie popełniono błędy](https://deon.drivendata.org/examples/) - lista kontrolna Deon z przykładami.

> 🚨 Pomyśl o studiach przypadków, które widziałeś - czy doświadczyłeś lub byłeś dotknięty podobnym wyzwaniem etycznym w swoim życiu? Czy możesz wymienić przynajmniej jedno inne studium przypadku ilustrujące jedno z omawianych wyzwań etycznych?

## Etyka stosowana

Omówiliśmy koncepcje etyczne, wyzwania i studia przypadków w kontekstach rzeczywistych. Ale jak zacząć _stosować_ zasady i praktyki etyczne w naszych projektach? I jak _operacjonalizować_ te praktyki dla lepszego zarządzania? Przyjrzyjmy się kilku rzeczywistym rozwiązaniom:

### 1. Kodeksy zawodowe

Kodeksy zawodowe oferują jedną z opcji dla organizacji, aby "zachęcać" członków do wspierania ich zasad etycznych i misji. Kodeksy są _moralnymi wytycznymi_ dotyczącymi zachowań zawodowych, pomagającymi pracownikom lub członkom podejmować decyzje zgodne z zasadami organizacji. Są one skuteczne tylko w takim stopniu, w jakim członkowie dobrowolnie ich przestrzegają; jednak wiele organizacji oferuje dodatkowe nagrody i kary, aby motywować członków do przestrzegania kodeksu.

Przykłady obejmują:

 * [Kodeks etyki Oxford Munich](http://www.code-of-ethics.org/code-of-conduct/) 
 * [Kodeks postępowania Stowarzyszenia Nauki o Danych](http://datascienceassn.org/code-of-conduct.html) (stworzony w 2013 roku)
 * [Kodeks etyki i postępowania zawodowego ACM](https://www.acm.org/code-of-ethics) (od 1993 roku)

> 🚨 Czy należysz do organizacji inżynierskiej lub związanej z nauką o danych? Sprawdź ich stronę, aby zobaczyć, czy definiują kodeks etyki zawodowej. Co mówi on o ich zasadach etycznych? Jak "zachęcają" członków do przestrzegania kodeksu?

### 2. Listy kontrolne etyki

Podczas gdy kodeksy zawodowe definiują wymagane _zachowania etyczne_ praktyków, [mają znane ograniczenia](https://resources.oreilly.com/examples/0636920203964/blob/master/of_oaths_and_checklists.md) w egzekwowaniu, szczególnie w dużych projektach. Zamiast tego wielu ekspertów ds. nauki o danych [zaleca stosowanie list kontrolnych](https://resources.oreilly.com/examples/0636920203964/blob/master/of_oaths_and_checklists.md), które mogą **połączyć zasady z praktykami** w bardziej deterministyczny i wykonalny sposób.

Listy kontrolne przekształcają pytania w zadania "tak/nie", które można operacjonalizować, umożliwiając ich śledzenie jako część standardowych procesów wydawania produktów.

Przykłady obejmują:
 * [Deon](https://deon.drivendata.org/) - ogólna lista kontrolna etyki danych stworzona na podstawie [rekomendacji branżowych](https://deon.drivendata.org/#checklist-citations) z narzędziem wiersza poleceń do łatwej integracji.
 * [Lista kontrolna audytu prywatności](https://cyber.harvard.edu/ecommerce/privacyaudit.html) - zapewnia ogólne wskazówki dotyczące praktyk zarządzania informacjami z perspektywy prawnej i społecznej.
 * [Lista kontrolna AI Fairness](https://www.microsoft.com/en-us/research/project/ai-fairness-checklist/) - stworzona przez praktyków AI, aby wspierać przyjęcie i integrację sprawdzania sprawiedliwości w cyklach rozwoju AI.
 * [22 pytania dotyczące etyki w danych i AI](https://medium.com/the-organization/22-questions-for-ethics-in-data-and-ai-efb68fd19429) - bardziej otwarta struktura, zaprojektowana do wstępnej eksploracji problemów etycznych w projektowaniu, wdrażaniu i kontekstach organizacyjnych.

### 3. Regulacje etyczne

Etyka dotyczy definiowania wspólnych wartości i dobrowolnego postępowania zgodnie z nimi. **Zgodność** dotyczy _przestrzegania prawa_, jeśli i gdzie jest ono zdefiniowane. **Zarządzanie** obejmuje szeroko wszystkie sposoby, w jakie organizacje działają, aby egzekwować zasady etyczne i przestrzegać ustanowionych przepisów.

Obecnie zarządzanie przyjmuje dwie formy w organizacjach. Po pierwsze, chodzi o definiowanie zasad **etycznego AI** i ustanawianie praktyk, które umożliwiają ich wdrożenie we wszystkich projektach związanych z AI w organizacji. Po drugie, chodzi o przestrzeganie wszystkich rządowych regulacji dotyczących **ochrony danych** w regionach, w których organizacja działa.

Przykłady regulacji dotyczących ochrony danych i prywatności:

 * `1974`, [Ustawa o prywatności w USA](https://www.justice.gov/opcl/privacy-act-1974) - reguluje _federalne_ zbieranie, wykorzystywanie i ujawnianie danych osobowych.
 * `1996`, [Ustawa o przenośności i odpowiedzialności w ubezpieczeniach zdrowotnych w USA (HIPAA)](https://www.cdc.gov/phlp/publications/topic/hipaa.html) - chroni dane osobowe dotyczące zdrowia.
 * `1998`, [Ustawa o ochronie prywatności dzieci w Internecie w USA (COPPA)](https://www.ftc.gov/enforcement/rules/rulemaking-regulatory-reform-proceedings/childrens-online-privacy-protection-rule) - chroni prywatność danych dzieci poniżej 13 roku życia.
 * `2018`, [Ogólne rozporządzenie o ochronie danych (GDPR)](https://gdpr-info.eu/) - zapewnia prawa użytkowników, ochronę danych i prywatność.
 * `2018`, [Ustawa o ochronie prywatności konsumentów w Kalifornii (CCPA)](https://www.oag.ca.gov/privacy/ccpa) - daje konsumentom większe _prawa_ dotyczące ich danych osobowych.
 * `2021`, Chińska [Ustawa o ochronie danych osobowych](https://www.reuters.com/world/china/china-passes-new-personal-data-privacy-law-take-effect-nov-1-2021-08-20/) - jedna z najsilniejszych regulacji dotyczących prywatności danych online na świecie.

> 🚨 Ogólne rozporządzenie o ochronie danych (GDPR) zdefiniowane przez Unię Europejską pozostaje jednym z najbardziej wpływowych regulacji dotyczących prywatności danych. Czy wiesz, że definiuje również [8 praw użytkowników](https://www.freeprivacypolicy.com/blog/8-user-rights-gdpr), aby chronić cyfrową prywatność i dane osobowe obywateli? Dowiedz się, czym są te prawa i dlaczego są ważne.

### 4. Kultura etyki

Należy zauważyć, że istnieje niematerialna luka między _zgodnością_ (robieniem wystarczająco dużo, aby spełnić "literę prawa") a rozwiązywaniem [systemowych problemów](https://www.coursera.org/learn/data-science-ethics/home/week/4) (takich jak skostnienie, asymetria informacji i niesprawiedliwość dystrybucyjna), które mogą przyspieszyć wykorzystanie AI w szkodliwy sposób.

To drugie wymaga [współpracy w definiowaniu kultur etycznych](https://towardsdatascience.com/why-ai-ethics-requires-a-culture-driven-approach-26f451afa29f), które budują emocjonalne więzi i spójne wspólne wartości _w organizacjach_ w branży. Wymaga to bardziej [sformalizowanych kultur etyki danych](https://www.codeforamerica.org/news/formalizing-an-ethical-data-culture/) w organizacjach - umożliwiając _każdemu_ [pociągnięcie za sznur Andon](https://en.wikipedia.org/wiki/Andon_(manufacturing)) (aby zgłosić obawy etyczne na wczesnym etapie procesu) i uczynienie _ocen etycznych_ (np. w rekrutacji) kluczowym kryterium formowania zespołów w projektach AI.

---
## [Quiz po wykładzie](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/3) 🎯
## Przegląd i samodzielna nauka 

Kursy i książki pomagają zrozumieć podstawowe koncepcje etyczne i wyzwania, podczas gdy studia przypadków i narzędzia pomagają w stosowaniu praktyk etycznych w rzeczywistych kontekstach. Oto kilka zasobów na początek:

* [Uczenie maszynowe dla początkujących](https://github.com/microsoft/ML-For-Beginners
* [Zasady Odpowiedzialnej AI](https://docs.microsoft.com/en-us/learn/modules/responsible-ai-principles/) - darmowy kurs edukacyjny od Microsoft Learn.
* [Etyka i Data Science](https://resources.oreilly.com/examples/0636920203964) - EBook od O'Reilly (M. Loukides, H. Mason i in.)
* [Etyka w Data Science](https://www.coursera.org/learn/data-science-ethics#syllabus) - kurs online od Uniwersytetu Michigan.
* [Etyka Rozwinięta](https://ethicsunwrapped.utexas.edu/case-studies) - studia przypadków od Uniwersytetu Teksasu.

# Zadanie 

[Napisz studium przypadku dotyczące etyki danych](assignment.md)

**Zastrzeżenie**:  
Ten dokument został przetłumaczony za pomocą usługi tłumaczenia AI [Co-op Translator](https://github.com/Azure/co-op-translator). Chociaż dokładamy wszelkich starań, aby tłumaczenie było precyzyjne, prosimy pamiętać, że automatyczne tłumaczenia mogą zawierać błędy lub nieścisłości. Oryginalny dokument w jego rodzimym języku powinien być uznawany za wiarygodne źródło. W przypadku informacji o kluczowym znaczeniu zaleca się skorzystanie z profesjonalnego tłumaczenia wykonanego przez człowieka. Nie ponosimy odpowiedzialności za jakiekolwiek nieporozumienia lub błędne interpretacje wynikające z użycia tego tłumaczenia.