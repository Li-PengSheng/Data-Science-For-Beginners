<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "87faccac113d772551486a67a607153e",
  "translation_date": "2025-08-27T10:13:45+00:00",
  "source_file": "3-Data-Visualization/10-visualization-distributions/README.md",
  "language_code": "ur"
}
-->
# تقسیمات کو بصری بنانا

|![ Sketchnote by [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/10-Visualizing-Distributions.png)|
|:---:|
| تقسیمات کو بصری بنانا - _Sketchnote by [@nitya](https://twitter.com/nitya)_ |

پچھلے سبق میں، آپ نے منیسوٹا کے پرندوں کے بارے میں ایک ڈیٹا سیٹ کے کچھ دلچسپ حقائق سیکھے۔ آپ نے آؤٹ لائرز کو بصری بنا کر کچھ غلط ڈیٹا دریافت کیا اور پرندوں کی اقسام کے درمیان زیادہ سے زیادہ لمبائی کے فرق کو دیکھا۔

## [لیکچر سے پہلے کا کوئز](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/18)
## پرندوں کے ڈیٹا سیٹ کو دریافت کریں

ڈیٹا کو سمجھنے کا ایک اور طریقہ یہ ہے کہ اس کی تقسیم کو دیکھیں، یعنی ڈیٹا کسی محور کے ساتھ کیسے ترتیب دیا گیا ہے۔ مثال کے طور پر، آپ یہ جاننا چاہیں گے کہ اس ڈیٹا سیٹ میں منیسوٹا کے پرندوں کے زیادہ سے زیادہ پروں کے پھیلاؤ یا زیادہ سے زیادہ جسمانی وزن کی عمومی تقسیم کیا ہے۔

آئیے اس ڈیٹا سیٹ میں موجود ڈیٹا کی تقسیم کے بارے میں کچھ حقائق دریافت کریں۔ اس سبق کے فولڈر کی جڑ میں موجود _notebook.ipynb_ فائل میں، Pandas، Matplotlib، اور اپنے ڈیٹا کو درآمد کریں:

```python
import pandas as pd
import matplotlib.pyplot as plt
birds = pd.read_csv('../../data/birds.csv')
birds.head()
```

|      | Name                         | ScientificName         | Category              | Order        | Family   | Genus       | ConservationStatus | MinLength | MaxLength | MinBodyMass | MaxBodyMass | MinWingspan | MaxWingspan |
| ---: | :--------------------------- | :--------------------- | :-------------------- | :----------- | :------- | :---------- | :----------------- | --------: | --------: | ----------: | ----------: | ----------: | ----------: |
|    0 | Black-bellied whistling-duck | Dendrocygna autumnalis | Ducks/Geese/Waterfowl | Anseriformes | Anatidae | Dendrocygna | LC                 |        47 |        56 |         652 |        1020 |          76 |          94 |
|    1 | Fulvous whistling-duck       | Dendrocygna bicolor    | Ducks/Geese/Waterfowl | Anseriformes | Anatidae | Dendrocygna | LC                 |        45 |        53 |         712 |        1050 |          85 |          93 |
|    2 | Snow goose                   | Anser caerulescens     | Ducks/Geese/Waterfowl | Anseriformes | Anatidae | Anser       | LC                 |        64 |        79 |        2050 |        4050 |         135 |         165 |
|    3 | Ross's goose                 | Anser rossii           | Ducks/Geese/Waterfowl | Anseriformes | Anatidae | Anser       | LC                 |      57.3 |        64 |        1066 |        1567 |         113 |         116 |
|    4 | Greater white-fronted goose  | Anser albifrons        | Ducks/Geese/Waterfowl | Anseriformes | Anatidae | Anser       | LC                 |        64 |        81 |        1930 |        3310 |         130 |         165 |

عمومی طور پر، آپ ڈیٹا کی تقسیم کو جلدی سے دیکھ سکتے ہیں جیسا کہ ہم نے پچھلے سبق میں ایک اسکیٹر پلاٹ کے ذریعے کیا:

```python
birds.plot(kind='scatter',x='MaxLength',y='Order',figsize=(12,8))

plt.title('Max Length per Order')
plt.ylabel('Order')
plt.xlabel('Max Length')

plt.show()
```
![max length per order](../../../../translated_images/scatter-wb.9d98b0ed7f0388af979441853361a11df5f518f5307938a503ca7913e986111b.ur.png)

یہ پرندوں کے آرڈر کے مطابق جسمانی لمبائی کی عمومی تقسیم کا جائزہ دیتا ہے، لیکن یہ حقیقی تقسیمات کو ظاہر کرنے کا بہترین طریقہ نہیں ہے۔ یہ کام عام طور پر ہسٹوگرام بنا کر کیا جاتا ہے۔

## ہسٹوگرام کے ساتھ کام کرنا

Matplotlib ہسٹوگرامز کے ذریعے ڈیٹا کی تقسیم کو بصری بنانے کے بہترین طریقے فراہم کرتا ہے۔ یہ چارٹ بار چارٹ کی طرح ہوتا ہے جہاں تقسیم کو بارز کے اتار چڑھاؤ کے ذریعے دیکھا جا سکتا ہے۔ ہسٹوگرام بنانے کے لیے، آپ کو عددی ڈیٹا کی ضرورت ہوتی ہے۔ ہسٹوگرام بنانے کے لیے، آپ ایک چارٹ بنا سکتے ہیں جس میں قسم کو 'hist' کے طور پر بیان کیا گیا ہو۔ یہ چارٹ پورے ڈیٹا سیٹ کی عددی ڈیٹا کی حد کے لیے MaxBodyMass کی تقسیم کو ظاہر کرتا ہے۔ ڈیٹا کے صف کو چھوٹے حصوں میں تقسیم کر کے، یہ ڈیٹا کی قدروں کی تقسیم کو ظاہر کر سکتا ہے:

```python
birds['MaxBodyMass'].plot(kind = 'hist', bins = 10, figsize = (12,12))
plt.show()
```
![distribution over the entire dataset](../../../../translated_images/dist1-wb.0d0cac82e2974fbbec635826fefead401af795f82e2279e2e2678bf2c117d827.ur.png)

جیسا کہ آپ دیکھ سکتے ہیں، اس ڈیٹا سیٹ میں موجود 400+ پرندوں میں سے زیادہ تر کا زیادہ سے زیادہ جسمانی وزن 2000 سے کم ہے۔ `bins` پیرامیٹر کو زیادہ تعداد، جیسے 30، پر تبدیل کر کے ڈیٹا کے بارے میں مزید بصیرت حاصل کریں:

```python
birds['MaxBodyMass'].plot(kind = 'hist', bins = 30, figsize = (12,12))
plt.show()
```
![distribution over the entire dataset with larger bins param](../../../../translated_images/dist2-wb.2c0a7a3499b2fbf561e9f93b69f265dfc538dc78f6de15088ba84a88152e26ba.ur.png)

یہ چارٹ تقسیم کو تھوڑا زیادہ تفصیلی انداز میں دکھاتا ہے۔ ایک کم بائیں طرف جھکا ہوا چارٹ اس وقت بنایا جا سکتا ہے جب آپ صرف ایک دی گئی حد کے اندر ڈیٹا منتخب کریں:

اپنے ڈیٹا کو فلٹر کریں تاکہ صرف وہ پرندے شامل ہوں جن کا جسمانی وزن 60 سے کم ہو، اور 40 `bins` دکھائیں:

```python
filteredBirds = birds[(birds['MaxBodyMass'] > 1) & (birds['MaxBodyMass'] < 60)]      
filteredBirds['MaxBodyMass'].plot(kind = 'hist',bins = 40,figsize = (12,12))
plt.show()     
```
![filtered histogram](../../../../translated_images/dist3-wb.64b88db7f9780200bd486a2c2a3252548dd439672dbd3f778193db7f654b100c.ur.png)

✅ کچھ دوسرے فلٹرز اور ڈیٹا پوائنٹس آزمائیں۔ ڈیٹا کی مکمل تقسیم دیکھنے کے لیے، `['MaxBodyMass']` فلٹر کو ہٹا دیں تاکہ لیبل شدہ تقسیمات دکھائی دیں۔

ہسٹوگرام کچھ خوبصورت رنگ اور لیبلنگ کی بہتریاں بھی پیش کرتا ہے:

دو تقسیمات کے درمیان تعلق کا موازنہ کرنے کے لیے ایک 2D ہسٹوگرام بنائیں۔ آئیے `MaxBodyMass` اور `MaxLength` کا موازنہ کریں۔ Matplotlib ایک بلٹ ان طریقہ فراہم کرتا ہے جو روشن رنگوں کے ذریعے ہم آہنگی کو ظاہر کرتا ہے:

```python
x = filteredBirds['MaxBodyMass']
y = filteredBirds['MaxLength']

fig, ax = plt.subplots(tight_layout=True)
hist = ax.hist2d(x, y)
```
ایسا لگتا ہے کہ ان دو عناصر کے درمیان ایک متوقع محور کے ساتھ ایک متوقع تعلق ہے، جس میں ہم آہنگی کا ایک خاص طور پر مضبوط نقطہ موجود ہے:

![2D plot](../../../../translated_images/2D-wb.ae22fdd33936507a41e3af22e11e4903b04a9be973b23a4e05214efaccfd66c8.ur.png)

ہسٹوگرام عددی ڈیٹا کے لیے ڈیفالٹ طور پر اچھا کام کرتے ہیں۔ اگر آپ کو متن پر مبنی ڈیٹا کے مطابق تقسیمات دیکھنے کی ضرورت ہو تو کیا ہوگا؟

## متن پر مبنی ڈیٹا کے ذریعے ڈیٹا سیٹ کی تقسیم کو دریافت کریں

اس ڈیٹا سیٹ میں پرندوں کی اقسام، ان کے جینس، انواع، خاندان، اور ان کے تحفظ کی حیثیت کے بارے میں بھی اچھی معلومات شامل ہیں۔ آئیے اس تحفظ کی معلومات کو دریافت کریں۔ پرندوں کی تقسیم ان کے تحفظ کی حیثیت کے مطابق کیا ہے؟

> ✅ اس ڈیٹا سیٹ میں تحفظ کی حیثیت کو بیان کرنے کے لیے کئی مخففات استعمال کیے گئے ہیں۔ یہ مخففات [IUCN Red List Categories](https://www.iucnredlist.org/) سے آتے ہیں، جو انواع کی حیثیت کو کیٹلاگ کرنے والی ایک تنظیم ہے۔
> 
> - CR: شدید خطرے میں
> - EN: خطرے میں
> - EX: معدوم
> - LC: کم سے کم تشویش
> - NT: قریب خطرے میں
> - VU: کمزور

یہ متن پر مبنی قدریں ہیں، لہذا آپ کو ہسٹوگرام بنانے کے لیے ایک تبدیلی کرنے کی ضرورت ہوگی۔ فلٹر شدہ پرندوں کے ڈیٹا فریم کا استعمال کرتے ہوئے، اس کی تحفظ کی حیثیت کو اس کے کم از کم پروں کے پھیلاؤ کے ساتھ دکھائیں۔ آپ کیا دیکھتے ہیں؟

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

![wingspan and conservation collation](../../../../translated_images/histogram-conservation-wb.3c40450eb072c14de7a1a3ec5c0fcba4995531024760741b392911b567fd8b70.ur.png)

کم از کم پروں کے پھیلاؤ اور تحفظ کی حیثیت کے درمیان کوئی اچھا تعلق نظر نہیں آتا۔ اس طریقے کا استعمال کرتے ہوئے ڈیٹا سیٹ کے دیگر عناصر کو آزمائیں۔ آپ مختلف فلٹرز بھی آزما سکتے ہیں۔ کیا آپ کو کوئی تعلق نظر آتا ہے؟

## کثافت کے پلاٹس

آپ نے محسوس کیا ہوگا کہ اب تک دیکھے گئے ہسٹوگرام 'سیڑھی دار' ہیں اور ہموار آرک میں نہیں بہتے۔ ایک ہموار کثافت چارٹ دکھانے کے لیے، آپ کثافت پلاٹ آزما سکتے ہیں۔

کثافت پلاٹس کے ساتھ کام کرنے کے لیے، ایک نئی پلاٹنگ لائبریری، [Seaborn](https://seaborn.pydata.org/generated/seaborn.kdeplot.html) سے واقف ہوں۔

Seaborn کو لوڈ کریں اور ایک بنیادی کثافت پلاٹ آزمائیں:

```python
import seaborn as sns
import matplotlib.pyplot as plt
sns.kdeplot(filteredBirds['MinWingspan'])
plt.show()
```
![Density plot](../../../../translated_images/density1.8801043bd4af2567b0f706332b5853c7614e5e4b81b457acc27eb4e092a65cbd.ur.png)

آپ دیکھ سکتے ہیں کہ یہ پلاٹ کم از کم پروں کے پھیلاؤ کے ڈیٹا کے لیے پچھلے پلاٹ کی عکاسی کرتا ہے؛ یہ صرف تھوڑا زیادہ ہموار ہے۔ Seaborn کی دستاویزات کے مطابق، "ہسٹوگرام کے مقابلے میں، KDE ایک ایسا پلاٹ تیار کر سکتا ہے جو کم الجھا ہوا اور زیادہ قابل فہم ہو، خاص طور پر جب متعدد تقسیمات کو کھینچتے ہیں۔ لیکن اگر بنیادی تقسیم محدود یا ہموار نہ ہو تو اس میں بگاڑ پیدا کرنے کی صلاحیت ہوتی ہے۔" [ماخذ](https://seaborn.pydata.org/generated/seaborn.kdeplot.html) دوسرے الفاظ میں، آؤٹ لائرز ہمیشہ آپ کے چارٹس کو خراب کر سکتے ہیں۔

اگر آپ اس سیڑھی دار MaxBodyMass لائن کو دوبارہ دیکھنا چاہتے ہیں جو آپ نے دوسرا چارٹ بنایا تھا، تو آپ اسے اس طریقے کا استعمال کرتے ہوئے بہت اچھی طرح ہموار کر سکتے ہیں:

```python
sns.kdeplot(filteredBirds['MaxBodyMass'])
plt.show()
```
![smooth bodymass line](../../../../translated_images/density2.8e7647257060ff544a1aaded57e8dd1887586bfe340139e9b77ac1e5287f7977.ur.png)

اگر آپ ایک ہموار، لیکن زیادہ ہموار نہ ہونے والی لائن چاہتے ہیں، تو `bw_adjust` پیرامیٹر میں ترمیم کریں:

```python
sns.kdeplot(filteredBirds['MaxBodyMass'], bw_adjust=.2)
plt.show()
```
![less smooth bodymass line](../../../../translated_images/density3.84ae27da82f31e6b83ad977646f029a1d21186574d7581facd70123b3eb257ee.ur.png)

✅ اس قسم کے پلاٹ کے لیے دستیاب پیرامیٹرز کے بارے میں پڑھیں اور تجربہ کریں!

یہ قسم کے چارٹس خوبصورت وضاحتی بصریات پیش کرتے ہیں۔ مثال کے طور پر، چند لائنوں کے کوڈ کے ساتھ، آپ پرندوں کے آرڈر کے مطابق زیادہ سے زیادہ جسمانی وزن کی کثافت دکھا سکتے ہیں:

```python
sns.kdeplot(
   data=filteredBirds, x="MaxBodyMass", hue="Order",
   fill=True, common_norm=False, palette="crest",
   alpha=.5, linewidth=0,
)
```

![bodymass per order](../../../../translated_images/density4.e9d6c033f15c500fd33df94cb592b9f5cf1ed2a3d213c448a3f9e97ba39573ce.ur.png)

آپ ایک چارٹ میں کئی متغیرات کی کثافت کو بھی نقشہ بنا سکتے ہیں۔ پرندے کی زیادہ سے زیادہ لمبائی اور کم از کم لمبائی کا ان کے تحفظ کی حیثیت کے ساتھ موازنہ کریں:

```python
sns.kdeplot(data=filteredBirds, x="MinLength", y="MaxLength", hue="ConservationStatus")
```

![multiple densities, superimposed](../../../../translated_images/multi.56548caa9eae8d0fd9012a8586295538c7f4f426e2abc714ba070e2e4b1fc2c1.ur.png)

شاید یہ تحقیق کرنے کے قابل ہو کہ آیا لمبائی کے مطابق 'کمزور' پرندوں کا کلسٹر معنی خیز ہے یا نہیں۔

## 🚀 چیلنج

ہسٹوگرامز بنیادی اسکیٹر پلاٹس، بار چارٹس، یا لائن چارٹس کے مقابلے میں زیادہ نفیس قسم کے چارٹس ہیں۔ انٹرنیٹ پر تلاش کریں اور ہسٹوگرامز کے استعمال کی اچھی مثالیں تلاش کریں۔ یہ کیسے استعمال کیے جاتے ہیں، کیا ظاہر کرتے ہیں، اور کن شعبوں یا تحقیق کے علاقوں میں ان کا رجحان ہوتا ہے؟

## [لیکچر کے بعد کا کوئز](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/19)

## جائزہ اور خود مطالعہ

اس سبق میں، آپ نے Matplotlib کا استعمال کیا اور زیادہ نفیس چارٹس دکھانے کے لیے Seaborn کے ساتھ کام کرنا شروع کیا۔ Seaborn میں `kdeplot` پر تحقیق کریں، جو "ایک یا زیادہ جہتوں میں مسلسل احتمال کثافت کا منحنی خط" ہے۔ [دستاویزات](https://seaborn.pydata.org/generated/seaborn.kdeplot.html) کو پڑھیں تاکہ یہ سمجھ سکیں کہ یہ کیسے کام کرتا ہے۔

## اسائنمنٹ

[اپنی مہارتوں کا اطلاق کریں](assignment.md)

---

**ڈس کلیمر**:  
یہ دستاویز AI ترجمہ سروس [Co-op Translator](https://github.com/Azure/co-op-translator) کا استعمال کرتے ہوئے ترجمہ کی گئی ہے۔ ہم درستگی کے لیے پوری کوشش کرتے ہیں، لیکن براہ کرم آگاہ رہیں کہ خودکار ترجمے میں غلطیاں یا عدم درستگی ہو سکتی ہیں۔ اصل دستاویز کو اس کی اصل زبان میں مستند ذریعہ سمجھا جانا چاہیے۔ اہم معلومات کے لیے، پیشہ ور انسانی ترجمہ کی سفارش کی جاتی ہے۔ اس ترجمے کے استعمال سے پیدا ہونے والی کسی بھی غلط فہمی یا غلط تشریح کے لیے ہم ذمہ دار نہیں ہیں۔