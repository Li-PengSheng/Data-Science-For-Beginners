<!--
CO_OP_TRANSLATOR_METADATA:
{
  "original_hash": "87faccac113d772551486a67a607153e",
  "translation_date": "2025-08-28T18:47:44+00:00",
  "source_file": "3-Data-Visualization/10-visualization-distributions/README.md",
  "language_code": "vi"
}
-->
# Trực quan hóa phân bố

|![ Sketchnote của [(@sketchthedocs)](https://sketchthedocs.dev) ](../../sketchnotes/10-Visualizing-Distributions.png)|
|:---:|
| Trực quan hóa phân bố - _Sketchnote của [@nitya](https://twitter.com/nitya)_ |

Trong bài học trước, bạn đã tìm hiểu một số thông tin thú vị về bộ dữ liệu về các loài chim ở Minnesota. Bạn đã phát hiện một số dữ liệu sai lệch bằng cách trực quan hóa các giá trị ngoại lai và xem xét sự khác biệt giữa các loại chim dựa trên chiều dài tối đa của chúng.

## [Câu hỏi trước bài học](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/18)
## Khám phá bộ dữ liệu về các loài chim

Một cách khác để tìm hiểu dữ liệu là xem xét phân bố của nó, hoặc cách dữ liệu được tổ chức dọc theo một trục. Ví dụ, có thể bạn muốn tìm hiểu về phân bố chung, đối với bộ dữ liệu này, của sải cánh tối đa hoặc khối lượng cơ thể tối đa của các loài chim ở Minnesota.

Hãy khám phá một số thông tin về phân bố dữ liệu trong bộ dữ liệu này. Trong tệp _notebook.ipynb_ ở thư mục gốc của bài học này, hãy nhập Pandas, Matplotlib và dữ liệu của bạn:

```python
import pandas as pd
import matplotlib.pyplot as plt
birds = pd.read_csv('../../data/birds.csv')
birds.head()
```

|      | Tên                          | Tên khoa học           | Loại                  | Bộ           | Họ       | Chi         | Tình trạng bảo tồn | Chiều dài tối thiểu | Chiều dài tối đa | Khối lượng cơ thể tối thiểu | Khối lượng cơ thể tối đa | Sải cánh tối thiểu | Sải cánh tối đa |
| ---: | :--------------------------- | :--------------------- | :-------------------- | :----------- | :------- | :---------- | :----------------- | ------------------: | ----------------: | --------------------------: | --------------------------: | ------------------: | ------------------: |
|    0 | Vịt huýt sáo bụng đen        | Dendrocygna autumnalis | Vịt/Ngan/Chim nước    | Anseriformes | Anatidae | Dendrocygna | LC                 |                  47 |                  56 |                       652 |                       1020 |                  76 |                  94 |
|    1 | Vịt huýt sáo nâu             | Dendrocygna bicolor    | Vịt/Ngan/Chim nước    | Anseriformes | Anatidae | Dendrocygna | LC                 |                  45 |                  53 |                       712 |                       1050 |                  85 |                  93 |
|    2 | Ngỗng tuyết                  | Anser caerulescens     | Vịt/Ngan/Chim nước    | Anseriformes | Anatidae | Anser       | LC                 |                  64 |                  79 |                      2050 |                      4050 |                 135 |                 165 |
|    3 | Ngỗng Ross                   | Anser rossii           | Vịt/Ngan/Chim nước    | Anseriformes | Anatidae | Anser       | LC                 |                57.3 |                  64 |                      1066 |                      1567 |                 113 |                 116 |
|    4 | Ngỗng trắng lớn              | Anser albifrons        | Vịt/Ngan/Chim nước    | Anseriformes | Anatidae | Anser       | LC                 |                  64 |                  81 |                      1930 |                      3310 |                 130 |                 165 |

Nhìn chung, bạn có thể nhanh chóng xem cách dữ liệu được phân bố bằng cách sử dụng biểu đồ phân tán như chúng ta đã làm trong bài học trước:

```python
birds.plot(kind='scatter',x='MaxLength',y='Order',figsize=(12,8))

plt.title('Max Length per Order')
plt.ylabel('Order')
plt.xlabel('Max Length')

plt.show()
```
![chiều dài tối đa theo bộ](../../../../translated_images/scatter-wb.9d98b0ed7f0388af979441853361a11df5f518f5307938a503ca7913e986111b.vi.png)

Điều này cung cấp một cái nhìn tổng quan về phân bố chiều dài cơ thể theo bộ của chim, nhưng đây không phải là cách tối ưu để hiển thị phân bố thực sự. Nhiệm vụ này thường được thực hiện bằng cách tạo biểu đồ Histogram.

## Làm việc với biểu đồ Histogram

Matplotlib cung cấp các cách rất tốt để trực quan hóa phân bố dữ liệu bằng biểu đồ Histogram. Loại biểu đồ này giống như biểu đồ cột, nơi phân bố có thể được nhìn thấy qua sự tăng giảm của các cột. Để tạo một biểu đồ Histogram, bạn cần dữ liệu số. Để tạo một biểu đồ Histogram, bạn có thể vẽ biểu đồ bằng cách định nghĩa loại là 'hist' cho Histogram. Biểu đồ này hiển thị phân bố của MaxBodyMass cho toàn bộ phạm vi dữ liệu số của bộ dữ liệu. Bằng cách chia mảng dữ liệu được cung cấp thành các nhóm nhỏ hơn, nó có thể hiển thị phân bố các giá trị của dữ liệu:

```python
birds['MaxBodyMass'].plot(kind = 'hist', bins = 10, figsize = (12,12))
plt.show()
```
![phân bố trên toàn bộ bộ dữ liệu](../../../../translated_images/dist1-wb.0d0cac82e2974fbbec635826fefead401af795f82e2279e2e2678bf2c117d827.vi.png)

Như bạn có thể thấy, hầu hết hơn 400 loài chim trong bộ dữ liệu này nằm trong phạm vi dưới 2000 cho khối lượng cơ thể tối đa của chúng. Tìm hiểu thêm về dữ liệu bằng cách thay đổi tham số `bins` thành một số lớn hơn, chẳng hạn như 30:

```python
birds['MaxBodyMass'].plot(kind = 'hist', bins = 30, figsize = (12,12))
plt.show()
```
![phân bố trên toàn bộ bộ dữ liệu với tham số bins lớn hơn](../../../../translated_images/dist2-wb.2c0a7a3499b2fbf561e9f93b69f265dfc538dc78f6de15088ba84a88152e26ba.vi.png)

Biểu đồ này hiển thị phân bố chi tiết hơn một chút. Một biểu đồ ít lệch về bên trái hơn có thể được tạo bằng cách đảm bảo rằng bạn chỉ chọn dữ liệu trong một phạm vi nhất định:

Lọc dữ liệu của bạn để chỉ lấy những loài chim có khối lượng cơ thể dưới 60 và hiển thị 40 `bins`:

```python
filteredBirds = birds[(birds['MaxBodyMass'] > 1) & (birds['MaxBodyMass'] < 60)]      
filteredBirds['MaxBodyMass'].plot(kind = 'hist',bins = 40,figsize = (12,12))
plt.show()     
```
![biểu đồ histogram đã lọc](../../../../translated_images/dist3-wb.64b88db7f9780200bd486a2c2a3252548dd439672dbd3f778193db7f654b100c.vi.png)

✅ Thử một số bộ lọc và điểm dữ liệu khác. Để xem toàn bộ phân bố của dữ liệu, hãy loại bỏ bộ lọc `['MaxBodyMass']` để hiển thị các phân bố được gắn nhãn.

Biểu đồ Histogram cung cấp một số cải tiến về màu sắc và nhãn mà bạn có thể thử:

Tạo một biểu đồ Histogram 2D để so sánh mối quan hệ giữa hai phân bố. Hãy so sánh `MaxBodyMass` và `MaxLength`. Matplotlib cung cấp một cách tích hợp để hiển thị sự hội tụ bằng cách sử dụng màu sắc sáng hơn:

```python
x = filteredBirds['MaxBodyMass']
y = filteredBirds['MaxLength']

fig, ax = plt.subplots(tight_layout=True)
hist = ax.hist2d(x, y)
```
Có vẻ như có một mối tương quan dự kiến giữa hai yếu tố này dọc theo một trục dự kiến, với một điểm hội tụ đặc biệt mạnh:

![biểu đồ 2D](../../../../translated_images/2D-wb.ae22fdd33936507a41e3af22e11e4903b04a9be973b23a4e05214efaccfd66c8.vi.png)

Biểu đồ Histogram hoạt động tốt theo mặc định cho dữ liệu số. Vậy nếu bạn cần xem phân bố theo dữ liệu văn bản thì sao? 
## Khám phá bộ dữ liệu để tìm phân bố theo dữ liệu văn bản 

Bộ dữ liệu này cũng bao gồm thông tin tốt về loại chim và chi, loài, họ cũng như tình trạng bảo tồn của chúng. Hãy tìm hiểu thông tin bảo tồn này. Phân bố của các loài chim theo tình trạng bảo tồn của chúng là gì?

> ✅ Trong bộ dữ liệu, một số từ viết tắt được sử dụng để mô tả tình trạng bảo tồn. Những từ viết tắt này đến từ [Danh mục Đỏ của IUCN](https://www.iucnredlist.org), một tổ chức chuyên lập danh mục tình trạng của các loài.
> 
> - CR: Cực kỳ nguy cấp
> - EN: Nguy cấp
> - EX: Tuyệt chủng
> - LC: Ít quan tâm
> - NT: Gần bị đe dọa
> - VU: Dễ tổn thương

Đây là các giá trị dựa trên văn bản, vì vậy bạn sẽ cần thực hiện một chuyển đổi để tạo biểu đồ Histogram. Sử dụng dataframe filteredBirds, hiển thị tình trạng bảo tồn của nó cùng với sải cánh tối thiểu. Bạn thấy gì?

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

![sải cánh và sự phân loại bảo tồn](../../../../translated_images/histogram-conservation-wb.3c40450eb072c14de7a1a3ec5c0fcba4995531024760741b392911b567fd8b70.vi.png)

Dường như không có mối tương quan tốt giữa sải cánh tối thiểu và tình trạng bảo tồn. Thử nghiệm các yếu tố khác của bộ dữ liệu bằng phương pháp này. Bạn có thể thử các bộ lọc khác nhau. Bạn có tìm thấy mối tương quan nào không?

## Biểu đồ mật độ

Bạn có thể đã nhận thấy rằng các biểu đồ Histogram mà chúng ta đã xem xét cho đến nay có dạng 'bậc thang' và không trôi chảy mượt mà theo một vòng cung. Để hiển thị biểu đồ mật độ mượt mà hơn, bạn có thể thử biểu đồ mật độ.

Để làm việc với biểu đồ mật độ, hãy làm quen với một thư viện vẽ biểu đồ mới, [Seaborn](https://seaborn.pydata.org/generated/seaborn.kdeplot.html). 

Tải Seaborn, thử một biểu đồ mật độ cơ bản:

```python
import seaborn as sns
import matplotlib.pyplot as plt
sns.kdeplot(filteredBirds['MinWingspan'])
plt.show()
```
![Biểu đồ mật độ](../../../../translated_images/density1.8801043bd4af2567b0f706332b5853c7614e5e4b81b457acc27eb4e092a65cbd.vi.png)

Bạn có thể thấy cách biểu đồ phản ánh biểu đồ trước đó về dữ liệu sải cánh tối thiểu; nó chỉ mượt mà hơn một chút. Theo tài liệu của Seaborn, "So với biểu đồ Histogram, KDE có thể tạo ra một biểu đồ ít lộn xộn và dễ hiểu hơn, đặc biệt khi vẽ nhiều phân bố. Nhưng nó có khả năng gây ra biến dạng nếu phân bố cơ bản bị giới hạn hoặc không mượt mà. Giống như biểu đồ Histogram, chất lượng của biểu diễn cũng phụ thuộc vào việc chọn các tham số làm mịn tốt." [nguồn](https://seaborn.pydata.org/generated/seaborn.kdeplot.html) Nói cách khác, các giá trị ngoại lai như mọi khi sẽ làm cho biểu đồ của bạn hoạt động không đúng.

Nếu bạn muốn xem lại đường MaxBodyMass gập ghềnh trong biểu đồ thứ hai mà bạn đã tạo, bạn có thể làm mượt nó rất tốt bằng cách tạo lại nó bằng phương pháp này:

```python
sns.kdeplot(filteredBirds['MaxBodyMass'])
plt.show()
```
![đường khối lượng cơ thể mượt mà](../../../../translated_images/density2.8e7647257060ff544a1aaded57e8dd1887586bfe340139e9b77ac1e5287f7977.vi.png)

Nếu bạn muốn một đường mượt mà nhưng không quá mượt, hãy chỉnh tham số `bw_adjust`: 

```python
sns.kdeplot(filteredBirds['MaxBodyMass'], bw_adjust=.2)
plt.show()
```
![đường khối lượng cơ thể ít mượt hơn](../../../../translated_images/density3.84ae27da82f31e6b83ad977646f029a1d21186574d7581facd70123b3eb257ee.vi.png)

✅ Đọc về các tham số có sẵn cho loại biểu đồ này và thử nghiệm!

Loại biểu đồ này cung cấp các hình ảnh trực quan giải thích rất đẹp. Với một vài dòng mã, ví dụ, bạn có thể hiển thị mật độ khối lượng cơ thể tối đa theo bộ của chim:

```python
sns.kdeplot(
   data=filteredBirds, x="MaxBodyMass", hue="Order",
   fill=True, common_norm=False, palette="crest",
   alpha=.5, linewidth=0,
)
```

![khối lượng cơ thể theo bộ](../../../../translated_images/density4.e9d6c033f15c500fd33df94cb592b9f5cf1ed2a3d213c448a3f9e97ba39573ce.vi.png)

Bạn cũng có thể ánh xạ mật độ của nhiều biến trong một biểu đồ. Thử nghiệm chiều dài tối đa và chiều dài tối thiểu của chim so với tình trạng bảo tồn của chúng:

```python
sns.kdeplot(data=filteredBirds, x="MinLength", y="MaxLength", hue="ConservationStatus")
```

![nhiều mật độ, chồng lên nhau](../../../../translated_images/multi.56548caa9eae8d0fd9012a8586295538c7f4f426e2abc714ba070e2e4b1fc2c1.vi.png)

Có lẽ đáng để nghiên cứu xem cụm chim 'Dễ tổn thương' theo chiều dài của chúng có ý nghĩa hay không.

## 🚀 Thử thách

Biểu đồ Histogram là một loại biểu đồ tinh vi hơn so với biểu đồ phân tán, biểu đồ cột hoặc biểu đồ đường cơ bản. Hãy tìm kiếm trên internet để tìm các ví dụ tốt về việc sử dụng biểu đồ Histogram. Chúng được sử dụng như thế nào, chúng thể hiện điều gì, và trong các lĩnh vực hoặc lĩnh vực nghiên cứu nào chúng thường được sử dụng?

## [Câu hỏi sau bài học](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/19)

## Ôn tập & Tự học

Trong bài học này, bạn đã sử dụng Matplotlib và bắt đầu làm việc với Seaborn để hiển thị các biểu đồ tinh vi hơn. Hãy nghiên cứu về `kdeplot` trong Seaborn, một "đường mật độ xác suất liên tục trong một hoặc nhiều chiều". Đọc qua [tài liệu](https://seaborn.pydata.org/generated/seaborn.kdeplot.html) để hiểu cách nó hoạt động.

## Bài tập

[Áp dụng kỹ năng của bạn](assignment.md)

---

**Tuyên bố miễn trừ trách nhiệm**:  
Tài liệu này đã được dịch bằng dịch vụ dịch thuật AI [Co-op Translator](https://github.com/Azure/co-op-translator). Mặc dù chúng tôi cố gắng đảm bảo độ chính xác, xin lưu ý rằng các bản dịch tự động có thể chứa lỗi hoặc không chính xác. Tài liệu gốc bằng ngôn ngữ bản địa nên được coi là nguồn thông tin chính thức. Đối với các thông tin quan trọng, khuyến nghị sử dụng dịch vụ dịch thuật chuyên nghiệp từ con người. Chúng tôi không chịu trách nhiệm về bất kỳ sự hiểu lầm hoặc diễn giải sai nào phát sinh từ việc sử dụng bản dịch này.