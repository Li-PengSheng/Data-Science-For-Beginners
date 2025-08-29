<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "116c5d361fbe812e59a73f37ce721d36",
  "translation_date": "2025-08-25T16:25:18+00:00",
  "source_file": "2-Working-With-Data/07-python/README.md",
  "language_code": "tw"
}
-->
# 使用數據：Python 與 Pandas 函式庫

| ![ 由 [(@sketchthedocs)](https://sketchthedocs.dev) 繪製的手繪筆記 ](../../sketchnotes/07-WorkWithPython.png) |
| :-------------------------------------------------------------------------------------------------------: |
|                 使用 Python - _由 [@nitya](https://twitter.com/nitya) 繪製的手繪筆記_                      |

[![介紹影片](../../../../translated_images/video-ds-python.245247dc811db8e4d5ac420246de8a118c63fd28f6a56578d08b630ae549f260.tw.png)](https://youtu.be/dZjWOGbsN4Y)

雖然資料庫提供了非常高效的方式來存儲數據並使用查詢語言進行查詢，但最靈活的數據處理方式是編寫自己的程式來操作數據。在許多情況下，使用資料庫查詢會更有效。然而，在某些需要更複雜數據處理的情況下，SQL 無法輕鬆完成這些操作。

數據處理可以用任何程式語言來編寫，但有些語言在處理數據方面更高效。數據科學家通常偏好以下幾種語言：

* **[Python](https://www.python.org/)**：一種通用程式語言，因其簡單性常被認為是初學者的最佳選擇之一。Python 擁有許多額外的函式庫，可以幫助解決許多實際問題，例如從 ZIP 壓縮檔中提取數據，或將圖片轉換為灰階。除了數據科學，Python 也常用於網頁開發。
* **[R](https://www.r-project.org/)**：一個專為統計數據處理而開發的傳統工具箱。它擁有大量的函式庫資源（CRAN），使其成為數據處理的良好選擇。然而，R 並非通用程式語言，且很少用於數據科學領域以外的場景。
* **[Julia](https://julialang.org/)**：另一種專為數據科學開發的語言。它旨在提供比 Python 更好的性能，是科學實驗的強大工具。

在本課程中，我們將專注於使用 Python 進行簡單的數據處理。我們假設您對該語言已有基本的了解。如果您想更深入地學習 Python，可以參考以下資源：

* [用烏龜圖形和分形圖有趣地學習 Python](https://github.com/shwars/pycourse) - 基於 GitHub 的 Python 程式設計快速入門課程
* [從零開始學習 Python](https://docs.microsoft.com/en-us/learn/paths/python-first-steps/?WT.mc_id=academic-77958-bethanycheum) - [Microsoft Learn](http://learn.microsoft.com/?WT.mc_id=academic-77958-bethanycheum) 上的學習路徑

數據可以有多種形式。在本課程中，我們將探討三種數據形式：**表格數據**、**文本**和**圖片**。

我們將專注於數據處理的一些示例，而不是全面介紹所有相關函式庫。這樣可以讓您掌握主要概念，並在需要時知道去哪裡尋找解決方案。

> **最有用的建議**：當您需要對數據執行某些操作但不知道如何進行時，嘗試在網路上搜尋解決方案。[Stackoverflow](https://stackoverflow.com/) 通常包含許多針對常見任務的 Python 範例程式碼。

## [課前測驗](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/12)

## 表格數據與 DataFrame

當我們討論關聯式資料庫時，您已經接觸過表格數據。當您擁有大量數據，且這些數據存儲於多個相互關聯的表中時，使用 SQL 來處理它們是非常合理的。然而，在許多情況下，我們擁有一個數據表，並需要對該數據進行一些**理解**或**洞察**，例如分佈情況、數值之間的相關性等。在數據科學中，經常需要對原始數據進行一些轉換，然後進行可視化。這兩個步驟都可以輕鬆地使用 Python 完成。

Python 中有兩個非常有用的函式庫可以幫助您處理表格數據：
* **[Pandas](https://pandas.pydata.org/)**：允許您操作所謂的 **DataFrame**，類似於關聯式表格。您可以擁有命名的列，並對行、列和整個 DataFrame 執行不同的操作。
* **[Numpy](https://numpy.org/)**：用於處理 **張量**（即多維**陣列**）的函式庫。陣列的值具有相同的基礎類型，比 DataFrame 更簡單，但提供了更多數學運算，並且開銷更小。

此外，還有幾個您應該了解的函式庫：
* **[Matplotlib](https://matplotlib.org/)**：用於數據可視化和繪製圖表的函式庫
* **[SciPy](https://www.scipy.org/)**：包含一些額外科學函數的函式庫。我們在討論概率和統計時已經接觸過該函式庫

以下是您通常在 Python 程式開頭用來匯入這些函式庫的程式碼：
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from scipy import ... # you need to specify exact sub-packages that you need
```

Pandas 圍繞幾個基本概念進行設計。

### Series

**Series** 是一個值的序列，類似於列表或 numpy 陣列。主要區別在於 Series 還有一個 **索引**，當我們對 Series 進行操作（例如相加）時，索引會被考慮在內。索引可以是簡單的整數行號（從列表或陣列創建 Series 時的默認索引），也可以具有複雜結構，例如日期區間。

> **注意**：在附帶的筆記本 [`notebook.ipynb`](../../../../2-Working-With-Data/07-python/notebook.ipynb) 中有一些 Pandas 的入門程式碼。我們在這裡僅概述一些示例，您可以查看完整的筆記本。

舉個例子：我們想分析我們冰淇淋店的銷售情況。讓我們生成一段時間內的銷售數據（每天售出的數量）：
```python
start_date = "Jan 1, 2020"
end_date = "Mar 31, 2020"
idx = pd.date_range(start_date,end_date)
print(f"Length of index is {len(idx)}")
items_sold = pd.Series(np.random.randint(25,50,size=len(idx)),index=idx)
items_sold.plot()
```
![時間序列圖](../../../../translated_images/timeseries-1.80de678ab1cf727e50e00bcf24009fa2b0a8b90ebc43e34b99a345227d28e467.tw.png)

假設每週我們都會為朋友舉辦派對，並額外準備 10 盒冰淇淋。我們可以創建另一個以週為索引的 Series 來展示這一點：
```python
additional_items = pd.Series(10,index=pd.date_range(start_date,end_date,freq="W"))
```
當我們將兩個 Series 相加時，我們會得到總數：
```python
total_items = items_sold.add(additional_items,fill_value=0)
total_items.plot()
```
![時間序列圖](../../../../translated_images/timeseries-2.aae51d575c55181ceda81ade8c546a2fc2024f9136934386d57b8a189d7570ff.tw.png)

> **注意**：我們沒有使用簡單的語法 `total_items+additional_items`。如果這樣做，結果 Series 中會有許多 `NaN`（*非數值*）值。這是因為在 `additional_items` Series 的某些索引點上存在缺失值，而將 `NaN` 與任何值相加都會得到 `NaN`。因此，我們需要在相加時指定 `fill_value` 參數。

對於時間序列，我們還可以使用不同的時間間隔對其進行**重採樣**。例如，假設我們想計算每月的平均銷售量。我們可以使用以下程式碼：
```python
monthly = total_items.resample("1M").mean()
ax = monthly.plot(kind='bar')
```
![每月時間序列平均值](../../../../translated_images/timeseries-3.f3147cbc8c624881008564bc0b5d9fcc15e7374d339da91766bd0e1c6bd9e3af.tw.png)

### DataFrame

DataFrame 本質上是具有相同索引的多個 Series 的集合。我們可以將幾個 Series 組合成一個 DataFrame：
```python
a = pd.Series(range(1,10))
b = pd.Series(["I","like","to","play","games","and","will","not","change"],index=range(0,9))
df = pd.DataFrame([a,b])
```
這將創建如下的橫向表格：
|     | 0   | 1    | 2   | 3   | 4      | 5   | 6      | 7    | 8    |
| --- | --- | ---- | --- | --- | ------ | --- | ------ | ---- | ---- |
| 0   | 1   | 2    | 3   | 4   | 5      | 6   | 7      | 8    | 9    |
| 1   | I   | like | to  | use | Python | and | Pandas | very | much |

我們還可以將 Series 作為列，並使用字典指定列名：
```python
df = pd.DataFrame({ 'A' : a, 'B' : b })
```
這將生成如下表格：

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

**注意**：我們也可以通過轉置前一個表格來獲得這種表格佈局，例如：
```python
df = pd.DataFrame([a,b]).T..rename(columns={ 0 : 'A', 1 : 'B' })
```
這裡 `.T` 表示轉置 DataFrame 的操作，即更改行和列，而 `rename` 操作允許我們將列名重命名以匹配前一個示例。

以下是我們可以對 DataFrame 執行的一些最重要操作：

**選擇列**。我們可以通過 `df['A']` 選擇單個列，該操作返回一個 Series。我們還可以通過 `df[['B','A']]` 選擇列的子集，這將返回另一個 DataFrame。

**篩選**符合條件的行。例如，要僅保留列 `A` 大於 5 的行，我們可以寫 `df[df['A']>5]`。

> **注意**：篩選的工作方式如下。表達式 `df['A']<5` 返回一個布林 Series，指示原始 Series `df['A']` 中每個元素的表達式是否為 `True` 或 `False`。當布林 Series 用作索引時，它返回 DataFrame 中的行子集。因此，無法使用任意的 Python 布林表達式，例如，寫 `df[df['A']>5 and df['A']<7]` 是錯誤的。相反，您應該對布林 Series 使用特殊的 `&` 運算符，寫作 `df[(df['A']>5) & (df['A']<7)]`（*括號在這裡很重要*）。

**創建新的可計算列**。我們可以通過直觀的表達式輕鬆為 DataFrame 創建新的可計算列：
```python
df['DivA'] = df['A']-df['A'].mean() 
```
此示例計算 A 與其平均值的偏差。實際上，我們是在計算一個 Series，然後將該 Series 賦值給左側，創建另一列。因此，我們不能使用與 Series 不兼容的任何操作，例如，以下程式碼是錯誤的：
```python
# Wrong code -> df['ADescr'] = "Low" if df['A'] < 5 else "Hi"
df['LenB'] = len(df['B']) # <- Wrong result
```
後一個示例雖然語法正確，但結果錯誤，因為它將 Series `B` 的長度賦值給列中的所有值，而不是我們預期的每個元素的長度。

如果我們需要計算這樣的複雜表達式，可以使用 `apply` 函數。最後一個示例可以寫成如下：
```python
df['LenB'] = df['B'].apply(lambda x : len(x))
# or 
df['LenB'] = df['B'].apply(len)
```

經過上述操作後，我們將得到以下 DataFrame：

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

**基於數字選擇行**可以使用 `iloc` 結構。例如，要選擇 DataFrame 的前 5 行：
```python
df.iloc[:5]
```

**分組**通常用於獲得類似於 Excel 中*樞軸表*的結果。例如，假設我們想計算每個 `LenB` 值對應的列 `A` 的平均值。我們可以按 `LenB` 將 DataFrame 分組，然後調用 `mean`：
```python
df.groupby(by='LenB').mean()
```
如果我們需要計算平均值和組中元素的數量，可以使用更複雜的 `aggregate` 函數：
```python
df.groupby(by='LenB') \
 .aggregate({ 'DivA' : len, 'A' : lambda x: x.mean() }) \
 .rename(columns={ 'DivA' : 'Count', 'A' : 'Mean'})
```
這將生成以下表格：

| LenB | Count | Mean     |
| ---- | ----- | -------- |
| 1    | 1     | 1.000000 |
| 2    | 1     | 3.000000 |
| 3    | 2     | 5.000000 |
| 4    | 3     | 6.333333 |
| 6    | 2     | 6.000000 |

### 獲取數據
我們已經看到如何輕鬆地從 Python 物件構建 Series 和 DataFrame。然而，數據通常以文字檔案或 Excel 表格的形式出現。幸運的是，Pandas 提供了一種簡單的方法來從磁碟載入數據。例如，讀取 CSV 檔案就像這樣簡單：
```python
df = pd.read_csv('file.csv')
```
我們將在“挑戰”部分看到更多載入數據的範例，包括從外部網站獲取數據。

### 列印與繪圖

數據科學家經常需要探索數據，因此能夠視覺化數據非常重要。當 DataFrame 很大時，我們通常只想確認我們的操作是否正確，這可以通過列印出前幾行來完成。這可以通過呼叫 `df.head()` 完成。如果你在 Jupyter Notebook 中執行，它會以漂亮的表格形式顯示 DataFrame。

我們還看到了使用 `plot` 函數來視覺化某些列的用法。雖然 `plot` 對於許多任務非常有用，並且通過 `kind=` 參數支持多種不同的圖表類型，但你也可以使用原始的 `matplotlib` 庫來繪製更複雜的圖表。我們將在單獨的課程中詳細介紹數據視覺化。

這個概述涵蓋了 Pandas 的最重要概念，但這個庫非常豐富，幾乎沒有你無法完成的事情！現在，讓我們應用這些知識來解決具體問題。

## 🚀 挑戰 1：分析 COVID 傳播

我們將專注於的第一個問題是 COVID-19 的流行病傳播建模。為了做到這一點，我們將使用由 [約翰霍普金斯大學](https://jhu.edu/) 的 [系統科學與工程中心](https://systems.jhu.edu/) (CSSE) 提供的不同國家感染人數數據。數據集可在 [這個 GitHub 資源庫](https://github.com/CSSEGISandData/COVID-19) 中找到。

由於我們想展示如何處理數據，我們邀請你打開 [`notebook-covidspread.ipynb`](../../../../2-Working-With-Data/07-python/notebook-covidspread.ipynb) 並從頭到尾閱讀。你也可以執行單元格，並完成我們在最後為你留下的一些挑戰。

![COVID 傳播](../../../../translated_images/covidspread.f3d131c4f1d260ab0344d79bac0abe7924598dd754859b165955772e1bd5e8a2.tw.png)

> 如果你不知道如何在 Jupyter Notebook 中執行程式碼，可以參考 [這篇文章](https://soshnikov.com/education/how-to-execute-notebooks-from-github/)。

## 處理非結構化數據

雖然數據通常以表格形式出現，但在某些情況下，我們需要處理結構化程度較低的數據，例如文字或圖片。在這種情況下，要應用我們上面看到的數據處理技術，我們需要以某種方式**提取**結構化數據。以下是一些範例：

* 從文字中提取關鍵字，並查看這些關鍵字出現的頻率
* 使用神經網絡從圖片中提取物件資訊
* 從視頻鏡頭中獲取人們的情緒資訊

## 🚀 挑戰 2：分析 COVID 論文

在這個挑戰中，我們將繼續探討 COVID 大流行的主題，並專注於處理有關該主題的科學論文。有一個 [CORD-19 數據集](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge)，其中包含超過 7000 篇（撰寫時）關於 COVID 的論文，並附有元數據和摘要（其中約一半還提供全文）。

使用 [Text Analytics for Health](https://docs.microsoft.com/azure/cognitive-services/text-analytics/how-tos/text-analytics-for-health/?WT.mc_id=academic-77958-bethanycheum) 認知服務分析此數據集的完整範例已在 [這篇部落格文章](https://soshnikov.com/science/analyzing-medical-papers-with-azure-and-text-analytics-for-health/) 中描述。我們將討論此分析的簡化版本。

> **NOTE**: 我們未在此資源庫中提供數據集的副本。你可能需要先從 [Kaggle 上的這個數據集](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge?select=metadata.csv) 下載 [`metadata.csv`](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge?select=metadata.csv) 文件。可能需要在 Kaggle 註冊。你也可以從 [這裡](https://ai2-semanticscholar-cord-19.s3-us-west-2.amazonaws.com/historical_releases.html) 無需註冊下載數據集，但它將包括所有全文以及元數據文件。

打開 [`notebook-papers.ipynb`](../../../../2-Working-With-Data/07-python/notebook-papers.ipynb) 並從頭到尾閱讀。你也可以執行單元格，並完成我們在最後為你留下的一些挑戰。

![COVID 醫療處理](../../../../translated_images/covidtreat.b2ba59f57ca45fbcda36e0ddca3f8cfdddeeed6ca879ea7f866d93fa6ec65791.tw.png)

## 處理圖片數據

最近，已經開發出非常強大的 AI 模型，能夠理解圖片。有許多任務可以使用預訓練的神經網絡或雲服務解決。一些範例包括：

* **圖片分類**，可以幫助你將圖片分類到預定義的類別中。你可以使用像 [Custom Vision](https://azure.microsoft.com/services/cognitive-services/custom-vision-service/?WT.mc_id=academic-77958-bethanycheum) 這樣的服務輕鬆訓練自己的圖片分類器。
* **物件檢測**，用於檢測圖片中的不同物件。像 [Computer Vision](https://azure.microsoft.com/services/cognitive-services/computer-vision/?WT.mc_id=academic-77958-bethanycheum) 這樣的服務可以檢測許多常見物件，你也可以訓練 [Custom Vision](https://azure.microsoft.com/services/cognitive-services/custom-vision-service/?WT.mc_id=academic-77958-bethanycheum) 模型來檢測一些特定的感興趣物件。
* **人臉檢測**，包括年齡、性別和情緒檢測。這可以通過 [Face API](https://azure.microsoft.com/services/cognitive-services/face/?WT.mc_id=academic-77958-bethanycheum) 完成。

所有這些雲服務都可以通過 [Python SDK](https://docs.microsoft.com/samples/azure-samples/cognitive-services-python-sdk-samples/cognitive-services-python-sdk-samples/?WT.mc_id=academic-77958-bethanycheum) 呼叫，因此可以輕鬆地整合到你的數據探索工作流程中。

以下是一些探索圖片數據來源的範例：
* 在部落格文章 [如何在不編碼的情況下學習數據科學](https://soshnikov.com/azure/how-to-learn-data-science-without-coding/) 中，我們探索了 Instagram 照片，試圖了解什麼使人們對照片按更多讚。我們首先使用 [Computer Vision](https://azure.microsoft.com/services/cognitive-services/computer-vision/?WT.mc_id=academic-77958-bethanycheum) 從圖片中提取盡可能多的資訊，然後使用 [Azure Machine Learning AutoML](https://docs.microsoft.com/azure/machine-learning/concept-automated-ml/?WT.mc_id=academic-77958-bethanycheum) 建立可解釋的模型。
* 在 [Facial Studies Workshop](https://github.com/CloudAdvocacy/FaceStudies) 中，我們使用 [Face API](https://azure.microsoft.com/services/cognitive-services/face/?WT.mc_id=academic-77958-bethanycheum) 提取活動照片中人們的情緒，試圖了解什麼讓人們感到快樂。

## 結論

無論你已經擁有結構化數據還是非結構化數據，使用 Python 你都可以執行與數據處理和理解相關的所有步驟。這可能是數據處理最靈活的方式，這也是為什麼大多數數據科學家將 Python 作為主要工具的原因。如果你對數據科學之旅是認真的，那麼深入學習 Python 可能是一個好主意！

## [課後測驗](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/13)

## 回顧與自學

**書籍**
* [Wes McKinney. Python for Data Analysis: Data Wrangling with Pandas, NumPy, and IPython](https://www.amazon.com/gp/product/1491957662)

**線上資源**
* 官方 [10 分鐘學 Pandas](https://pandas.pydata.org/pandas-docs/stable/user_guide/10min.html) 教程
* [Pandas 視覺化文檔](https://pandas.pydata.org/pandas-docs/stable/user_guide/visualization.html)

**學習 Python**
* [用 Turtle Graphics 和分形圖形以有趣的方式學習 Python](https://github.com/shwars/pycourse)
* [從 Python 的第一步開始](https://docs.microsoft.com/learn/paths/python-first-steps/?WT.mc_id=academic-77958-bethanycheum) 的學習路徑在 [Microsoft Learn](http://learn.microsoft.com/?WT.mc_id=academic-77958-bethanycheum)

## 作業

[對上述挑戰進行更詳細的數據研究](assignment.md)

## 致謝

這節課由 [Dmitry Soshnikov](http://soshnikov.com) 用 ♥️ 編寫。

**免責聲明**：  
本文件使用 AI 翻譯服務 [Co-op Translator](https://github.com/Azure/co-op-translator) 進行翻譯。雖然我們致力於提供準確的翻譯，但請注意，自動翻譯可能包含錯誤或不準確之處。原始文件的母語版本應被視為權威來源。對於重要資訊，建議尋求專業人工翻譯。我們對因使用此翻譯而引起的任何誤解或錯誤解釋不承擔責任。