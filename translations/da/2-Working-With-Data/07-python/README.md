<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "116c5d361fbe812e59a73f37ce721d36",
  "translation_date": "2025-08-26T21:03:35+00:00",
  "source_file": "2-Working-With-Data/07-python/README.md",
  "language_code": "da"
}
-->
# Arbejde med Data: Python og Pandas-biblioteket

| ![ Sketchnote af [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/07-WorkWithPython.png) |
| :-------------------------------------------------------------------------------------------------------: |
|                 Arbejde med Python - _Sketchnote af [@nitya](https://twitter.com/nitya)_                 |

[![Introduktionsvideo](../../../../translated_images/video-ds-python.245247dc811db8e4d5ac420246de8a118c63fd28f6a56578d08b630ae549f260.da.png)](https://youtu.be/dZjWOGbsN4Y)

Selvom databaser tilbyder meget effektive måder at gemme data og forespørge dem ved hjælp af forespørgselssprog, er den mest fleksible måde at bearbejde data på at skrive dit eget program til at manipulere data. I mange tilfælde vil en databaseforespørgsel være en mere effektiv løsning. Men i nogle tilfælde, hvor mere kompleks databehandling er nødvendig, kan det ikke nemt gøres med SQL.  
Databehandling kan programmeres i ethvert programmeringssprog, men der er visse sprog, der er mere avancerede med hensyn til arbejde med data. Dataforskere foretrækker typisk et af følgende sprog:

* **[Python](https://www.python.org/)**, et generelt programmeringssprog, som ofte betragtes som en af de bedste muligheder for begyndere på grund af dets enkelhed. Python har mange ekstra biblioteker, der kan hjælpe dig med at løse praktiske problemer, såsom at udtrække data fra en ZIP-arkiv eller konvertere et billede til gråtoner. Ud over data science bruges Python også ofte til webudvikling.  
* **[R](https://www.r-project.org/)** er et traditionelt værktøj udviklet med statistisk databehandling i tankerne. Det indeholder også et stort bibliotek af pakker (CRAN), hvilket gør det til et godt valg til databehandling. Dog er R ikke et generelt programmeringssprog og bruges sjældent uden for data science-domænet.  
* **[Julia](https://julialang.org/)** er et andet sprog udviklet specifikt til data science. Det er designet til at give bedre ydeevne end Python, hvilket gør det til et fremragende værktøj til videnskabelige eksperimenter.

I denne lektion vil vi fokusere på at bruge Python til simpel databehandling. Vi antager grundlæggende kendskab til sproget. Hvis du ønsker en dybere introduktion til Python, kan du henvise til en af følgende ressourcer:

* [Lær Python på en sjov måde med Turtle Graphics og Fractals](https://github.com/shwars/pycourse) - GitHub-baseret hurtig introduktionskursus til Python-programmering  
* [Tag dine første skridt med Python](https://docs.microsoft.com/en-us/learn/paths/python-first-steps/?WT.mc_id=academic-77958-bethanycheum) Læringssti på [Microsoft Learn](http://learn.microsoft.com/?WT.mc_id=academic-77958-bethanycheum)

Data kan komme i mange former. I denne lektion vil vi se på tre former for data - **tabulære data**, **tekst** og **billeder**.

Vi vil fokusere på nogle få eksempler på databehandling i stedet for at give dig en fuld oversigt over alle relaterede biblioteker. Dette vil give dig en idé om, hvad der er muligt, og efterlade dig med en forståelse af, hvor du kan finde løsninger på dine problemer, når du har brug for dem.

> **Det mest nyttige råd**. Når du skal udføre en bestemt operation på data, som du ikke ved, hvordan du gør, så prøv at søge efter det på internettet. [Stackoverflow](https://stackoverflow.com/) indeholder ofte mange nyttige kodeeksempler i Python til mange typiske opgaver.

## [Quiz før lektionen](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/12)

## Tabulære Data og Dataframes

Du har allerede stiftet bekendtskab med tabulære data, da vi talte om relationelle databaser. Når du har mange data, og de er indeholdt i mange forskellige sammenkædede tabeller, giver det bestemt mening at bruge SQL til at arbejde med dem. Men der er mange tilfælde, hvor vi har en tabel med data, og vi skal opnå en **forståelse** eller **indsigt** om disse data, såsom fordeling, korrelation mellem værdier osv. I data science er der mange tilfælde, hvor vi skal udføre nogle transformationer af de oprindelige data, efterfulgt af visualisering. Begge disse trin kan nemt udføres med Python.

Der er to mest nyttige biblioteker i Python, der kan hjælpe dig med at arbejde med tabulære data:
* **[Pandas](https://pandas.pydata.org/)** giver dig mulighed for at manipulere såkaldte **Dataframes**, som er analoge med relationelle tabeller. Du kan have navngivne kolonner og udføre forskellige operationer på rækker, kolonner og dataframes generelt.  
* **[Numpy](https://numpy.org/)** er et bibliotek til at arbejde med **tensore**, dvs. multidimensionelle **arrays**. Arrays har værdier af samme underliggende type og er enklere end dataframes, men de tilbyder flere matematiske operationer og skaber mindre overhead.

Der er også et par andre biblioteker, du bør kende til:
* **[Matplotlib](https://matplotlib.org/)** er et bibliotek, der bruges til datavisualisering og graftegning  
* **[SciPy](https://www.scipy.org/)** er et bibliotek med nogle ekstra videnskabelige funktioner. Vi er allerede stødt på dette bibliotek, da vi talte om sandsynlighed og statistik  

Her er et stykke kode, som du typisk vil bruge til at importere disse biblioteker i begyndelsen af dit Python-program:
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from scipy import ... # you need to specify exact sub-packages that you need
```

Pandas er centreret omkring nogle få grundlæggende begreber.

### Series

**Series** er en sekvens af værdier, der ligner en liste eller numpy-array. Den største forskel er, at en series også har en **indeks**, og når vi opererer på series (f.eks. lægger dem sammen), tages indekset i betragtning. Indekset kan være så simpelt som et heltal (det er standardindekset, når man opretter en series fra en liste eller et array), eller det kan have en kompleks struktur, såsom et datointerval.

> **Bemærk**: Der er noget introducerende Pandas-kode i den medfølgende notebook [`notebook.ipynb`](notebook.ipynb). Vi skitserer kun nogle af eksemplerne her, og du er bestemt velkommen til at tjekke hele notebooken.

Lad os tage et eksempel: vi vil analysere salget fra vores isbod. Lad os generere en series af salgsnumre (antal solgte varer hver dag) for en given tidsperiode:

```python
start_date = "Jan 1, 2020"
end_date = "Mar 31, 2020"
idx = pd.date_range(start_date,end_date)
print(f"Length of index is {len(idx)}")
items_sold = pd.Series(np.random.randint(25,50,size=len(idx)),index=idx)
items_sold.plot()
```
![Tidsserieplot](../../../../translated_images/timeseries-1.80de678ab1cf727e50e00bcf24009fa2b0a8b90ebc43e34b99a345227d28e467.da.png)

Antag nu, at vi hver uge arrangerer en fest for venner, og vi tager yderligere 10 pakker is med til festen. Vi kan oprette en anden series, indekseret efter uge, for at demonstrere dette:
```python
additional_items = pd.Series(10,index=pd.date_range(start_date,end_date,freq="W"))
```
Når vi lægger to series sammen, får vi det samlede antal:
```python
total_items = items_sold.add(additional_items,fill_value=0)
total_items.plot()
```
![Tidsserieplot](../../../../translated_images/timeseries-2.aae51d575c55181ceda81ade8c546a2fc2024f9136934386d57b8a189d7570ff.da.png)

> **Bemærk** at vi ikke bruger den simple syntaks `total_items+additional_items`. Hvis vi gjorde det, ville vi få mange `NaN` (*Not a Number*) værdier i den resulterende series. Dette skyldes, at der mangler værdier for nogle af indeksene i `additional_items`-serien, og at lægge `NaN` til noget resulterer i `NaN`. Derfor skal vi angive parameteren `fill_value` under additionen.

Med tidsserier kan vi også **resample** serien med forskellige tidsintervaller. For eksempel, hvis vi vil beregne gennemsnitligt salgsvolumen månedligt, kan vi bruge følgende kode:
```python
monthly = total_items.resample("1M").mean()
ax = monthly.plot(kind='bar')
```
![Månedlige tidsserie-gennemsnit](../../../../translated_images/timeseries-3.f3147cbc8c624881008564bc0b5d9fcc15e7374d339da91766bd0e1c6bd9e3af.da.png)

### DataFrame

En DataFrame er i bund og grund en samling af series med samme indeks. Vi kan kombinere flere series sammen til en DataFrame:
```python
a = pd.Series(range(1,10))
b = pd.Series(["I","like","to","play","games","and","will","not","change"],index=range(0,9))
df = pd.DataFrame([a,b])
```
Dette vil skabe en horisontal tabel som denne:
|     | 0   | 1    | 2   | 3   | 4      | 5   | 6      | 7    | 8    |
| --- | --- | ---- | --- | --- | ------ | --- | ------ | ---- | ---- |
| 0   | 1   | 2    | 3   | 4   | 5      | 6   | 7      | 8    | 9    |
| 1   | I   | like | to  | use | Python | and | Pandas | very | much |

Vi kan også bruge Series som kolonner og angive kolonnenavne ved hjælp af en ordbog:
```python
df = pd.DataFrame({ 'A' : a, 'B' : b })
```
Dette vil give os en tabel som denne:

|     | A   | B      |
| --- | --- | ------ |
| 0   | 1   | I      |
| 1   | 2   | like   |
| 2   | 3   | to     |
| 3   | 4   | use    |
| 4   | 5   | Python |
| 5   | 6   | and    |
| 6   | 7   | Pandas |
| 7   | 8   | very   |
| 8   | 9   | much   |

**Bemærk** at vi også kan få dette tabel-layout ved at transponere den tidligere tabel, f.eks. ved at skrive 
```python
df = pd.DataFrame([a,b]).T..rename(columns={ 0 : 'A', 1 : 'B' })
```
Her betyder `.T` operationen at transponere DataFrame, dvs. bytte rækker og kolonner, og `rename`-operationen giver os mulighed for at omdøbe kolonnerne, så de matcher det tidligere eksempel.

Her er nogle af de vigtigste operationer, vi kan udføre på DataFrames:

**Kolonnevalg**. Vi kan vælge individuelle kolonner ved at skrive `df['A']` - denne operation returnerer en Series. Vi kan også vælge et underudvalg af kolonner til en anden DataFrame ved at skrive `df[['B','A']]` - dette returnerer en ny DataFrame.

**Filtrering** af kun visse rækker baseret på kriterier. For eksempel, for kun at beholde rækker, hvor kolonnen `A` er større end 5, kan vi skrive `df[df['A']>5]`.

> **Bemærk**: Sådan fungerer filtrering. Udtrykket `df['A']<5` returnerer en boolsk series, der angiver, om udtrykket er `True` eller `False` for hvert element i den oprindelige series `df['A']`. Når en boolsk series bruges som indeks, returnerer det et underudvalg af rækker i DataFrame. Derfor er det ikke muligt at bruge vilkårlige Python-boolske udtryk, f.eks. at skrive `df[df['A']>5 and df['A']<7]` ville være forkert. I stedet skal du bruge den specielle `&`-operation på boolske series, ved at skrive `df[(df['A']>5) & (df['A']<7)]` (*parenteser er vigtige her*).

**Oprettelse af nye beregnelige kolonner**. Vi kan nemt oprette nye beregnelige kolonner til vores DataFrame ved at bruge intuitive udtryk som dette:
```python
df['DivA'] = df['A']-df['A'].mean() 
``` 
Dette eksempel beregner afvigelsen af A fra dens gennemsnitsværdi. Hvad der faktisk sker her, er, at vi beregner en series og derefter tildeler denne series til venstre side, hvilket skaber en ny kolonne. Derfor kan vi ikke bruge operationer, der ikke er kompatible med series, f.eks. nedenstående kode, som er forkert:
```python
# Wrong code -> df['ADescr'] = "Low" if df['A'] < 5 else "Hi"
df['LenB'] = len(df['B']) # <- Wrong result
``` 
Det sidste eksempel, selvom det er syntaktisk korrekt, giver os et forkert resultat, fordi det tildeler længden af serien `B` til alle værdier i kolonnen og ikke længden af de individuelle elementer, som vi havde tænkt os.

Hvis vi har brug for at beregne komplekse udtryk som dette, kan vi bruge funktionen `apply`. Det sidste eksempel kan skrives som følger:
```python
df['LenB'] = df['B'].apply(lambda x : len(x))
# or 
df['LenB'] = df['B'].apply(len)
```

Efter ovenstående operationer ender vi med følgende DataFrame:

|     | A   | B      | DivA | LenB |
| --- | --- | ------ | ---- | ---- |
| 0   | 1   | I      | -4.0 | 1    |
| 1   | 2   | like   | -3.0 | 4    |
| 2   | 3   | to     | -2.0 | 2    |
| 3   | 4   | use    | -1.0 | 3    |
| 4   | 5   | Python | 0.0  | 6    |
| 5   | 6   | and    | 1.0  | 3    |
| 6   | 7   | Pandas | 2.0  | 6    |
| 7   | 8   | very   | 3.0  | 4    |
| 8   | 9   | much   | 4.0  | 4    |

**Valg af rækker baseret på numre** kan gøres ved hjælp af `iloc`-konstruktionen. For eksempel, for at vælge de første 5 rækker fra DataFrame:
```python
df.iloc[:5]
```

**Gruppering** bruges ofte til at opnå et resultat, der ligner *pivot-tabeller* i Excel. Antag, at vi vil beregne gennemsnitsværdien af kolonnen `A` for hver given værdi af `LenB`. Så kan vi gruppere vores DataFrame efter `LenB` og kalde `mean`:
```python
df.groupby(by='LenB').mean()
```
Hvis vi har brug for at beregne gennemsnit og antallet af elementer i gruppen, kan vi bruge den mere komplekse `aggregate`-funktion:
```python
df.groupby(by='LenB') \
 .aggregate({ 'DivA' : len, 'A' : lambda x: x.mean() }) \
 .rename(columns={ 'DivA' : 'Count', 'A' : 'Mean'})
```
Dette giver os følgende tabel:

| LenB | Count | Mean     |
| ---- | ----- | -------- |
| 1    | 1     | 1.000000 |
| 2    | 1     | 3.000000 |
| 3    | 2     | 5.000000 |
| 4    | 3     | 6.333333 |
| 6    | 2     | 6.000000 |

### Hentning af Data
Vi har set, hvor nemt det er at oprette Series og DataFrames fra Python-objekter. Dog kommer data ofte i form af en tekstfil eller en Excel-tabel. Heldigvis tilbyder Pandas en enkel måde at indlæse data fra disk. For eksempel er det lige så nemt at læse en CSV-fil som dette:  
```python
df = pd.read_csv('file.csv')
```  
Vi vil se flere eksempler på, hvordan man indlæser data, herunder at hente det fra eksterne websteder, i afsnittet "Udfordring".

### Udskrivning og Visualisering

En Data Scientist skal ofte udforske data, og derfor er det vigtigt at kunne visualisere dem. Når en DataFrame er stor, vil vi ofte bare sikre os, at vi gør alt korrekt, ved at udskrive de første par rækker. Dette kan gøres ved at kalde `df.head()`. Hvis du kører det fra Jupyter Notebook, vil det udskrive DataFrame i en pæn tabelform.

Vi har også set brugen af funktionen `plot` til at visualisere nogle kolonner. Selvom `plot` er meget nyttig til mange opgaver og understøtter mange forskellige graf-typer via parameteren `kind=`, kan du altid bruge det rå `matplotlib`-bibliotek til at lave noget mere komplekst. Vi vil dække datavisualisering i detaljer i separate kursuslektioner.

Denne oversigt dækker de vigtigste koncepter i Pandas, men biblioteket er meget rigt, og der er ingen grænser for, hvad du kan gøre med det! Lad os nu anvende denne viden til at løse et specifikt problem.

## 🚀 Udfordring 1: Analyse af COVID-spredning

Det første problem, vi vil fokusere på, er modellering af den epidemiske spredning af COVID-19. For at gøre dette vil vi bruge data om antallet af smittede personer i forskellige lande, leveret af [Center for Systems Science and Engineering](https://systems.jhu.edu/) (CSSE) ved [Johns Hopkins University](https://jhu.edu/). Datasættet er tilgængeligt i [dette GitHub-repository](https://github.com/CSSEGISandData/COVID-19).

Da vi ønsker at demonstrere, hvordan man arbejder med data, inviterer vi dig til at åbne [`notebook-covidspread.ipynb`](notebook-covidspread.ipynb) og læse det fra top til bund. Du kan også udføre celler og løse nogle udfordringer, vi har efterladt til dig i slutningen.

![COVID-spredning](../../../../translated_images/covidspread.f3d131c4f1d260ab0344d79bac0abe7924598dd754859b165955772e1bd5e8a2.da.png)

> Hvis du ikke ved, hvordan man kører kode i Jupyter Notebook, kan du se [denne artikel](https://soshnikov.com/education/how-to-execute-notebooks-from-github/).

## Arbejde med Ustrukturerede Data

Selvom data meget ofte kommer i tabelform, skal vi i nogle tilfælde arbejde med mindre strukturerede data, for eksempel tekst eller billeder. I dette tilfælde skal vi for at anvende de databehandlingsteknikker, vi har set ovenfor, på en eller anden måde **udtrække** strukturerede data. Her er nogle eksempler:

* Udtrække nøgleord fra tekst og se, hvor ofte disse nøgleord optræder
* Bruge neurale netværk til at udtrække information om objekter på et billede
* Få information om folks følelser fra et videokamerafeed

## 🚀 Udfordring 2: Analyse af COVID-artikler

I denne udfordring fortsætter vi med emnet COVID-pandemien og fokuserer på behandling af videnskabelige artikler om emnet. Der findes [CORD-19-datasættet](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge) med mere end 7000 (på tidspunktet for skrivning) artikler om COVID, tilgængeligt med metadata og abstracts (og for omkring halvdelen af dem er der også fuld tekst tilgængelig).

Et fuldt eksempel på analyse af dette datasæt ved hjælp af [Text Analytics for Health](https://docs.microsoft.com/azure/cognitive-services/text-analytics/how-tos/text-analytics-for-health/?WT.mc_id=academic-77958-bethanycheum) kognitive tjeneste er beskrevet [i dette blogindlæg](https://soshnikov.com/science/analyzing-medical-papers-with-azure-and-text-analytics-for-health/). Vi vil diskutere en forenklet version af denne analyse.

> **NOTE**: Vi leverer ikke en kopi af datasættet som en del af dette repository. Du skal muligvis først downloade filen [`metadata.csv`](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge?select=metadata.csv) fra [dette datasæt på Kaggle](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge). Registrering hos Kaggle kan være påkrævet. Du kan også downloade datasættet uden registrering [herfra](https://ai2-semanticscholar-cord-19.s3-us-west-2.amazonaws.com/historical_releases.html), men det vil inkludere alle fulde tekster ud over metadatafilen.

Åbn [`notebook-papers.ipynb`](notebook-papers.ipynb) og læs det fra top til bund. Du kan også udføre celler og løse nogle udfordringer, vi har efterladt til dig i slutningen.

![COVID Medicinsk Behandling](../../../../translated_images/covidtreat.b2ba59f57ca45fbcda36e0ddca3f8cfdddeeed6ca879ea7f866d93fa6ec65791.da.png)

## Behandling af Billeddata

For nylig er der udviklet meget kraftfulde AI-modeller, der gør det muligt for os at forstå billeder. Der er mange opgaver, der kan løses ved hjælp af forudtrænede neurale netværk eller cloud-tjenester. Nogle eksempler inkluderer:

* **Billedklassifikation**, som kan hjælpe dig med at kategorisere billedet i en af de foruddefinerede klasser. Du kan nemt træne dine egne billedklassifikatorer ved hjælp af tjenester som [Custom Vision](https://azure.microsoft.com/services/cognitive-services/custom-vision-service/?WT.mc_id=academic-77958-bethanycheum)
* **Objektdetektion** til at finde forskellige objekter på billedet. Tjenester som [computer vision](https://azure.microsoft.com/services/cognitive-services/computer-vision/?WT.mc_id=academic-77958-bethanycheum) kan finde en række almindelige objekter, og du kan træne en [Custom Vision](https://azure.microsoft.com/services/cognitive-services/custom-vision-service/?WT.mc_id=academic-77958-bethanycheum)-model til at finde specifikke objekter af interesse.
* **Ansigtsgenkendelse**, herunder alder, køn og følelsesdetektion. Dette kan gøres via [Face API](https://azure.microsoft.com/services/cognitive-services/face/?WT.mc_id=academic-77958-bethanycheum).

Alle disse cloud-tjenester kan kaldes ved hjælp af [Python SDK'er](https://docs.microsoft.com/samples/azure-samples/cognitive-services-python-sdk-samples/cognitive-services-python-sdk-samples/?WT.mc_id=academic-77958-bethanycheum) og kan derfor nemt integreres i din dataudforskningsarbejdsgang.

Her er nogle eksempler på at udforske data fra billedkilder:
* I blogindlægget [How to Learn Data Science without Coding](https://soshnikov.com/azure/how-to-learn-data-science-without-coding/) udforsker vi Instagram-billeder og forsøger at forstå, hvad der får folk til at give flere likes til et billede. Vi udtrækker først så meget information som muligt fra billeder ved hjælp af [computer vision](https://azure.microsoft.com/services/cognitive-services/computer-vision/?WT.mc_id=academic-77958-bethanycheum) og bruger derefter [Azure Machine Learning AutoML](https://docs.microsoft.com/azure/machine-learning/concept-automated-ml/?WT.mc_id=academic-77958-bethanycheum) til at bygge en fortolkelig model.
* I [Facial Studies Workshop](https://github.com/CloudAdvocacy/FaceStudies) bruger vi [Face API](https://azure.microsoft.com/services/cognitive-services/face/?WT.mc_id=academic-77958-bethanycheum) til at udtrække følelser fra mennesker på fotografier fra begivenheder for at forsøge at forstå, hvad der gør folk glade.

## Konklusion

Uanset om du allerede har strukturerede eller ustrukturerede data, kan du med Python udføre alle trin relateret til databehandling og forståelse. Det er sandsynligvis den mest fleksible måde at behandle data på, og det er grunden til, at størstedelen af dataforskere bruger Python som deres primære værktøj. At lære Python i dybden er sandsynligvis en god idé, hvis du er seriøs omkring din rejse inden for data science!

## [Quiz efter lektionen](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/13)

## Gennemgang & Selvstudie

**Bøger**  
* [Wes McKinney. Python for Data Analysis: Data Wrangling with Pandas, NumPy, and IPython](https://www.amazon.com/gp/product/1491957662)

**Online Ressourcer**  
* Officiel [10 minutter til Pandas](https://pandas.pydata.org/pandas-docs/stable/user_guide/10min.html) tutorial  
* [Dokumentation om Pandas-visualisering](https://pandas.pydata.org/pandas-docs/stable/user_guide/visualization.html)

**Lær Python**  
* [Lær Python på en sjov måde med Turtle Graphics og Fraktaler](https://github.com/shwars/pycourse)  
* [Tag dine første skridt med Python](https://docs.microsoft.com/learn/paths/python-first-steps/?WT.mc_id=academic-77958-bethanycheum) Læringssti på [Microsoft Learn](http://learn.microsoft.com/?WT.mc_id=academic-77958-bethanycheum)

## Opgave

[Udfør en mere detaljeret dataundersøgelse for ovenstående udfordringer](assignment.md)

## Kreditering

Denne lektion er skrevet med ♥️ af [Dmitry Soshnikov](http://soshnikov.com)

---

**Ansvarsfraskrivelse**:  
Dette dokument er blevet oversat ved hjælp af AI-oversættelsestjenesten [Co-op Translator](https://github.com/Azure/co-op-translator). Selvom vi bestræber os på nøjagtighed, skal det bemærkes, at automatiserede oversættelser kan indeholde fejl eller unøjagtigheder. Det originale dokument på dets oprindelige sprog bør betragtes som den autoritative kilde. For kritisk information anbefales professionel menneskelig oversættelse. Vi påtager os intet ansvar for misforståelser eller fejltolkninger, der måtte opstå som følge af brugen af denne oversættelse.