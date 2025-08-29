<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "cad419b574d5c35eaa417e9abfdcb0c8",
  "translation_date": "2025-08-24T22:39:31+00:00",
  "source_file": "3-Data-Visualization/12-visualization-relationships/README.md",
  "language_code": "de"
}
-->
# Visualisierung von Beziehungen: Alles über Honig 🍯

|![ Sketchnote von [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/12-Visualizing-Relationships.png)|
|:---:|
|Visualisierung von Beziehungen - _Sketchnote von [@nitya](https://twitter.com/nitya)_ |

Im Rahmen unseres naturbezogenen Forschungsfokus wollen wir interessante Visualisierungen entdecken, um die Beziehungen zwischen verschiedenen Honigsorten darzustellen. Grundlage ist ein Datensatz des [United States Department of Agriculture](https://www.nass.usda.gov/About_NASS/index.php). 

Dieser Datensatz mit etwa 600 Einträgen zeigt die Honigproduktion in vielen US-Bundesstaaten. So kann man beispielsweise die Anzahl der Bienenvölker, den Ertrag pro Volk, die Gesamtproduktion, Lagerbestände, den Preis pro Pfund und den Wert des produzierten Honigs in einem bestimmten Bundesstaat von 1998 bis 2012 betrachten, wobei jede Zeile ein Jahr pro Bundesstaat repräsentiert.

Es wäre interessant, die Beziehung zwischen der jährlichen Produktion eines Bundesstaates und beispielsweise dem Honigpreis in diesem Bundesstaat zu visualisieren. Alternativ könnte man die Beziehung zwischen den Erträgen pro Volk in verschiedenen Bundesstaaten darstellen. Dieser Zeitraum umfasst auch das verheerende 'CCD' oder 'Colony Collapse Disorder', das erstmals 2006 beobachtet wurde (http://npic.orst.edu/envir/ccd.html). Ein bewegender Datensatz zum Studieren. 🐝

## [Quiz vor der Lektion](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/22)

In dieser Lektion kannst du Seaborn verwenden, eine Bibliothek, die du bereits kennst, um Beziehungen zwischen Variablen zu visualisieren. Besonders interessant ist die Funktion `relplot` von Seaborn, die es ermöglicht, mit Streu- und Liniendiagrammen schnell '[statistische Beziehungen](https://seaborn.pydata.org/tutorial/relational.html?highlight=relationships)' darzustellen. Dies hilft Datenwissenschaftlern, besser zu verstehen, wie Variablen miteinander in Beziehung stehen.

## Streudiagramme

Verwende ein Streudiagramm, um zu zeigen, wie sich der Honigpreis Jahr für Jahr in den einzelnen Bundesstaaten entwickelt hat. Seaborn gruppiert mit `relplot` die Daten der Bundesstaaten und zeigt Datenpunkte sowohl für kategoriale als auch numerische Daten an.

Beginnen wir mit dem Import der Daten und Seaborn:

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
honey = pd.read_csv('../../data/honey.csv')
honey.head()
```
Du wirst feststellen, dass die Honigdaten mehrere interessante Spalten enthalten, darunter Jahr und Preis pro Pfund. Lass uns diese Daten erkunden, gruppiert nach US-Bundesstaat:

| state | numcol | yieldpercol | totalprod | stocks   | priceperlb | prodvalue | year |
| ----- | ------ | ----------- | --------- | -------- | ---------- | --------- | ---- |
| AL    | 16000  | 71          | 1136000   | 159000   | 0.72       | 818000    | 1998 |
| AZ    | 55000  | 60          | 3300000   | 1485000  | 0.64       | 2112000   | 1998 |
| AR    | 53000  | 65          | 3445000   | 1688000  | 0.59       | 2033000   | 1998 |
| CA    | 450000 | 83          | 37350000  | 12326000 | 0.62       | 23157000  | 1998 |
| CO    | 27000  | 72          | 1944000   | 1594000  | 0.7        | 1361000   | 1998 |

Erstelle ein einfaches Streudiagramm, um die Beziehung zwischen dem Preis pro Pfund Honig und seinem Ursprungsbundesstaat darzustellen. Mache die `y`-Achse hoch genug, um alle Bundesstaaten anzuzeigen:

```python
sns.relplot(x="priceperlb", y="state", data=honey, height=15, aspect=.5);
```
![scatterplot 1](../../../../translated_images/scatter1.5e1aa5fd6706c5d12b5e503ccb77f8a930f8620f539f524ddf56a16c039a5d2f.de.png)

Zeige nun dieselben Daten mit einer honigfarbenen Farbpalette, um zu zeigen, wie sich der Preis im Laufe der Jahre entwickelt hat. Dies kannst du tun, indem du einen 'hue'-Parameter hinzufügst, der die Veränderung Jahr für Jahr darstellt:

> ✅ Erfahre mehr über die [Farbpaletten, die du in Seaborn verwenden kannst](https://seaborn.pydata.org/tutorial/color_palettes.html) – probiere eine schöne Regenbogenfarbpalette aus!

```python
sns.relplot(x="priceperlb", y="state", hue="year", palette="YlOrBr", data=honey, height=15, aspect=.5);
```
![scatterplot 2](../../../../translated_images/scatter2.c0041a58621ca702990b001aa0b20cd68c1e1814417139af8a7211a2bed51c5f.de.png)

Mit dieser Farbänderung kannst du deutlich erkennen, dass es im Laufe der Jahre eine starke Preissteigerung pro Pfund Honig gibt. Wenn du einen bestimmten Bundesstaat wie Arizona als Beispiel nimmst, kannst du ein Muster von Preissteigerungen Jahr für Jahr mit wenigen Ausnahmen erkennen:

| state | numcol | yieldpercol | totalprod | stocks  | priceperlb | prodvalue | year |
| ----- | ------ | ----------- | --------- | ------- | ---------- | --------- | ---- |
| AZ    | 55000  | 60          | 3300000   | 1485000 | 0.64       | 2112000   | 1998 |
| AZ    | 52000  | 62          | 3224000   | 1548000 | 0.62       | 1999000   | 1999 |
| AZ    | 40000  | 59          | 2360000   | 1322000 | 0.73       | 1723000   | 2000 |
| AZ    | 43000  | 59          | 2537000   | 1142000 | 0.72       | 1827000   | 2001 |
| AZ    | 38000  | 63          | 2394000   | 1197000 | 1.08       | 2586000   | 2002 |
| AZ    | 35000  | 72          | 2520000   | 983000  | 1.34       | 3377000   | 2003 |
| AZ    | 32000  | 55          | 1760000   | 774000  | 1.11       | 1954000   | 2004 |
| AZ    | 36000  | 50          | 1800000   | 720000  | 1.04       | 1872000   | 2005 |
| AZ    | 30000  | 65          | 1950000   | 839000  | 0.91       | 1775000   | 2006 |
| AZ    | 30000  | 64          | 1920000   | 902000  | 1.26       | 2419000   | 2007 |
| AZ    | 25000  | 64          | 1600000   | 336000  | 1.26       | 2016000   | 2008 |
| AZ    | 20000  | 52          | 1040000   | 562000  | 1.45       | 1508000   | 2009 |
| AZ    | 24000  | 77          | 1848000   | 665000  | 1.52       | 2809000   | 2010 |
| AZ    | 23000  | 53          | 1219000   | 427000  | 1.55       | 1889000   | 2011 |
| AZ    | 22000  | 46          | 1012000   | 253000  | 1.79       | 1811000   | 2012 |

Eine andere Möglichkeit, diese Entwicklung darzustellen, ist die Verwendung der Größe anstelle von Farbe. Für farbenblinde Nutzer könnte dies eine bessere Option sein. Bearbeite deine Visualisierung so, dass die Preissteigerung durch eine Zunahme des Punktumfangs dargestellt wird:

```python
sns.relplot(x="priceperlb", y="state", size="year", data=honey, height=15, aspect=.5);
```
Du kannst sehen, wie die Größe der Punkte allmählich zunimmt.

![scatterplot 3](../../../../translated_images/scatter3.3c160a3d1dcb36b37900ebb4cf97f34036f28ae2b7b8e6062766c7c1dfc00853.de.png)

Ist dies ein einfacher Fall von Angebot und Nachfrage? Aufgrund von Faktoren wie Klimawandel und dem Bienensterben gibt es möglicherweise Jahr für Jahr weniger Honig zu kaufen, was den Preis steigen lässt.

Um eine Korrelation zwischen einigen Variablen in diesem Datensatz zu entdecken, lass uns einige Liniendiagramme untersuchen.

## Liniendiagramme

Frage: Gibt es einen klaren Anstieg des Honigpreises pro Pfund Jahr für Jahr? Dies kannst du am einfachsten mit einem einzigen Liniendiagramm herausfinden:

```python
sns.relplot(x="year", y="priceperlb", kind="line", data=honey);
```
Antwort: Ja, mit einigen Ausnahmen um das Jahr 2003:

![line chart 1](../../../../translated_images/line1.f36eb465229a3b1fe385cdc93861aab3939de987d504b05de0b6cd567ef79f43.de.png)

✅ Da Seaborn die Daten um eine Linie aggregiert, zeigt es "die mehrfachen Messungen an jedem x-Wert, indem es den Mittelwert und das 95%-Konfidenzintervall um den Mittelwert herum darstellt". [Quelle](https://seaborn.pydata.org/tutorial/relational.html). Dieses zeitaufwändige Verhalten kann durch Hinzufügen von `ci=None` deaktiviert werden.

Frage: Kann man im Jahr 2003 auch einen Anstieg des Honigangebots erkennen? Was passiert, wenn du die Gesamtproduktion Jahr für Jahr betrachtest?

```python
sns.relplot(x="year", y="totalprod", kind="line", data=honey);
```

![line chart 2](../../../../translated_images/line2.a5b3493dc01058af6402e657aaa9ae1125fafb5e7d6630c777aa60f900a544e4.de.png)

Antwort: Nicht wirklich. Wenn du die Gesamtproduktion betrachtest, scheint sie in diesem Jahr tatsächlich gestiegen zu sein, obwohl die Honigproduktion im Allgemeinen in diesen Jahren rückläufig ist.

Frage: Was könnte also den Preisanstieg für Honig um das Jahr 2003 verursacht haben?

Um dies herauszufinden, kannst du ein Facet Grid untersuchen.

## Facet Grids

Facet Grids nehmen eine Facette deines Datensatzes (in unserem Fall kannst du 'Jahr' wählen, um nicht zu viele Facetten zu erzeugen). Seaborn kann dann für jede dieser Facetten deiner gewählten x- und y-Koordinaten ein Diagramm erstellen, um den Vergleich zu erleichtern. Fällt das Jahr 2003 in diesem Vergleich auf?

Erstelle ein Facet Grid, indem du weiterhin `relplot` verwendest, wie in der [Seaborn-Dokumentation](https://seaborn.pydata.org/generated/seaborn.FacetGrid.html?highlight=facetgrid#seaborn.FacetGrid) empfohlen.

```python
sns.relplot(
    data=honey, 
    x="yieldpercol", y="numcol",
    col="year", 
    col_wrap=3,
    kind="line"
```
In dieser Visualisierung kannst du den Ertrag pro Volk und die Anzahl der Völker Jahr für Jahr nebeneinander vergleichen, mit einer Wrap-Einstellung von 3 für die Spalten:

![facet grid](../../../../translated_images/facet.6a34851dcd540050dcc0ead741be35075d776741668dd0e42f482c89b114c217.de.png)

Für diesen Datensatz fällt nichts Besonderes in Bezug auf die Anzahl der Völker und deren Ertrag Jahr für Jahr und Bundesstaat für Bundesstaat auf. Gibt es eine andere Möglichkeit, eine Korrelation zwischen diesen beiden Variablen zu finden?

## Dual-Line-Plots

Versuche ein Mehrlinien-Diagramm, indem du zwei Liniendiagramme übereinanderlegst, Seaborns 'despine' verwendest, um die oberen und rechten Achsen zu entfernen, und `ax.twinx` [aus Matplotlib](https://matplotlib.org/stable/api/_as_gen/matplotlib.axes.Axes.twinx.html) nutzt. Twinx ermöglicht es, eine gemeinsame x-Achse zu verwenden und zwei y-Achsen darzustellen. Zeige den Ertrag pro Volk und die Anzahl der Völker übereinandergelegt an:

```python
fig, ax = plt.subplots(figsize=(12,6))
lineplot = sns.lineplot(x=honey['year'], y=honey['numcol'], data=honey, 
                        label = 'Number of bee colonies', legend=False)
sns.despine()
plt.ylabel('# colonies')
plt.title('Honey Production Year over Year');

ax2 = ax.twinx()
lineplot2 = sns.lineplot(x=honey['year'], y=honey['yieldpercol'], ax=ax2, color="r", 
                         label ='Yield per colony', legend=False) 
sns.despine(right=False)
plt.ylabel('colony yield')
ax.figure.legend();
```
![superimposed plots](../../../../translated_images/dual-line.a4c28ce659603fab2c003f4df816733df2bf41d1facb7de27989ec9afbf01b33.de.png)

Auch wenn um das Jahr 2003 nichts ins Auge springt, können wir diese Lektion mit einer etwas positiveren Note beenden: Während die Anzahl der Bienenvölker insgesamt abnimmt, stabilisiert sich ihre Anzahl, auch wenn der Ertrag pro Volk sinkt.

Go, bees, go!

🐝❤️
## 🚀 Herausforderung

In dieser Lektion hast du mehr über die Verwendung von Streudiagrammen und Linienrastern, einschließlich Facet Grids, gelernt. Fordere dich selbst heraus, ein Facet Grid mit einem anderen Datensatz zu erstellen, vielleicht einem, den du in früheren Lektionen verwendet hast. Beachte, wie lange es dauert, sie zu erstellen, und sei vorsichtig, wie viele Grids du mit diesen Techniken zeichnen möchtest.
## [Quiz nach der Lektion](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/23)

## Rückblick & Selbststudium

Liniendiagramme können einfach oder recht komplex sein. Lies ein wenig in der [Seaborn-Dokumentation](https://seaborn.pydata.org/generated/seaborn.lineplot.html) über die verschiedenen Möglichkeiten, wie du sie erstellen kannst. Versuche, die in dieser Lektion erstellten Liniendiagramme mit anderen in der Dokumentation aufgeführten Methoden zu verbessern.
## Aufgabe

[Abtauchen in den Bienenstock](assignment.md)

**Haftungsausschluss**:  
Dieses Dokument wurde mit dem KI-Übersetzungsdienst [Co-op Translator](https://github.com/Azure/co-op-translator) übersetzt. Obwohl wir uns um Genauigkeit bemühen, weisen wir darauf hin, dass automatisierte Übersetzungen Fehler oder Ungenauigkeiten enthalten können. Das Originaldokument in seiner ursprünglichen Sprache sollte als maßgebliche Quelle betrachtet werden. Für kritische Informationen wird eine professionelle menschliche Übersetzung empfohlen. Wir übernehmen keine Haftung für Missverständnisse oder Fehlinterpretationen, die sich aus der Nutzung dieser Übersetzung ergeben.