<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "cad419b574d5c35eaa417e9abfdcb0c8",
  "translation_date": "2025-08-25T18:09:37+00:00",
  "source_file": "3-Data-Visualization/12-visualization-relationships/README.md",
  "language_code": "hk"
}
-->
# 視覺化關係：關於蜂蜜 🍯

|![ Sketchnote by [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/12-Visualizing-Relationships.png)|
|:---:|
|視覺化關係 - _Sketchnote by [@nitya](https://twitter.com/nitya)_ |

延續我們研究的自然主題，讓我們探索一些有趣的視覺化方式，展示不同種類蜂蜜之間的關係，根據一個來自[美國農業部](https://www.nass.usda.gov/About_NASS/index.php)的數據集。

這個包含約600項的數據集展示了美國多個州的蜂蜜生產情況。例如，您可以查看每個州在1998年至2012年間的蜂群數量、每群產量、總產量、庫存、每磅價格以及蜂蜜的生產價值，每年每州一行數據。

視覺化某州每年的生產量與該州蜂蜜價格之間的關係會很有趣。或者，您可以視覺化各州每群蜂蜜的產量之間的關係。這段時間涵蓋了2006年首次出現的毀滅性“蜂群崩潰症”（CCD，Colony Collapse Disorder）（http://npic.orst.edu/envir/ccd.html），因此這是一個值得研究的數據集。🐝

## [課前測驗](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/22)

在這節課中，您可以使用之前使用過的 Seaborn 作為一個很好的庫來視覺化變量之間的關係。特別有趣的是使用 Seaborn 的 `relplot` 函數，它允許快速生成散點圖和折線圖來視覺化“[統計關係](https://seaborn.pydata.org/tutorial/relational.html?highlight=relationships)”，幫助數據科學家更好地理解變量之間的關聯。

## 散點圖

使用散點圖展示蜂蜜價格每年每州的演變情況。Seaborn 使用 `relplot` 方便地將州數據分組，並顯示分類和數值數據的數據點。

首先，導入數據和 Seaborn：

```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
honey = pd.read_csv('../../data/honey.csv')
honey.head()
```
您會注意到蜂蜜數據有幾個有趣的列，包括年份和每磅價格。讓我們探索按美國州分組的數據：

| 州   | 蜂群數量 | 每群產量 | 總產量   | 庫存     | 每磅價格   | 生產價值   | 年份 |
| ----- | ------ | ----------- | --------- | -------- | ---------- | --------- | ---- |
| AL    | 16000  | 71          | 1136000   | 159000   | 0.72       | 818000    | 1998 |
| AZ    | 55000  | 60          | 3300000   | 1485000  | 0.64       | 2112000   | 1998 |
| AR    | 53000  | 65          | 3445000   | 1688000  | 0.59       | 2033000   | 1998 |
| CA    | 450000 | 83          | 37350000  | 12326000 | 0.62       | 23157000  | 1998 |
| CO    | 27000  | 72          | 1944000   | 1594000  | 0.7        | 1361000   | 1998 |

創建一個基本的散點圖，展示蜂蜜每磅價格與其美國州的來源之間的關係。讓 `y` 軸足夠高以顯示所有州：

```python
sns.relplot(x="priceperlb", y="state", data=honey, height=15, aspect=.5);
```
![scatterplot 1](../../../../translated_images/scatter1.5e1aa5fd6706c5d12b5e503ccb77f8a930f8620f539f524ddf56a16c039a5d2f.hk.png)

現在，使用蜂蜜色調展示數據，顯示價格如何隨年份演變。您可以通過添加 'hue' 參數來展示每年的變化：

> ✅ 了解更多關於 [Seaborn 中可用的色彩調色板](https://seaborn.pydata.org/tutorial/color_palettes.html) - 試試美麗的彩虹色調！

```python
sns.relplot(x="priceperlb", y="state", hue="year", palette="YlOrBr", data=honey, height=15, aspect=.5);
```
![scatterplot 2](../../../../translated_images/scatter2.c0041a58621ca702990b001aa0b20cd68c1e1814417139af8a7211a2bed51c5f.hk.png)

通過這種色彩方案的改變，您可以清楚地看到蜂蜜每磅價格在多年來的明顯增長趨勢。事實上，如果您查看數據中的樣本集（例如選擇一個州，亞利桑那州），您可以看到價格逐年上漲的模式，只有少數例外：

| 州   | 蜂群數量 | 每群產量 | 總產量   | 庫存     | 每磅價格   | 生產價值   | 年份 |
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

另一種視覺化這種演變的方法是使用大小而不是顏色。對於色盲用戶，這可能是一個更好的選擇。編輯您的視覺化，通過點的圓周大小來展示價格的增長：

```python
sns.relplot(x="priceperlb", y="state", size="year", data=honey, height=15, aspect=.5);
```
您可以看到點的大小逐漸增大。

![scatterplot 3](../../../../translated_images/scatter3.3c160a3d1dcb36b37900ebb4cf97f34036f28ae2b7b8e6062766c7c1dfc00853.hk.png)

這是否是一個簡單的供需問題？由於氣候變化和蜂群崩潰等因素，是否每年可供購買的蜂蜜減少，因此價格上漲？

為了探索這個數據集中某些變量之間的相關性，讓我們研究一些折線圖。

## 折線圖

問題：蜂蜜每磅價格是否每年都有明顯上漲？您可以通過創建一個單一折線圖來最容易地發現這一點：

```python
sns.relplot(x="year", y="priceperlb", kind="line", data=honey);
```
答案：是的，但在2003年左右有一些例外：

![line chart 1](../../../../translated_images/line1.f36eb465229a3b1fe385cdc93861aab3939de987d504b05de0b6cd567ef79f43.hk.png)

✅ 由於 Seaborn 將數據聚合到一條線上，它通過繪製均值和均值周圍的95%置信區間來顯示“每個 x 值的多個測量值”。[來源](https://seaborn.pydata.org/tutorial/relational.html)。這種耗時的行為可以通過添加 `ci=None` 禁用。

問題：那麼，在2003年，我們是否也能看到蜂蜜供應的激增？如果您查看每年的總產量呢？

```python
sns.relplot(x="year", y="totalprod", kind="line", data=honey);
```

![line chart 2](../../../../translated_images/line2.a5b3493dc01058af6402e657aaa9ae1125fafb5e7d6630c777aa60f900a544e4.hk.png)

答案：並不完全。如果您查看總產量，實際上在那一年似乎有所增加，儘管總體來看蜂蜜的生產量在這些年中呈下降趨勢。

問題：在這種情況下，2003年蜂蜜價格的激增可能是什麼原因？

為了探索這一點，您可以研究一個 Facet Grid。

## Facet Grids

Facet Grids 將數據集的一個方面（在我們的例子中，您可以選擇“年份”以避免生成過多的 Facets）。Seaborn 可以為您選擇的 x 和 y 坐標的每個 Facet 繪製一個圖表，以便更容易進行視覺比較。在這種比較中，2003年是否突出？

通過繼續使用 `relplot` 創建 Facet Grid，正如 [Seaborn 的文檔](https://seaborn.pydata.org/generated/seaborn.FacetGrid.html?highlight=facetgrid#seaborn.FacetGrid)所推薦的。

```python
sns.relplot(
    data=honey, 
    x="yieldpercol", y="numcol",
    col="year", 
    col_wrap=3,
    kind="line"
```
在這個視覺化中，您可以比較每年的每群產量和蜂群數量，並將列的包裹設置為3：

![facet grid](../../../../translated_images/facet.6a34851dcd540050dcc0ead741be35075d776741668dd0e42f482c89b114c217.hk.png)

對於這個數據集，關於蜂群數量及其產量，按年份和州來看並沒有特別突出的地方。是否有其他方式來尋找這兩個變量之間的相關性？

## 雙折線圖

嘗試通過將兩個折線圖疊加在一起來創建多折線圖，使用 Seaborn 的 'despine' 移除其頂部和右側的脊，並使用 `ax.twinx` [源自 Matplotlib](https://matplotlib.org/stable/api/_as_gen/matplotlib.axes.Axes.twinx.html)。Twins 允許圖表共享 x 軸並顯示兩個 y 軸。因此，顯示每群產量和蜂群數量，疊加：

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
![superimposed plots](../../../../translated_images/dual-line.a4c28ce659603fab2c003f4df816733df2bf41d1facb7de27989ec9afbf01b33.hk.png)

雖然在2003年沒有明顯的異常，但它確實讓我們以一個稍微更樂觀的結論結束這節課：儘管蜂群數量總體上在下降，但蜂群數量正在穩定，即使每群的產量在減少。

加油，蜜蜂們！

🐝❤️
## 🚀 挑戰

在這節課中，您學到了更多關於散點圖和折線網格的其他用途，包括 Facet Grids。挑戰自己使用不同的數據集創建一個 Facet Grid，也許是您之前使用過的數據集。注意它們的創建時間以及您需要如何小心地控制生成的網格數量。

## [課後測驗](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/23)

## 回顧與自學

折線圖可以很簡單也可以很複雜。閱讀 [Seaborn 文檔](https://seaborn.pydata.org/generated/seaborn.lineplot.html) 中的各種構建方法。嘗試使用文檔中列出的其他方法來增強您在這節課中構建的折線圖。

## 作業

[深入蜂巢](assignment.md)

**免責聲明**：  
本文件已使用人工智能翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。儘管我們致力於提供準確的翻譯，請注意自動翻譯可能包含錯誤或不準確之處。原始語言的文件應被視為權威來源。對於重要信息，建議使用專業人工翻譯。我們對因使用此翻譯而引起的任何誤解或錯誤解釋概不負責。