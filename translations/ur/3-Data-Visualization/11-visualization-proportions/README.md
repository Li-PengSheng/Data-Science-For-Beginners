<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "af6a12015c6e250e500b570a9fa42593",
  "translation_date": "2025-08-27T10:48:05+00:00",
  "source_file": "3-Data-Visualization/11-visualization-proportions/README.md",
  "language_code": "ur"
}
-->
# تناسبات کی بصری نمائندگی

|![ [(@sketchthedocs)](https://sketchthedocs.dev) کی اسکیچ نوٹ ](../../sketchnotes/11-Visualizing-Proportions.png)|
|:---:|
|تناسبات کی بصری نمائندگی - _[@nitya](https://twitter.com/nitya) کی اسکیچ نوٹ_ |

اس سبق میں، آپ ایک مختلف قدرتی ڈیٹا سیٹ کا استعمال کریں گے تاکہ تناسبات کو بصری طور پر سمجھ سکیں، جیسے کہ مشرومز کے بارے میں دیے گئے ڈیٹا سیٹ میں مختلف قسم کے فنگس کی تعداد۔ آئیے اس دلچسپ فنگس کو ایک ڈیٹا سیٹ کے ذریعے دریافت کریں جو آڈوبون سے حاصل کیا گیا ہے اور جس میں Agaricus اور Lepiota خاندانوں کے 23 اقسام کے گِلڈ مشرومز کی تفصیلات شامل ہیں۔ آپ مزیدار بصری نمائندگیوں کے ساتھ تجربہ کریں گے جیسے:

- پائی چارٹس 🥧  
- ڈونٹ چارٹس 🍩  
- وافل چارٹس 🧇  

> 💡 مائیکروسافٹ ریسرچ کا ایک بہت دلچسپ پروجیکٹ [Charticulator](https://charticulator.com) ایک مفت ڈریگ اینڈ ڈراپ انٹرفیس فراہم کرتا ہے ڈیٹا ویژولائزیشن کے لیے۔ ان کے ایک ٹیوٹوریل میں بھی یہ مشروم ڈیٹا سیٹ استعمال کیا گیا ہے! تو آپ ڈیٹا کو دریافت کر سکتے ہیں اور ساتھ ہی لائبریری سیکھ سکتے ہیں: [Charticulator tutorial](https://charticulator.com/tutorials/tutorial4.html)۔

## [لیکچر سے پہلے کا کوئز](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/20)

## اپنے مشرومز کو جانیں 🍄

مشرومز بہت دلچسپ ہوتے ہیں۔ آئیے ایک ڈیٹا سیٹ درآمد کریں تاکہ ان کا مطالعہ کیا جا سکے:

```python
import pandas as pd
import matplotlib.pyplot as plt
mushrooms = pd.read_csv('../../data/mushrooms.csv')
mushrooms.head()
```  
ایک ٹیبل پرنٹ ہوتا ہے جس میں تجزیے کے لیے شاندار ڈیٹا موجود ہے:

| class     | cap-shape | cap-surface | cap-color | bruises | odor    | gill-attachment | gill-spacing | gill-size | gill-color | stalk-shape | stalk-root | stalk-surface-above-ring | stalk-surface-below-ring | stalk-color-above-ring | stalk-color-below-ring | veil-type | veil-color | ring-number | ring-type | spore-print-color | population | habitat |
| --------- | --------- | ----------- | --------- | ------- | ------- | --------------- | ------------ | --------- | ---------- | ----------- | ---------- | ------------------------ | ------------------------ | ---------------------- | ---------------------- | --------- | ---------- | ----------- | --------- | ----------------- | ---------- | ------- |
| Poisonous | Convex    | Smooth      | Brown     | Bruises | Pungent | Free            | Close        | Narrow    | Black      | Enlarging   | Equal      | Smooth                   | Smooth                   | White                  | White                  | Partial   | White      | One         | Pendant   | Black             | Scattered  | Urban   |
| Edible    | Convex    | Smooth      | Yellow    | Bruises | Almond  | Free            | Close        | Broad     | Black      | Enlarging   | Club       | Smooth                   | Smooth                   | White                  | White                  | Partial   | White      | One         | Pendant   | Brown             | Numerous   | Grasses |
| Edible    | Bell      | Smooth      | White     | Bruises | Anise   | Free            | Close        | Broad     | Brown      | Enlarging   | Club       | Smooth                   | Smooth                   | White                  | White                  | Partial   | White      | One         | Pendant   | Brown             | Numerous   | Meadows |
| Poisonous | Convex    | Scaly       | White     | Bruises | Pungent | Free            | Close        | Narrow    | Brown      | Enlarging   | Equal      | Smooth                   | Smooth                   | White                  | White                  | Partial   | White      | One         | Pendant   | Black             | Scattered  | Urban   |

فوراً آپ دیکھتے ہیں کہ تمام ڈیٹا متنی ہے۔ آپ کو اس ڈیٹا کو چارٹ میں استعمال کرنے کے قابل بنانے کے لیے تبدیل کرنا ہوگا۔ درحقیقت، زیادہ تر ڈیٹا ایک آبجیکٹ کے طور پر ظاہر کیا گیا ہے:

```python
print(mushrooms.select_dtypes(["object"]).columns)
```  

آؤٹ پٹ یہ ہے:

```output
Index(['class', 'cap-shape', 'cap-surface', 'cap-color', 'bruises', 'odor',
       'gill-attachment', 'gill-spacing', 'gill-size', 'gill-color',
       'stalk-shape', 'stalk-root', 'stalk-surface-above-ring',
       'stalk-surface-below-ring', 'stalk-color-above-ring',
       'stalk-color-below-ring', 'veil-type', 'veil-color', 'ring-number',
       'ring-type', 'spore-print-color', 'population', 'habitat'],
      dtype='object')
```  
اس ڈیٹا کو لیں اور 'class' کالم کو ایک زمرے میں تبدیل کریں:

```python
cols = mushrooms.select_dtypes(["object"]).columns
mushrooms[cols] = mushrooms[cols].astype('category')
```  

```python
edibleclass=mushrooms.groupby(['class']).count()
edibleclass
```  

اب، اگر آپ مشرومز کا ڈیٹا پرنٹ کریں تو آپ دیکھ سکتے ہیں کہ اسے زہریلے/کھانے کے قابل کلاس کے مطابق زمروں میں گروپ کیا گیا ہے:

|           | cap-shape | cap-surface | cap-color | bruises | odor | gill-attachment | gill-spacing | gill-size | gill-color | stalk-shape | ... | stalk-surface-below-ring | stalk-color-above-ring | stalk-color-below-ring | veil-type | veil-color | ring-number | ring-type | spore-print-color | population | habitat |
| --------- | --------- | ----------- | --------- | ------- | ---- | --------------- | ------------ | --------- | ---------- | ----------- | --- | ------------------------ | ---------------------- | ---------------------- | --------- | ---------- | ----------- | --------- | ----------------- | ---------- | ------- |
| class     |           |             |           |         |      |                 |              |           |            |             |     |                          |                        |                        |           |            |             |           |                   |            |         |
| Edible    | 4208      | 4208        | 4208      | 4208    | 4208 | 4208            | 4208         | 4208      | 4208       | 4208        | ... | 4208                     | 4208                   | 4208                   | 4208      | 4208       | 4208        | 4208      | 4208              | 4208       | 4208    |
| Poisonous | 3916      | 3916        | 3916      | 3916    | 3916 | 3916            | 3916         | 3916      | 3916       | 3916        | ... | 3916                     | 3916                   | 3916                   | 3916      | 3916       | 3916        | 3916      | 3916              | 3916       | 3916    |

اگر آپ اس ٹیبل میں پیش کردہ ترتیب کے مطابق اپنی کلاس کیٹیگری لیبلز بنائیں تو آپ ایک پائی چارٹ بنا سکتے ہیں:

## پائی!

```python
labels=['Edible','Poisonous']
plt.pie(edibleclass['population'],labels=labels,autopct='%.1f %%')
plt.title('Edible?')
plt.show()
```  
لو جی، ایک پائی چارٹ جو اس ڈیٹا کے تناسبات کو ان دو مشرومز کی کلاسز کے مطابق دکھاتا ہے۔ لیبلز کی ترتیب کو درست رکھنا خاص طور پر یہاں بہت اہم ہے، اس لیے اس بات کو یقینی بنائیں کہ لیبل آرے کی ترتیب کی تصدیق کریں!

![پائی چارٹ](../../../../translated_images/pie1-wb.e201f2fcc335413143ce37650fb7f5f0bb21358e7823a327ed8644dfb84be9db.ur.png)

## ڈونٹس!

ایک بصری طور پر زیادہ دلچسپ پائی چارٹ ڈونٹ چارٹ ہے، جو ایک پائی چارٹ ہے جس کے درمیان میں ایک سوراخ ہوتا ہے۔ آئیے اپنے ڈیٹا کو اس طریقے سے دیکھتے ہیں۔

ان مختلف رہائش گاہوں پر نظر ڈالیں جہاں مشرومز اگتے ہیں:

```python
habitat=mushrooms.groupby(['habitat']).count()
habitat
```  
یہاں، آپ اپنے ڈیٹا کو رہائش گاہ کے مطابق گروپ کر رہے ہیں۔ سات درج ہیں، لہذا ان کو اپنے ڈونٹ چارٹ کے لیبلز کے طور پر استعمال کریں:

```python
labels=['Grasses','Leaves','Meadows','Paths','Urban','Waste','Wood']

plt.pie(habitat['class'], labels=labels,
        autopct='%1.1f%%', pctdistance=0.85)
  
center_circle = plt.Circle((0, 0), 0.40, fc='white')
fig = plt.gcf()

fig.gca().add_artist(center_circle)
  
plt.title('Mushroom Habitats')
  
plt.show()
```  

![ڈونٹ چارٹ](../../../../translated_images/donut-wb.be3c12a22712302b5d10c40014d5389d4a1ae4412fe1655b3cf4af57b64f799a.ur.png)

یہ کوڈ ایک چارٹ اور ایک مرکز کا دائرہ بناتا ہے، پھر اس مرکز کے دائرے کو چارٹ میں شامل کرتا ہے۔ مرکز کے دائرے کی چوڑائی کو `0.40` کو کسی اور قدر میں تبدیل کرکے ایڈٹ کریں۔

ڈونٹ چارٹس کو کئی طریقوں سے ایڈجسٹ کیا جا سکتا ہے تاکہ لیبلز کو نمایاں کیا جا سکے۔ خاص طور پر لیبلز کو پڑھنے میں آسان بنانے کے لیے نمایاں کیا جا سکتا ہے۔ مزید جانیں [docs](https://matplotlib.org/stable/gallery/pie_and_polar_charts/pie_and_donut_labels.html?highlight=donut) میں۔

اب جب کہ آپ جانتے ہیں کہ اپنے ڈیٹا کو گروپ کیسے کرنا ہے اور پھر اسے پائی یا ڈونٹ کے طور پر کیسے دکھانا ہے، آپ دیگر قسم کے چارٹس کو دریافت کر سکتے ہیں۔ ایک وافل چارٹ آزمائیں، جو مقدار کو دریافت کرنے کا ایک مختلف طریقہ ہے۔

## وافلز!

'وافل' قسم کا چارٹ مقدار کو 2D مربعوں کی صف کے طور پر بصری طور پر ظاہر کرنے کا ایک مختلف طریقہ ہے۔ اس ڈیٹا سیٹ میں مشرومز کی ٹوپی کے مختلف رنگوں کی مقدار کو بصری طور پر دیکھنے کی کوشش کریں۔ ایسا کرنے کے لیے، آپ کو ایک مددگار لائبریری [PyWaffle](https://pypi.org/project/pywaffle/) انسٹال کرنی ہوگی اور Matplotlib استعمال کرنا ہوگا:

```python
pip install pywaffle
```  

اپنے ڈیٹا کے ایک حصے کو منتخب کریں اور گروپ کریں:

```python
capcolor=mushrooms.groupby(['cap-color']).count()
capcolor
```  

لیبلز بنا کر اور پھر اپنے ڈیٹا کو گروپ کرکے ایک وافل چارٹ بنائیں:

```python
import pandas as pd
import matplotlib.pyplot as plt
from pywaffle import Waffle
  
data ={'color': ['brown', 'buff', 'cinnamon', 'green', 'pink', 'purple', 'red', 'white', 'yellow'],
    'amount': capcolor['class']
     }
  
df = pd.DataFrame(data)
  
fig = plt.figure(
    FigureClass = Waffle,
    rows = 100,
    values = df.amount,
    labels = list(df.color),
    figsize = (30,30),
    colors=["brown", "tan", "maroon", "green", "pink", "purple", "red", "whitesmoke", "yellow"],
)
```  

وافل چارٹ کا استعمال کرتے ہوئے، آپ اس مشرومز ڈیٹا سیٹ کے ٹوپی کے رنگوں کے تناسب کو واضح طور پر دیکھ سکتے ہیں۔ دلچسپ بات یہ ہے کہ بہت سے سبز ٹوپی والے مشرومز ہیں!

![وافل چارٹ](../../../../translated_images/waffle.5455dbae4ccf17d53bb40ff0a657ecef7b8aa967e27a19cc96325bd81598f65e.ur.png)

✅ Pywaffle چارٹس میں آئیکنز کی حمایت کرتا ہے جو [Font Awesome](https://fontawesome.com/) میں دستیاب کسی بھی آئیکن کو استعمال کرتے ہیں۔ آئیکنز کے بجائے مربعوں کا استعمال کرتے ہوئے ایک اور دلچسپ وافل چارٹ بنانے کے لیے کچھ تجربات کریں۔

اس سبق میں، آپ نے تناسبات کو بصری طور پر ظاہر کرنے کے تین طریقے سیکھے۔ سب سے پہلے، آپ کو اپنے ڈیٹا کو زمروں میں گروپ کرنا ہوگا اور پھر فیصلہ کرنا ہوگا کہ ڈیٹا کو ظاہر کرنے کا بہترین طریقہ کون سا ہے - پائی، ڈونٹ، یا وافل۔ یہ سب مزیدار ہیں اور صارف کو ڈیٹا سیٹ کا فوری جائزہ فراہم کرتے ہیں۔

## 🚀 چیلنج

[Charticulator](https://charticulator.com) میں ان مزیدار چارٹس کو دوبارہ بنانے کی کوشش کریں۔

## [لیکچر کے بعد کا کوئز](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/21)

## جائزہ اور خود مطالعہ

کبھی کبھی یہ واضح نہیں ہوتا کہ پائی، ڈونٹ، یا وافل چارٹ کب استعمال کرنا ہے۔ اس موضوع پر پڑھنے کے لیے یہاں کچھ مضامین ہیں:

https://www.beautiful.ai/blog/battle-of-the-charts-pie-chart-vs-donut-chart  

https://medium.com/@hypsypops/pie-chart-vs-donut-chart-showdown-in-the-ring-5d24fd86a9ce  

https://www.mit.edu/~mbarker/formula1/f1help/11-ch-c6.htm  

https://medium.datadriveninvestor.com/data-visualization-done-the-right-way-with-tableau-waffle-chart-fdf2a19be402  

مزید معلومات حاصل کرنے کے لیے اس مشکل فیصلے پر تحقیق کریں۔

## اسائنمنٹ

[ایکسسل میں آزمائیں](assignment.md)  

---

**ڈسکلیمر**:  
یہ دستاویز AI ترجمہ سروس [Co-op Translator](https://github.com/Azure/co-op-translator) کا استعمال کرتے ہوئے ترجمہ کی گئی ہے۔ ہم درستگی کے لیے کوشش کرتے ہیں، لیکن براہ کرم آگاہ رہیں کہ خودکار ترجمے میں غلطیاں یا عدم درستگی ہو سکتی ہیں۔ اصل دستاویز، جو اس کی مقامی زبان میں ہے، کو مستند ذریعہ سمجھا جانا چاہیے۔ اہم معلومات کے لیے، پیشہ ور انسانی ترجمہ کی سفارش کی جاتی ہے۔ اس ترجمے کے استعمال سے پیدا ہونے والی کسی بھی غلط فہمی یا غلط تشریح کے لیے ہم ذمہ دار نہیں ہیں۔