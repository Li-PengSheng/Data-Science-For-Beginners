<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "87faccac113d772551486a67a607153e",
  "translation_date": "2025-08-25T18:06:16+00:00",
  "source_file": "3-Data-Visualization/10-visualization-distributions/README.md",
  "language_code": "fr"
}
-->
# Visualiser les distributions

|![ Sketchnote par [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/10-Visualizing-Distributions.png)|
|:---:|
| Visualiser les distributions - _Sketchnote par [@nitya](https://twitter.com/nitya)_ |

Dans la leçon précédente, vous avez appris des faits intéressants sur un ensemble de données concernant les oiseaux du Minnesota. Vous avez identifié des données erronées en visualisant les valeurs aberrantes et examiné les différences entre les catégories d'oiseaux en fonction de leur longueur maximale.

## [Quiz avant la leçon](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/18)
## Explorer l'ensemble de données des oiseaux

Une autre façon d'explorer les données est d'examiner leur distribution, c'est-à-dire comment les données sont organisées le long d'un axe. Par exemple, vous pourriez vouloir en savoir plus sur la distribution générale, pour cet ensemble de données, de l'envergure maximale ou de la masse corporelle maximale des oiseaux du Minnesota.

Découvrons quelques faits sur les distributions des données dans cet ensemble de données. Dans le fichier _notebook.ipynb_ à la racine de ce dossier de leçon, importez Pandas, Matplotlib et vos données :

```python
import pandas as pd
import matplotlib.pyplot as plt
birds = pd.read_csv('../../data/birds.csv')
birds.head()
```

|      | Nom                          | NomScientifique        | Catégorie             | Ordre        | Famille  | Genre       | StatutConservation | MinLongueur | MaxLongueur | MinMasseCorporelle | MaxMasseCorporelle | MinEnvergure | MaxEnvergure |
| ---: | :--------------------------- | :--------------------- | :-------------------- | :----------- | :------- | :---------- | :----------------- | --------:   | --------:   | ----------:        | ----------:        | ----------: | ----------: |
|    0 | Dendrocygne à ventre noir    | Dendrocygna autumnalis | Canards/Oies/Oiseaux aquatiques | Anseriformes | Anatidae | Dendrocygna | LC                 |        47   |        56   |         652        |        1020        |          76 |          94 |
|    1 | Dendrocygne fauve            | Dendrocygna bicolor    | Canards/Oies/Oiseaux aquatiques | Anseriformes | Anatidae | Dendrocygna | LC                 |        45   |        53   |         712        |        1050        |          85 |          93 |
|    2 | Oie des neiges               | Anser caerulescens     | Canards/Oies/Oiseaux aquatiques | Anseriformes | Anatidae | Anser       | LC                 |        64   |        79   |        2050        |        4050        |         135 |         165 |
|    3 | Oie de Ross                  | Anser rossii           | Canards/Oies/Oiseaux aquatiques | Anseriformes | Anatidae | Anser       | LC                 |      57.3   |        64   |        1066        |        1567        |         113 |         116 |
|    4 | Oie rieuse                   | Anser albifrons        | Canards/Oies/Oiseaux aquatiques | Anseriformes | Anatidae | Anser       | LC                 |        64   |        81   |        1930        |        3310        |         130 |         165 |

En général, vous pouvez rapidement examiner la façon dont les données sont distribuées en utilisant un diagramme de dispersion, comme nous l'avons fait dans la leçon précédente :

```python
birds.plot(kind='scatter',x='MaxLength',y='Order',figsize=(12,8))

plt.title('Max Length per Order')
plt.ylabel('Order')
plt.xlabel('Max Length')

plt.show()
```
![longueur maximale par ordre](../../../../translated_images/scatter-wb.9d98b0ed7f0388af979441853361a11df5f518f5307938a503ca7913e986111b.fr.png)

Cela donne un aperçu de la distribution générale de la longueur corporelle par ordre d'oiseaux, mais ce n'est pas la méthode optimale pour afficher les véritables distributions. Cette tâche est généralement réalisée en créant un histogramme.

## Travailler avec des histogrammes

Matplotlib offre d'excellents moyens de visualiser la distribution des données à l'aide d'histogrammes. Ce type de graphique ressemble à un diagramme en barres où la distribution peut être observée à travers la montée et la descente des barres. Pour construire un histogramme, vous avez besoin de données numériques. Pour créer un histogramme, vous pouvez tracer un graphique en définissant le type comme 'hist' pour Histogramme. Ce graphique montre la distribution de la MaxMasseCorporelle pour l'ensemble de données entier. En divisant le tableau de données en petits intervalles, il peut afficher la distribution des valeurs des données :

```python
birds['MaxBodyMass'].plot(kind = 'hist', bins = 10, figsize = (12,12))
plt.show()
```
![distribution sur l'ensemble du dataset](../../../../translated_images/dist1-wb.0d0cac82e2974fbbec635826fefead401af795f82e2279e2e2678bf2c117d827.fr.png)

Comme vous pouvez le voir, la plupart des 400+ oiseaux de cet ensemble de données ont une masse corporelle maximale inférieure à 2000. Obtenez plus d'informations sur les données en modifiant le paramètre `bins` pour un nombre plus élevé, comme 30 :

```python
birds['MaxBodyMass'].plot(kind = 'hist', bins = 30, figsize = (12,12))
plt.show()
```
![distribution avec un paramètre bins plus élevé](../../../../translated_images/dist2-wb.2c0a7a3499b2fbf561e9f93b69f265dfc538dc78f6de15088ba84a88152e26ba.fr.png)

Ce graphique montre la distribution de manière un peu plus détaillée. Un graphique moins biaisé vers la gauche pourrait être créé en s'assurant que vous ne sélectionnez que des données dans une plage donnée :

Filtrez vos données pour obtenir uniquement les oiseaux dont la masse corporelle est inférieure à 60, et affichez 40 `bins` :

```python
filteredBirds = birds[(birds['MaxBodyMass'] > 1) & (birds['MaxBodyMass'] < 60)]      
filteredBirds['MaxBodyMass'].plot(kind = 'hist',bins = 40,figsize = (12,12))
plt.show()     
```
![histogramme filtré](../../../../translated_images/dist3-wb.64b88db7f9780200bd486a2c2a3252548dd439672dbd3f778193db7f654b100c.fr.png)

✅ Essayez d'autres filtres et points de données. Pour voir la distribution complète des données, supprimez le filtre `['MaxBodyMass']` pour afficher les distributions étiquetées.

L'histogramme offre également des améliorations intéressantes en termes de couleur et d'étiquetage :

Créez un histogramme 2D pour comparer la relation entre deux distributions. Comparons `MaxBodyMass` et `MaxLength`. Matplotlib propose une méthode intégrée pour montrer la convergence en utilisant des couleurs plus vives :

```python
x = filteredBirds['MaxBodyMass']
y = filteredBirds['MaxLength']

fig, ax = plt.subplots(tight_layout=True)
hist = ax.hist2d(x, y)
```
Il semble y avoir une corrélation attendue entre ces deux éléments le long d'un axe attendu, avec un point de convergence particulièrement fort :

![graphique 2D](../../../../translated_images/2D-wb.ae22fdd33936507a41e3af22e11e4903b04a9be973b23a4e05214efaccfd66c8.fr.png)

Les histogrammes fonctionnent bien par défaut pour les données numériques. Que faire si vous devez examiner les distributions selon des données textuelles ? 
## Explorer l'ensemble de données pour les distributions basées sur des données textuelles 

Cet ensemble de données contient également de bonnes informations sur la catégorie des oiseaux, leur genre, espèce, famille ainsi que leur statut de conservation. Explorons ces informations de conservation. Quelle est la distribution des oiseaux selon leur statut de conservation ?

> ✅ Dans l'ensemble de données, plusieurs acronymes sont utilisés pour décrire le statut de conservation. Ces acronymes proviennent des [Catégories de la Liste Rouge de l'UICN](https://www.iucnredlist.org/), une organisation qui catalogue le statut des espèces.
> 
> - CR : En danger critique
> - EN : En danger
> - EX : Éteint
> - LC : Préoccupation mineure
> - NT : Quasi menacé
> - VU : Vulnérable

Ces valeurs sont basées sur du texte, vous devrez donc effectuer une transformation pour créer un histogramme. En utilisant le dataframe filteredBirds, affichez son statut de conservation avec son envergure minimale. Que voyez-vous ?

```python
x1 = filteredBirds.loc[filteredBirds.ConservationStatus=='EX', 'MinWingspan']
x2 = filteredBirds.loc[filteredBirds.ConservationStatus=='CR', 'MinWingspan']
x3 = filteredBirds.loc[filteredBirds.ConservationStatus=='EN', 'MinWingspan']
x4 = filteredBirds.loc[filteredBirds.ConservationStatus=='NT', 'MinWingspan']
x5 = filteredBirds.loc[filteredBirds.ConservationStatus=='VU', 'MinWingspan']
x6 = filteredBirds.loc[filteredBirds.ConservationStatus=='LC', 'MinWingspan']

kwargs = dict(alpha=0.5, bins=20)

plt.hist(x1, **kwargs, color='red', label='Extinct')
plt.hist(x2, **kwargs, color='orange', label='Critically Endangered')
plt.hist(x3, **kwargs, color='yellow', label='Endangered')
plt.hist(x4, **kwargs, color='green', label='Near Threatened')
plt.hist(x5, **kwargs, color='blue', label='Vulnerable')
plt.hist(x6, **kwargs, color='gray', label='Least Concern')

plt.gca().set(title='Conservation Status', ylabel='Min Wingspan')
plt.legend();
```

![collation envergure et conservation](../../../../translated_images/histogram-conservation-wb.3c40450eb072c14de7a1a3ec5c0fcba4995531024760741b392911b567fd8b70.fr.png)

Il ne semble pas y avoir de bonne corrélation entre l'envergure minimale et le statut de conservation. Testez d'autres éléments de l'ensemble de données en utilisant cette méthode. Vous pouvez également essayer différents filtres. Trouvez-vous une corrélation ?

## Graphiques de densité

Vous avez peut-être remarqué que les histogrammes que nous avons examinés jusqu'à présent sont "en escalier" et ne s'écoulent pas de manière fluide en arc. Pour afficher un graphique de densité plus fluide, vous pouvez essayer un graphique de densité.

Pour travailler avec des graphiques de densité, familiarisez-vous avec une nouvelle bibliothèque de tracé, [Seaborn](https://seaborn.pydata.org/generated/seaborn.kdeplot.html). 

En chargeant Seaborn, essayez un graphique de densité de base :

```python
import seaborn as sns
import matplotlib.pyplot as plt
sns.kdeplot(filteredBirds['MinWingspan'])
plt.show()
```
![Graphique de densité](../../../../translated_images/density1.8801043bd4af2567b0f706332b5853c7614e5e4b81b457acc27eb4e092a65cbd.fr.png)

Vous pouvez voir comment le graphique reflète le précédent pour les données d'envergure minimale ; il est juste un peu plus fluide. Selon la documentation de Seaborn, "Par rapport à un histogramme, le KDE peut produire un graphique moins encombré et plus interprétable, surtout lorsqu'on trace plusieurs distributions. Mais il a le potentiel d'introduire des distorsions si la distribution sous-jacente est limitée ou non fluide. Comme un histogramme, la qualité de la représentation dépend également de la sélection de bons paramètres de lissage." [source](https://seaborn.pydata.org/generated/seaborn.kdeplot.html) En d'autres termes, les valeurs aberrantes, comme toujours, feront mal fonctionner vos graphiques.

Si vous vouliez revisiter cette ligne irrégulière de MaxBodyMass dans le deuxième graphique que vous avez construit, vous pourriez la lisser très bien en la recréant avec cette méthode :

```python
sns.kdeplot(filteredBirds['MaxBodyMass'])
plt.show()
```
![ligne de masse corporelle lissée](../../../../translated_images/density2.8e7647257060ff544a1aaded57e8dd1887586bfe340139e9b77ac1e5287f7977.fr.png)

Si vous vouliez une ligne lisse, mais pas trop lisse, modifiez le paramètre `bw_adjust` : 

```python
sns.kdeplot(filteredBirds['MaxBodyMass'], bw_adjust=.2)
plt.show()
```
![ligne de masse corporelle moins lissée](../../../../translated_images/density3.84ae27da82f31e6b83ad977646f029a1d21186574d7581facd70123b3eb257ee.fr.png)

✅ Lisez les paramètres disponibles pour ce type de graphique et expérimentez !

Ce type de graphique offre des visualisations magnifiquement explicatives. Avec quelques lignes de code, par exemple, vous pouvez montrer la densité de masse corporelle maximale par ordre d'oiseaux :

```python
sns.kdeplot(
   data=filteredBirds, x="MaxBodyMass", hue="Order",
   fill=True, common_norm=False, palette="crest",
   alpha=.5, linewidth=0,
)
```

![masse corporelle par ordre](../../../../translated_images/density4.e9d6c033f15c500fd33df94cb592b9f5cf1ed2a3d213c448a3f9e97ba39573ce.fr.png)

Vous pouvez également cartographier la densité de plusieurs variables dans un seul graphique. Testez la longueur maximale et la longueur minimale d'un oiseau par rapport à son statut de conservation :

```python
sns.kdeplot(data=filteredBirds, x="MinLength", y="MaxLength", hue="ConservationStatus")
```

![densités multiples superposées](../../../../translated_images/multi.56548caa9eae8d0fd9012a8586295538c7f4f426e2abc714ba070e2e4b1fc2c1.fr.png)

Peut-être vaut-il la peine de rechercher si le regroupement des oiseaux "Vulnérables" selon leurs longueurs est significatif ou non.

## 🚀 Défi

Les histogrammes sont un type de graphique plus sophistiqué que les diagrammes de dispersion, les diagrammes en barres ou les graphiques linéaires de base. Faites une recherche sur Internet pour trouver de bons exemples d'utilisation des histogrammes. Comment sont-ils utilisés, que démontrent-ils, et dans quels domaines ou champs d'étude ont-ils tendance à être utilisés ?

## [Quiz après la leçon](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/19)

## Révision et auto-apprentissage

Dans cette leçon, vous avez utilisé Matplotlib et commencé à travailler avec Seaborn pour afficher des graphiques plus sophistiqués. Faites des recherches sur `kdeplot` dans Seaborn, une "courbe de densité de probabilité continue dans une ou plusieurs dimensions". Lisez la [documentation](https://seaborn.pydata.org/generated/seaborn.kdeplot.html) pour comprendre son fonctionnement.

## Devoir

[Appliquez vos compétences](assignment.md)

**Avertissement** :  
Ce document a été traduit à l'aide du service de traduction automatique [Co-op Translator](https://github.com/Azure/co-op-translator). Bien que nous nous efforcions d'assurer l'exactitude, veuillez noter que les traductions automatisées peuvent contenir des erreurs ou des inexactitudes. Le document original dans sa langue d'origine doit être considéré comme la source faisant autorité. Pour des informations critiques, il est recommandé de recourir à une traduction professionnelle réalisée par un humain. Nous déclinons toute responsabilité en cas de malentendus ou d'interprétations erronées résultant de l'utilisation de cette traduction.