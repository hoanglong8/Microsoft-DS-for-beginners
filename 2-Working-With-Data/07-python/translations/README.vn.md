# Working with Data: Python và thư viện Pandas, Numpy...

![Sketchnote by [(@sketchthedocs)](https://sketchthedocs.dev)](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/sketchnotes/07-WorkWithPython.png)
| :-------------------------------------------------------------------------------------------------------: |
|                 Working With Python - _Sketchnote by [@nitya](https://twitter.com/nitya)_                 |

[![Intro Video](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/07-python/images/video-ds-python.png)](https://youtu.be/dZjWOGbsN4Y)

Trong khi cơ sở dữ liệu cung cấp những cách rất hiệu quả để lưu trữ dữ liệu và truy vấn chúng bằng ngôn ngữ truy vấn, cách xử lý dữ liệu linh hoạt nhất là viết chương trình của riêng bạn để thao tác dữ liệu. Trong nhiều trường hợp, thực hiện truy vấn cơ sở dữ liệu sẽ là cách hiệu quả hơn. Tuy nhiên, trong một số trường hợp khi cần xử lý dữ liệu phức tạp hơn, không thể thực hiện dễ dàng bằng SQL. Xử lý dữ liệu có thể được lập trình bằng bất kỳ ngôn ngữ lập trình nào, nhưng có một số ngôn ngữ ở cấp độ cao hơn về mặt làm việc với dữ liệu. Các nhà khoa học dữ liệu thường thích một trong các ngôn ngữ sau:

* **[Python](https://www.python.org/)**, một ngôn ngữ lập trình đa năng, thường được coi là một trong những lựa chọn tốt nhất cho người mới bắt đầu vì tính đơn giản của nó. Python có rất nhiều thư viện bổ sung có thể giúp bạn giải quyết nhiều vấn đề thực tế, chẳng hạn như trích xuất dữ liệu từ tệp ZIP hoặc chuyển đổi hình ảnh sang thang độ xám. Ngoài khoa học dữ liệu, Python cũng thường được sử dụng để phát triển web. 
* **[R](https://www.r-project.org/)** là một hộp công cụ truyền thống được phát triển với mục đích xử lý dữ liệu thống kê. Nó cũng chứa kho thư viện lớn (CRAN), khiến nó trở thành lựa chọn tốt cho xử lý dữ liệu. Tuy nhiên, R không phải là ngôn ngữ lập trình mục đích chung và hiếm khi được sử dụng bên ngoài phạm vi khoa học dữ liệu.
* **[Julia](https://julialang.org/)** là một ngôn ngữ khác được phát triển dành riêng cho khoa học dữ liệu. Ngôn ngữ này có mục đích mang lại hiệu suất tốt hơn Python, khiến nó trở thành một công cụ tuyệt vời cho thử nghiệm khoa học.

Trong bài học này, chúng ta sẽ tập trung vào việc sử dụng Python để xử lý dữ liệu đơn giản. Chúng ta sẽ giả định rằng bạn đã quen thuộc cơ bản với ngôn ngữ này. Nếu bạn muốn tìm hiểu sâu hơn về Python, bạn có thể tham khảo một trong các tài nguyên sau:

* [Học Python theo cách thú vị với Turtle Graphics và Fractals](https://github.com/shwars/pycourse) - Khóa học giới thiệu nhanh về Lập trình Python trên GitHub
* [Take your First Steps with Python](https://docs.microsoft.com/en-us/learn/paths/python-first-steps/?WT.mc_id=academic-77958-bethanycheum) Học trên [Microsoft Learn](http://learn.microsoft.com/?WT.mc_id=academic-77958-bethanycheum)

Dữ liệu có thể có nhiều dạng. Trong bài học này, chúng ta sẽ xem xét ba dạng dữ liệu - dữ liệu **dạng bảng (tabular), văn bản và hình ảnh** .

Chúng tôi sẽ tập trung vào một số ví dụ về xử lý dữ liệu, thay vì cung cấp cho bạn tổng quan đầy đủ về tất cả các thư viện liên quan. Điều này sẽ cho phép bạn có được ý tưởng chính về những gì có thể và giúp bạn hiểu được nơi tìm giải pháp cho các vấn đề của mình khi bạn cần.

> **Most useful advice**. Khi bạn cần thực hiện một số thao tác trên dữ liệu mà bạn không biết cách thực hiện, hãy thử tìm kiếm trên internet. [Stackoverflow](https://stackoverflow.com/) thường chứa rất nhiều mẫu mã hữu ích bằng Python cho nhiều tác vụ thông thường. 



## [Pre-lecture quiz](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/12)

## Tabular Data and Dataframes (Dữ liệu dạng bảng và mảng dữ liệu)

Bạn đã gặp dữ liệu dạng bảng khi chúng ta nói về cơ sở dữ liệu quan hệ. Khi bạn có nhiều dữ liệu và dữ liệu đó được chứa trong nhiều bảng được liên kết khác nhau, thì việc sử dụng SQL để làm việc với dữ liệu đó chắc chắn là hợp lý. Tuy nhiên, có nhiều trường hợp khi chúng ta có một bảng dữ liệu và chúng ta cần có được một số **hiểu sơ** hoặc **hiểu sâu** về dữ liệu này, chẳng hạn như phân phối, tương quan giữa các giá trị, v.v. Trong khoa học dữ liệu, có rất nhiều trường hợp khi chúng ta cần thực hiện một số phép biến đổi dữ liệu gốc, sau đó là trực quan hóa. Cả hai bước đó đều có thể dễ dàng thực hiện bằng Python.

Có hai thư viện hữu ích nhất trong Python có thể giúp bạn xử lý dữ liệu dạng bảng:
* **[Pandas](https://pandas.pydata.org/)** cho phép bạn thao tác với **các Dataframes**, tương tự như các bảng dạng quan hệ SQL. Bạn có thể có các cột được đặt tên và thực hiện các thao tác khác nhau trên hàng, cột và khung dữ liệu nói chung. 
* **[Numpy](https://numpy.org/)** là một thư viện để làm việc với **các Tensors**, tức là mảng đa chiều. Mảng có các giá trị cùng kiểu cơ bản và đơn giản hơn khung dữ liệu, nhưng cung cấp nhiều phép toán hơn và tạo ra ít chi phí hơn.

Ngoài ra còn có một số thư viện khác mà bạn nên biết:
* **[Matplotlib](https://matplotlib.org/)** là một thư viện được sử dụng để trực quan hóa dữ liệu và vẽ đồ thị
* **[SciPy](https://www.scipy.org/)** là một thư viện có một số chức năng khoa học bổ sung. Chúng ta đã gặp thư viện này khi nói về xác suất và thống kê.

Sau đây là một đoạn mã mà bạn thường sử dụng để nhập các thư viện đó vào đầu chương trình Python của mình:
```python
import numpy as np
import pandas as pd
import matplotlib.pyplot as plt
from scipy import ... # you need to specify exact sub-packages that you need
``` 

Pandas tập trung vào một số khái niệm cơ bản sau:

**1.Series - Chuỗi**

**Series** là một chuỗi các giá trị, tương tự như một danh sách hoặc mảng numpy. Sự khác biệt chính là series cũng có một chỉ mục và khi chúng ta thao tác trên series (ví dụ: thêm), chỉ mục sẽ được tính đến. Index có thể đơn giản như số hàng nguyên (đây là chỉ mục được sử dụng theo mặc định khi tạo một series từ danh sách hoặc mảng) hoặc có thể có cấu trúc phức tạp, chẳng hạn như khoảng thời gian ngày.

> **Note**: Có một số mã Pandas giới thiệu trong sổ tay [`notebook.ipynb`](notebook.ipynb). Chúng tôi chỉ phác thảo một số ví dụ ở đây và bạn chắc chắn được chào đón để xem sổ tay đầy đủ.

Hãy xem xét một ví dụ: chúng ta muốn phân tích doanh số bán hàng của cửa hàng kem. Hãy tạo một loạt số liệu bán hàng (số mặt hàng được bán mỗi ngày) trong một khoảng thời gian nào đó:

```python
start_date = "Jan 1, 2020"
end_date = "Mar 31, 2020"
idx = pd.date_range(start_date,end_date)
print(f"Length of index is {len(idx)}")
items_sold = pd.Series(np.random.randint(25,50,size=len(idx)),index=idx)
items_sold.plot()
```
![Time Series Plot](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/07-python/images/timeseries-1.png)

Bây giờ giả sử rằng mỗi tuần chúng ta tổ chức một bữa tiệc cho bạn bè và chúng ta lấy thêm 10 gói kem cho bữa tiệc. Chúng ta có thể tạo một chuỗi khác, được lập chỉ mục theo tuần, để chứng minh rằng:
```python
additional_items = pd.Series(10,index=pd.date_range(start_date,end_date,freq="W"))
```
Khi chúng ta cộng hai dãy số lại với nhau, chúng ta sẽ có tổng số:
```python
total_items = items_sold.add(additional_items,fill_value=0)
total_items.plot()
```
![Time Series Plot 2](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/07-python/images/timeseries-2.png)

> **Lưu ý** chúng ta không sử dụng cú pháp đơn giản `total_items+additional_items`. Nếu chúng ta làm vậy, chúng ta sẽ nhận được rất nhiều giá trị `NaN` (Not a Number) trong chuỗi kết quả. Điều này là do có một số giá trị bị thiếu cho một số điểm chỉ mục trong `additional_items` chuỗi và việc thêm `Nan` vào bất kỳ thứ gì sẽ dẫn đến `NaN`. Do đó, chúng ta cần chỉ định `fill_value` tham số trong quá trình cộng.

Với chuỗi thời gian, chúng ta cũng có thể **lấy mẫu lại chuỗi (resample)** với các khoảng thời gian khác nhau. Ví dụ, giả sử chúng ta muốn tính khối lượng bán hàng trung bình hàng tháng. Chúng ta có thể sử dụng mã sau:
```python
monthly = total_items.resample("1M").mean()
ax = monthly.plot(kind='bar')
```
![Monthly Time Series Averages](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/07-python/images/timeseries-3.png)

### DataFrame

DataFrame về cơ bản là một tập hợp các chuỗi (Series) có cùng chỉ mục (Index). Chúng ta có thể kết hợp nhiều chuỗi lại với nhau thành một DataFrame:
```python
a = pd.Series(range(1,10))
b = pd.Series(["I","like","to","play","games","and","will","not","change"],index=range(0,9))
df = pd.DataFrame([a,b])
```
Thao tác này sẽ tạo ra một bảng nằm ngang như thế này:
|     | 0   | 1    | 2   | 3   | 4      | 5   | 6      | 7    | 8    |
| --- | --- | ---- | --- | --- | ------ | --- | ------ | ---- | ---- |
| 0   | 1   | 2    | 3   | 4   | 5      | 6   | 7      | 8    | 9    |
| 1   | I   | like | to  | use | Python | and | Pandas | very | much |

Chúng ta cũng có thể sử dụng Series làm cột và chỉ định tên cột bằng lệnh sau:
```python
df = pd.DataFrame({ 'A' : a, 'B' : b })
```
Lệnh này sẽ cho chúng ta một bảng như thế này:

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

**Lưu ý** chúng ta cũng có thể có được bố cục bảng này bằng cách chuyển vị bảng trước đó, ví dụ bằng lệnh sau:
```python
df = pd.DataFrame([a,b]).T..rename(columns={ 0 : 'A', 1 : 'B' })
```
Ở đây `.T` có nghĩa là thao tác chuyển vị DataFrame, tức là thay đổi hàng và cột, và `rename` thao tác này cho phép chúng ta đổi tên các cột để phù hợp với ví dụ trước.

Sau đây là một số thao tác quan trọng nhất mà chúng ta có thể thực hiện trên DataFrame:

**Column selection** Chúng ta có thể chọn từng cột bằng cách viết `df['A']` - thao tác này trả về một Series. Chúng ta cũng có thể chọn một tập hợp con các cột vào một DataFrame khác bằng cách viết `df[['B','A']]` - thao tác này trả về một DataFrame khác.

**Filtering** một số hàng nhất định theo tiêu chí. Ví dụ, để chỉ để lại các hàng có `cột A` lớn hơn 5, chúng ta có thể viết `df[df['A']>5]`.

> **Lưu ý:** Cách thức hoạt động của bộ lọc như sau: Biểu thức `df['A']<5` trả về một chuỗi boolean, biểu thị liệu biểu thức là `True` hay `False` cho từng phần tử của chuỗi gốc `df['A']`. Khi chuỗi boolean được sử dụng làm chỉ mục, nó trả về tập hợp con của các hàng trong DataFrame. Do đó, không thể sử dụng biểu thức boolean Python tùy ý, ví dụ, viết `df[df['A']>5 and df['A']<7]` sẽ là sai. Thay vào đó, bạn nên sử dụng `&` thao tác đặc biệt trên chuỗi boolean, viết `df[(df['A']>5) & (df['A']<7)]` (dấu ngoặc vuông rất quan trọng ở đây).

**Tạo các cột tính toán mới.** Chúng ta có thể dễ dàng tạo các cột tính toán mới cho DataFrame của mình bằng cách sử dụng biểu thức trực quan như sau:
```python
df['DivA'] = df['A']-df['A'].mean() 
``` 
Ví dụ này tính độ phân kỳ của A từ giá trị trung bình của nó. Điều thực sự xảy ra ở đây là chúng ta đang tính toán một chuỗi, sau đó gán chuỗi này cho vế trái, tạo ra một cột khác. Do đó, chúng ta không thể sử dụng bất kỳ phép toán nào không tương thích với chuỗi, ví dụ, mã bên dưới là sai:
```python
# Wrong code -> df['ADescr'] = "Low" if df['A'] < 5 else "Hi"
df['LenB'] = len(df['B']) # <- Wrong result
``` 
Ví dụ sau, mặc dù đúng về mặt cú pháp, nhưng lại cho chúng ta kết quả sai vì nó gán độ dài của chuỗi Bcho tất cả các giá trị trong cột, chứ không phải độ dài của từng phần tử như chúng ta mong muốn.

Nếu chúng ta cần tính toán các biểu thức phức tạp như thế này, chúng ta có thể sử dụng applyhàm. Ví dụ cuối cùng có thể được viết như sau:
```python
df['LenB'] = df['B'].apply(lambda x : len(x))
# or 
df['LenB'] = df['B'].apply(len)
```

Sau khi thực hiện các thao tác trên, chúng ta sẽ có được DataFrame sau:

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

**Lựa chọn hàng bất kỳ dựa trên số dòng của nó** có thể được thực hiện bằng cách sử dụng hàm `iloc`. Ví dụ, để chọn 5 hàng đầu tiên từ DataFrame:
```python
df.iloc[:5]
```

**Grouping** thường được sử dụng để có được kết quả tương tự như bảng trục trong Excel. Giả sử chúng ta muốn tính giá trị trung bình của `cột A` cho mỗi số đã cho của `LenB`. Sau đó, chúng ta có thể nhóm DataFrame của mình theo `LenB`, và gọi `mean`:
```python
df.groupby(by='LenB').mean()
```
Nếu chúng ta cần tính giá trị trung bình và số phần tử trong nhóm, thì chúng ta có thể sử dụng hàm `aggregate` phức tạp hơn:
```python
df.groupby(by='LenB') \
 .aggregate({ 'DivA' : len, 'A' : lambda x: x.mean() }) \
 .rename(columns={ 'DivA' : 'Count', 'A' : 'Mean'})
```
Lệnh này sẽ cho chúng ta bảng sau:

| LenB | Count | Mean     |
| ---- | ----- | -------- |
| 1    | 1     | 1.000000 |
| 2    | 1     | 3.000000 |
| 3    | 2     | 5.000000 |
| 4    | 3     | 6.333333 |
| 6    | 2     | 6.000000 |

### Getting Data - Đọc dữ liệu

Chúng ta đã thấy việc xây dựng Series và DataFrames từ các đối tượng Python dễ dàng như thế nào. Tuy nhiên, dữ liệu thường ở dạng tệp văn bản hoặc bảng Excel. May mắn thay, Pandas cung cấp cho chúng ta một cách đơn giản để tải dữ liệu từ đĩa. Ví dụ, đọc tệp CSV đơn giản như sau:
```python
df = pd.read_csv('file.csv')
```
Chúng ta sẽ thấy nhiều ví dụ hơn về việc tải dữ liệu, bao gồm cả việc lấy dữ liệu từ các trang web bên ngoài, trong phần "Thử thách"


### Printing (lệnh hiển thị) and Plotting (vẽ đồ thị)

Nhà khoa học dữ liệu thường phải khám phá dữ liệu, do đó, điều quan trọng là phải có khả năng trực quan hóa dữ liệu. Khi DataFrame lớn, nhiều lần chúng ta chỉ muốn đảm bảo rằng mình đang làm mọi thứ đúng bằng cách in ra một vài hàng đầu tiên. Điều này có thể được thực hiện bằng cách gọi `df.head()`. Nếu bạn đang chạy nó từ `Jupyter Notebook`, nó sẽ in ra DataFrame dưới dạng bảng đẹp mắt.

Chúng ta cũng đã thấy cách sử dụng hàm `plot` để trực quan hóa một số cột. Mặc dù `plot` rất hữu ích cho nhiều tác vụ và hỗ trợ nhiều loại biểu đồ khác nhau thông qua `kind=` tham số, bạn luôn có thể sử dụng thư viện thô `matplotlib` để vẽ thứ gì đó phức tạp hơn. Chúng tôi sẽ trình bày chi tiết về trực quan hóa dữ liệu trong các bài học riêng biệt của khóa học.

Tổng quan này bao gồm hầu hết các khái niệm quan trọng của `Pandas`, tuy nhiên, thư viện rất phong phú và không có giới hạn nào cho những gì bạn có thể làm với nó! Bây giờ chúng ta hãy áp dụng kiến ​​thức này để giải quyết vấn đề cụ thể.

## 🚀 Thử thách 1: Phân tích sự lây lan của COVID

Vấn đề đầu tiên chúng ta sẽ tập trung vào là mô hình hóa sự lây lan của dịch bệnh COVID-19. Để làm được điều đó, chúng ta sẽ sử dụng dữ liệu về số lượng cá nhân bị nhiễm bệnh ở các quốc gia khác nhau, do [Center for Systems Science and Engineering](https://systems.jhu.edu/) (CSSE) tại [Johns Hopkins University](https://jhu.edu/) cung cấp . Bộ dữ liệu có sẵn trong [this GitHub Repository](https://github.com/CSSEGISandData/COVID-19).

Vì chúng tôi muốn trình bày cách xử lý dữ liệu, chúng tôi mời bạn mở [`notebook-covidspread.ipynb`](https://github.com/hoanglong8/Microsoft-DS-for-beginners/blob/main/2-Working-With-Data/07-python/translations/02.07.notebook-covidspread.ipynb) và đọc dữ liệu từ trên xuống dưới. Bạn cũng có thể thực hiện các ô và thực hiện một số thử thách mà chúng tôi để lại cho bạn ở cuối.

![COVID Spread](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/07-python/images/covidspread.png)

> If you do not know how to run code in Jupyter Notebook, have a look at [this article](https://soshnikov.com/education/how-to-execute-notebooks-from-github/).

## Working with Unstructured Data - Làm việc với dữ liệu phi cấu trúc

Mặc dù dữ liệu thường ở dạng bảng, nhưng trong một số trường hợp, chúng ta cần xử lý dữ liệu ít có cấu trúc hơn, ví dụ như văn bản hoặc hình ảnh. Trong trường hợp này, để áp dụng các kỹ thuật xử lý dữ liệu mà chúng ta đã thấy ở trên, chúng ta cần trích xuất dữ liệu có cấu trúc theo một cách nào đó. Sau đây là một số ví dụ:

* Trích xuất các từ khóa từ văn bản và xem tần suất xuất hiện của các từ khóa đó
* Sử dụng mạng nơ-ron để trích xuất thông tin về các đối tượng trên hình ảnh
* Nhận thông tin về cảm xúc của mọi người trên nguồn cấp dữ liệu camera

## 🚀 Thử thách 2: Phân tích các bài báo về COVID

Trong thử thách này, chúng ta sẽ tiếp tục với chủ đề về đại dịch COVID và tập trung vào việc xử lý các bài báo khoa học về chủ đề này. Có [CORD-19 Dataset](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge) với hơn 7000 bài báo (tại thời điểm viết bài) về COVID, có sẵn siêu dữ liệu và tóm tắt (và đối với khoảng một nửa trong số đó cũng có toàn văn được cung cấp).

Bài đăng trên [blog này](https://soshnikov.com/science/analyzing-medical-papers-with-azure-and-text-analytics-for-health/) mô tả ví dụ đầy đủ về việc phân tích tập dữ liệu này bằng công cụ [Text Analytics for Health awareness service](https://docs.microsoft.com/azure/cognitive-services/text-analytics/how-tos/text-analytics-for-health/?WT.mc_id=academic-77958-bethanycheum) Chúng tôi sẽ thảo luận về phiên bản đơn giản hóa của phân tích này.

> **NOTE**: Chúng tôi không cung cấp bản sao của tập dữ liệu như một phần của kho lưu trữ này. Trước tiên, bạn có thể cần tải xuống tệp [`metadata.csv`](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge?select=metadata.csv) từ [this dataset on Kaggle](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge). Bạn cũng có thể tải xuống tập dữ liệu mà không cần đăng ký [from here](https://ai2-semanticscholar-cord-19.s3-us-west-2.amazonaws.com/historical_releases.html), nhưng nó sẽ bao gồm tất cả các văn bản đầy đủ ngoài tệp siêu dữ liệu metadata.

Mở [`notebook-papers.ipynb`](notebook-papers.ipynb) và đọc từ trên xuống dưới. Bạn cũng có thể thực hiện các ô và thực hiện một số thử thách mà chúng tôi để lại cho bạn ở phần cuối.

![Covid Medical Treatment](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/07-python/images/covidtreat.png)

## Processing Image Data - Xử lý dữ liệu hình ảnh

Gần đây, các mô hình AI rất mạnh mẽ đã được phát triển cho phép chúng ta hiểu hình ảnh. Có nhiều tác vụ có thể được giải quyết bằng cách sử dụng mạng nơ-ron được đào tạo trước hoặc dịch vụ đám mây. Một số ví dụ bao gồm:

* **Image Classification**, có thể giúp bạn phân loại hình ảnh thành một trong các lớp được xác định trước. Bạn có thể dễ dàng đào tạo bộ phân loại hình ảnh của riêng mình bằng các dịch vụ như [Custom Vision](https://azure.microsoft.com/services/cognitive-services/custom-vision-service/?WT.mc_id=academic-77958-bethanycheum)
* **Object Detection** để phát hiện các đối tượng khác nhau trong hình ảnh. Các dịch vụ như [computer vision](https://azure.microsoft.com/services/cognitive-services/computer-vision/?WT.mc_id=academic-77958-bethanycheum) có thể phát hiện một số đối tượng phổ biến và bạn có thể huấn luyện mô hình [Custom Vision](https://azure.microsoft.com/services/cognitive-services/custom-vision-service/?WT.mc_id=academic-77958-bethanycheum) để phát hiện một số đối tượng cụ thể cần quan tâm khác.
* **Face Detection**, bao gồm phát hiện Tuổi, Giới tính và Cảm xúc. Điều này có thể được thực hiện thông qua [Face API](https://azure.microsoft.com/services/cognitive-services/face/?WT.mc_id=academic-77958-bethanycheum).

Tất cả các dịch vụ đám mây đó có thể được gọi bằng [Python SDKs](https://docs.microsoft.com/samples/azure-samples/cognitive-services-python-sdk-samples/cognitive-services-python-sdk-samples/?WT.mc_id=academic-77958-bethanycheum), và có thể dễ dàng tích hợp vào quy trình khám phá dữ liệu của bạn.

Sau đây là một số ví dụ về việc khám phá dữ liệu từ nguồn dữ liệu Hình ảnh:
* Trong bài đăng trên blog [How to Learn Data Science without Coding](https://soshnikov.com/azure/how-to-learn-data-science-without-coding/) chúng tôi khám phá ảnh Instagram, cố gắng hiểu điều gì khiến mọi người thích ảnh nhiều hơn. Đầu tiên, chúng tôi trích xuất càng nhiều thông tin từ ảnh càng tốt bằng cách sử dụng [computer vision](https://azure.microsoft.com/services/cognitive-services/computer-vision/?WT.mc_id=academic-77958-bethanycheum), sau đó sử dụng [Azure Machine Learning AutoML](https://docs.microsoft.com/azure/machine-learning/concept-automated-ml/?WT.mc_id=academic-77958-bethanycheum) để xây dựng mô hình có thể diễn giải được.
* Trong [Facial Studies Workshop](https://github.com/CloudAdvocacy/FaceStudies) chúng tôi sử dụng [Face API](https://azure.microsoft.com/services/cognitive-services/face/?WT.mc_id=academic-77958-bethanycheum) để trích xuất cảm xúc của mọi người trên các bức ảnh chụp sự kiện, nhằm mục đích hiểu được điều gì khiến mọi người hạnh phúc.

## Conclusion - Kết luận

Cho dù bạn đã có dữ liệu có cấu trúc hay không có cấu trúc, sử dụng Python, bạn có thể thực hiện tất cả các bước liên quan đến xử lý và hiểu dữ liệu. Đây có lẽ là cách xử lý dữ liệu linh hoạt nhất và đó là lý do tại sao phần lớn các nhà khoa học dữ liệu sử dụng Python làm công cụ chính của họ. Học Python chuyên sâu có lẽ là một ý tưởng hay nếu bạn nghiêm túc với hành trình khoa học dữ liệu của mình!

## [Post-lecture quiz](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/13)

## Review & Self Study

**Books**
Cuốn sách của Wes McKinney: "Python để phân tích dữ liệu: Xử lý dữ liệu với Pandas, NumPy và IPython"
* [Wes McKinney. Python for Data Analysis: Data Wrangling with Pandas, NumPy, and IPython](https://www.amazon.com/gp/product/1491957662)

**Online Resources**
* Official [10 minutes to Pandas](https://pandas.pydata.org/pandas-docs/stable/user_guide/10min.html) tutorial
* [Documentation on Pandas Visualization](https://pandas.pydata.org/pandas-docs/stable/user_guide/visualization.html)

**Learning Python**
* [Learn Python in a Fun Way with Turtle Graphics and Fractals](https://github.com/shwars/pycourse)
* [Take your First Steps with Python](https://docs.microsoft.com/learn/paths/python-first-steps/?WT.mc_id=academic-77958-bethanycheum) Learning Path on [Microsoft Learn](http://learn.microsoft.com/?WT.mc_id=academic-77958-bethanycheum)

## Assignment

[Thực hiện nghiên cứu dữ liệu chi tiết hơn cho những thách thức trên](https://github.com/hoanglong8/Microsoft-DS-for-beginners/blob/main/2-Working-With-Data/07-python/translations/Assignment.vn.md)

## Credits

This lesson has been authored with ♥️ by [Dmitry Soshnikov](http://soshnikov.com)
