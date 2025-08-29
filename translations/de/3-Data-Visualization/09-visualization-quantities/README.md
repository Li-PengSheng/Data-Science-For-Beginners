<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "43c402d9d90ae6da55d004519ada5033",
  "translation_date": "2025-08-24T23:01:22+00:00",
  "source_file": "3-Data-Visualization/09-visualization-quantities/README.md",
  "language_code": "de"
}
-->
# Visualisierung von Mengen

|![ Sketchnote von [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/09-Visualizing-Quantities.png)|
|:---:|
| Visualisierung von Mengen - _Sketchnote von [@nitya](https://twitter.com/nitya)_ |

In dieser Lektion wirst du erkunden, wie man eine der vielen verfügbaren Python-Bibliotheken verwendet, um interessante Visualisierungen rund um das Konzept der Menge zu erstellen. Mit einem bereinigten Datensatz über die Vögel von Minnesota kannst du viele interessante Fakten über die lokale Tierwelt lernen.  
## [Quiz vor der Lektion](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/16)

## Beobachte die Flügelspannweite mit Matplotlib

Eine ausgezeichnete Bibliothek, um sowohl einfache als auch anspruchsvolle Diagramme und Grafiken verschiedener Art zu erstellen, ist [Matplotlib](https://matplotlib.org/stable/index.html). Allgemein umfasst der Prozess des Plottens von Daten mit diesen Bibliotheken das Identifizieren der Teile deines DataFrames, die du anvisieren möchtest, das Durchführen notwendiger Transformationen der Daten, das Zuweisen von x- und y-Achsenwerten, das Entscheiden, welche Art von Diagramm angezeigt werden soll, und schließlich das Anzeigen des Diagramms. Matplotlib bietet eine große Vielfalt an Visualisierungen, aber für diese Lektion konzentrieren wir uns auf die am besten geeigneten für die Visualisierung von Mengen: Liniendiagramme, Streudiagramme und Balkendiagramme.

> ✅ Wähle das beste Diagramm, das zur Struktur deiner Daten und der Geschichte, die du erzählen möchtest, passt.  
> - Um Trends über die Zeit zu analysieren: Linie  
> - Um Werte zu vergleichen: Balken, Säulen, Kreisdiagramm, Streudiagramm  
> - Um zu zeigen, wie Teile zu einem Ganzen gehören: Kreisdiagramm  
> - Um die Verteilung von Daten zu zeigen: Streudiagramm, Balken  
> - Um Trends zu zeigen: Linie, Säule  
> - Um Beziehungen zwischen Werten zu zeigen: Linie, Streudiagramm, Blasendiagramm  

Wenn du einen Datensatz hast und herausfinden möchtest, wie viel von einem bestimmten Element enthalten ist, wird eine der ersten Aufgaben sein, die Werte zu inspizieren.

✅ Es gibt sehr gute 'Cheat Sheets' für Matplotlib [hier](https://matplotlib.org/cheatsheets/cheatsheets.pdf).

## Erstelle ein Liniendiagramm über die Flügelspannweiten von Vögeln

Öffne die Datei `notebook.ipynb` im Stammverzeichnis dieses Lektionenordners und füge eine Zelle hinzu.

> Hinweis: Die Daten befinden sich im Stammverzeichnis dieses Repos im Ordner `/data`.

```python
import pandas as pd
import matplotlib.pyplot as plt
birds = pd.read_csv('../../data/birds.csv')
birds.head()
```  
Diese Daten sind eine Mischung aus Text und Zahlen:

|      | Name                         | ScientificName         | Category              | Order        | Family   | Genus       | ConservationStatus | MinLength | MaxLength | MinBodyMass | MaxBodyMass | MinWingspan | MaxWingspan |
| ---: | :--------------------------- | :--------------------- | :-------------------- | :----------- | :------- | :---------- | :----------------- | --------: | --------: | ----------: | ----------: | ----------: | ----------: |
|    0 | Schwarzbauch-Pfeifgans       | Dendrocygna autumnalis | Enten/Gänse/Wasservögel | Anseriformes | Anatidae | Dendrocygna | LC                 |        47 |        56 |         652 |        1020 |          76 |          94 |
|    1 | Fuchsrote Pfeifgans          | Dendrocygna bicolor    | Enten/Gänse/Wasservögel | Anseriformes | Anatidae | Dendrocygna | LC                 |        45 |        53 |         712 |        1050 |          85 |          93 |
|    2 | Schneegans                   | Anser caerulescens     | Enten/Gänse/Wasservögel | Anseriformes | Anatidae | Anser       | LC                 |        64 |        79 |        2050 |        4050 |         135 |         165 |
|    3 | Zwerggans                    | Anser rossii           | Enten/Gänse/Wasservögel | Anseriformes | Anatidae | Anser       | LC                 |      57.3 |        64 |        1066 |        1567 |         113 |         116 |
|    4 | Saatgans                     | Anser albifrons        | Enten/Gänse/Wasservögel | Anseriformes | Anatidae | Anser       | LC                 |        64 |        81 |        1930 |        3310 |         130 |         165 |

Beginnen wir damit, einige der numerischen Daten mit einem einfachen Liniendiagramm zu plotten. Angenommen, du möchtest die maximale Flügelspannweite dieser interessanten Vögel betrachten.

```python
wingspan = birds['MaxWingspan'] 
wingspan.plot()
```  
![Max Wingspan](../../../../translated_images/max-wingspan-02.e79fd847b2640b89e21e340a3a9f4c5d4b224c4fcd65f54385e84f1c9ed26d52.de.png)

Was fällt dir sofort auf? Es scheint mindestens einen Ausreißer zu geben – das ist eine beeindruckende Flügelspannweite! Eine Flügelspannweite von 2300 Zentimetern entspricht 23 Metern – gibt es Pterodaktylen in Minnesota? Lass uns das untersuchen.

Während du in Excel schnell sortieren könntest, um diese Ausreißer zu finden, die wahrscheinlich Tippfehler sind, setzen wir den Visualisierungsprozess innerhalb des Diagramms fort.

Füge Beschriftungen zur x-Achse hinzu, um zu zeigen, um welche Vogelarten es sich handelt:

```
plt.title('Max Wingspan in Centimeters')
plt.ylabel('Wingspan (CM)')
plt.xlabel('Birds')
plt.xticks(rotation=45)
x = birds['Name'] 
y = birds['MaxWingspan']

plt.plot(x, y)

plt.show()
```  
![wingspan with labels](../../../../translated_images/max-wingspan-labels-02.aa90e826ca49a9d1dde78075e9755c1849ef56a4e9ec60f7e9f3806daf9283e2.de.png)

Selbst mit einer Drehung der Beschriftungen um 45 Grad sind es zu viele, um sie zu lesen. Versuchen wir eine andere Strategie: Beschrifte nur die Ausreißer und setze die Beschriftungen innerhalb des Diagramms. Du kannst ein Streudiagramm verwenden, um mehr Platz für die Beschriftung zu schaffen:

```python
plt.title('Max Wingspan in Centimeters')
plt.ylabel('Wingspan (CM)')
plt.tick_params(axis='both',which='both',labelbottom=False,bottom=False)

for i in range(len(birds)):
    x = birds['Name'][i]
    y = birds['MaxWingspan'][i]
    plt.plot(x, y, 'bo')
    if birds['MaxWingspan'][i] > 500:
        plt.text(x, y * (1 - 0.05), birds['Name'][i], fontsize=12)
    
plt.show()
```  
Was passiert hier? Du hast `tick_params` verwendet, um die unteren Beschriftungen auszublenden, und dann eine Schleife über deinen Vogel-Datensatz erstellt. Indem du das Diagramm mit kleinen runden blauen Punkten (`bo`) geplottet hast, hast du überprüft, ob ein Vogel eine maximale Flügelspannweite von über 500 hat, und falls ja, seinen Namen als Beschriftung neben dem Punkt angezeigt. Du hast die Beschriftungen auf der y-Achse leicht versetzt (`y * (1 - 0.05)`) und den Vogelnamen als Beschriftung verwendet.

Was hast du herausgefunden?

![outliers](../../../../translated_images/labeled-wingspan-02.6110e2d2401cd5238ccc24dfb6d04a6c19436101f6cec151e3992e719f9f1e1f.de.png)  
## Filtere deine Daten

Sowohl der Weißkopfseeadler als auch der Präriefalke scheinen, obwohl wahrscheinlich sehr große Vögel, falsch beschriftet zu sein, mit einer zusätzlichen `0` in ihrer maximalen Flügelspannweite. Es ist unwahrscheinlich, dass du einem Weißkopfseeadler mit einer Flügelspannweite von 25 Metern begegnest, aber falls doch, lass es uns wissen! Lass uns einen neuen DataFrame ohne diese beiden Ausreißer erstellen:

```python
plt.title('Max Wingspan in Centimeters')
plt.ylabel('Wingspan (CM)')
plt.xlabel('Birds')
plt.tick_params(axis='both',which='both',labelbottom=False,bottom=False)
for i in range(len(birds)):
    x = birds['Name'][i]
    y = birds['MaxWingspan'][i]
    if birds['Name'][i] not in ['Bald eagle', 'Prairie falcon']:
        plt.plot(x, y, 'bo')
plt.show()
```  

Durch das Herausfiltern von Ausreißern sind deine Daten jetzt kohärenter und verständlicher.

![scatterplot of wingspans](../../../../translated_images/scatterplot-wingspan-02.1c33790094ce36a75f5fb45b25ed2cf27f0356ea609e43c11e97a2cedd7011a4.de.png)  

Jetzt, da wir einen bereinigten Datensatz zumindest in Bezug auf die Flügelspannweite haben, lass uns mehr über diese Vögel herausfinden.

Während Linien- und Streudiagramme Informationen über Datenwerte und deren Verteilungen anzeigen können, möchten wir über die Werte in diesem Datensatz nachdenken. Du könntest Visualisierungen erstellen, um folgende Fragen zur Menge zu beantworten:

> Wie viele Kategorien von Vögeln gibt es und wie viele gibt es in jeder Kategorie?  
> Wie viele Vögel sind ausgestorben, gefährdet, selten oder häufig?  
> Wie viele gibt es von den verschiedenen Gattungen und Ordnungen in der Terminologie von Linnaeus?  
## Erkunde Balkendiagramme

Balkendiagramme sind praktisch, wenn du Gruppierungen von Daten anzeigen möchtest. Lass uns die Kategorien von Vögeln in diesem Datensatz erkunden, um zu sehen, welche am häufigsten vorkommt.

Erstelle im Notebook eine grundlegende Balkengrafik.

✅ Hinweis: Du kannst entweder die beiden Ausreißer-Vögel, die wir im vorherigen Abschnitt identifiziert haben, herausfiltern, den Tippfehler in ihrer Flügelspannweite korrigieren oder sie für diese Übungen, die nicht von den Flügelspannweiten abhängen, belassen.

Wenn du ein Balkendiagramm erstellen möchtest, kannst du die Daten auswählen, auf die du dich konzentrieren möchtest. Balkendiagramme können aus Rohdaten erstellt werden:

```python
birds.plot(x='Category',
        kind='bar',
        stacked=True,
        title='Birds of Minnesota')

```  
![full data as a bar chart](../../../../translated_images/full-data-bar-02.aaa3fda71c63ed564b917841a1886c177dd9a26424142e510c0c0498fd6ca160.de.png)  

Dieses Balkendiagramm ist jedoch unleserlich, da es zu viele nicht gruppierte Daten gibt. Du musst nur die Daten auswählen, die du plotten möchtest, also lass uns die Länge der Vögel basierend auf ihrer Kategorie betrachten.

Filtere deine Daten, um nur die Kategorie der Vögel einzuschließen.

✅ Beachte, dass du Pandas verwendest, um die Daten zu verwalten, und dann Matplotlib für die Diagrammerstellung verwendest.

Da es viele Kategorien gibt, kannst du dieses Diagramm vertikal anzeigen und seine Höhe anpassen, um alle Daten darzustellen:

```python
category_count = birds.value_counts(birds['Category'].values, sort=True)
plt.rcParams['figure.figsize'] = [6, 12]
category_count.plot.barh()
```  
![category and length](../../../../translated_images/category-counts-02.0b9a0a4de42275ae5096d0f8da590d8bf520d9e7e40aad5cc4fc8d276480cc32.de.png)  

Dieses Balkendiagramm zeigt eine gute Übersicht über die Anzahl der Vögel in jeder Kategorie. Auf einen Blick siehst du, dass die größte Anzahl von Vögeln in dieser Region zur Kategorie Enten/Gänse/Wasservögel gehört. Minnesota ist das 'Land der 10.000 Seen', also ist das nicht überraschend!

✅ Probiere einige andere Zählungen in diesem Datensatz aus. Überrascht dich etwas?

## Daten vergleichen

Du kannst verschiedene Vergleiche von gruppierten Daten ausprobieren, indem du neue Achsen erstellst. Probiere einen Vergleich der MaxLength eines Vogels basierend auf seiner Kategorie:

```python
maxlength = birds['MaxLength']
plt.barh(y=birds['Category'], width=maxlength)
plt.rcParams['figure.figsize'] = [6, 12]
plt.show()
```  
![comparing data](../../../../translated_images/category-length-02.7304bf519375c9807d8165cc7ec60dd2a60f7b365b23098538e287d89adb7d76.de.png)  

Hier gibt es keine Überraschungen: Kolibris haben die geringste MaxLength im Vergleich zu Pelikanen oder Gänsen. Es ist gut, wenn Daten logisch Sinn ergeben!

Du kannst interessantere Visualisierungen von Balkendiagrammen erstellen, indem du Daten überlagerst. Lass uns die Minimal- und Maximal-Länge einer bestimmten Vogelkategorie überlagern:

```python
minLength = birds['MinLength']
maxLength = birds['MaxLength']
category = birds['Category']

plt.barh(category, maxLength)
plt.barh(category, minLength)

plt.show()
```  
In diesem Diagramm kannst du den Bereich pro Vogelkategorie der Minimal- und Maximal-Länge sehen. Du kannst mit Sicherheit sagen, dass, basierend auf diesen Daten, je größer der Vogel, desto größer sein Längenbereich. Faszinierend!

![superimposed values](../../../../translated_images/superimposed-02.f03058536baeb2ed7864f01102538464d4c2fd7ade881ddd7d5ba74dc5d2fdae.de.png)  

## 🚀 Herausforderung

Dieser Vogel-Datensatz bietet eine Fülle von Informationen über verschiedene Vogelarten innerhalb eines bestimmten Ökosystems. Suche im Internet nach anderen vogelbezogenen Datensätzen. Übe das Erstellen von Diagrammen und Grafiken zu diesen Vögeln, um Fakten zu entdecken, die dir vorher nicht bewusst waren.  
## [Quiz nach der Lektion](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/17)

## Rückblick & Selbststudium

Diese erste Lektion hat dir einige Informationen darüber gegeben, wie man Matplotlib verwendet, um Mengen zu visualisieren. Recherchiere andere Möglichkeiten, mit Datensätzen für Visualisierungen zu arbeiten. [Plotly](https://github.com/plotly/plotly.py) ist eine, die wir in diesen Lektionen nicht behandeln werden, also schau dir an, was sie bieten kann.  
## Aufgabe

[Linien, Streudiagramme und Balken](assignment.md)  

**Haftungsausschluss**:  
Dieses Dokument wurde mit dem KI-Übersetzungsdienst [Co-op Translator](https://github.com/Azure/co-op-translator) übersetzt. Obwohl wir uns um Genauigkeit bemühen, beachten Sie bitte, dass automatisierte Übersetzungen Fehler oder Ungenauigkeiten enthalten können. Das Originaldokument in seiner ursprünglichen Sprache sollte als maßgebliche Quelle betrachtet werden. Für kritische Informationen wird eine professionelle menschliche Übersetzung empfohlen. Wir übernehmen keine Haftung für Missverständnisse oder Fehlinterpretationen, die sich aus der Nutzung dieser Übersetzung ergeben.