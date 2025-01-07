# Data Preparation - Chuẩn bị dữ liệu

![ Sketchnote by [(@sketchthedocs)](https://sketchthedocs.dev)](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/sketchnotes/08-DataPreparation.png)
|:---:|
|Data Preparation - _Sketchnote by [@nitya](https://twitter.com/nitya)_ |

## [Pre-Lecture Quiz](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/14)

Tùy thuộc vào nguồn, dữ liệu thô có thể chứa một số điểm không nhất quán gây ra khó khăn trong phân tích và mô hình hóa. Nói cách khác, dữ liệu này có thể được phân loại là thô, chưa qua xử lý và cần được "làm sạch". Bài học này tập trung vào các kỹ thuật làm sạch và chuyển đổi dữ liệu để xử lý các thách thức về dữ liệu bị thiếu, không chính xác hoặc không đầy đủ. Các chủ đề được đề cập trong bài học này sẽ sử dụng Python và thư viện Pandas và sẽ được minh họa trong [notebook](notebook.ipynb).

## The importance of cleaning data - Tầm quan trọng của làm sạch dữ liệu

* **Dễ sử dụng và tái sử dụng:** Khi dữ liệu được tổ chức và chuẩn hóa hợp lý, việc tìm kiếm, sử dụng và chia sẻ với người khác sẽ dễ dàng hơn.

* **Tính nhất quán:** Khoa học dữ liệu thường đòi hỏi phải làm việc với nhiều hơn một tập dữ liệu, trong đó các tập dữ liệu từ nhiều nguồn khác nhau cần được kết hợp với nhau. Đảm bảo rằng mỗi tập dữ liệu riêng lẻ có chuẩn hóa chung sẽ đảm bảo rằng dữ liệu vẫn hữu ích khi tất cả chúng được hợp nhất thành một tập dữ liệu.

* **Độ chính xác của mô hình:** Dữ liệu đã được làm sạch sẽ cải thiện độ chính xác của các mô hình dựa vào nó.

## Common cleaning goals and strategies - Mục tiêu và chiến lược chung

- **Tìm hiểu sơ bộ về dữ liệu - Exploring**: Khám phá dữ liệu, sẽ được đề cập chi tiết trong [bài học 15-Analyzing](https://github.com/microsoft/Data-Science-For-Beginners/tree/main/4-Data-Science-Lifecycle/15-analyzing) có thể giúp bạn khám phá dữ liệu cần được dọn dẹp. Quan sát trực quan các giá trị trong một tập dữ liệu có thể thiết lập kỳ vọng về phần còn lại của tập dữ liệu sẽ trông như thế nào hoặc cung cấp ý tưởng về các vấn đề có thể được giải quyết. Quá trình khám phá/tìm hiểu sơ bộ bao gồm truy vấn cơ bản, trực quan hóa và lấy mẫu.

-  **Định dạng - Formatting**: Tùy thuộc vào nguồn, dữ liệu có thể không nhất quán về cách trình bày. Điều này có thể gây ra sự cố khi tìm kiếm và biểu diễn giá trị, khi giá trị được nhìn thấy trong tập dữ liệu nhưng không được biểu diễn đúng trong hình ảnh trực quan hoặc kết quả truy vấn. Các sự cố định dạng phổ biến liên quan đến việc giải quyết khoảng trắng, ngày tháng và kiểu dữ liệu. Việc giải quyết các vấn đề định dạng thường tùy thuộc vào những người sử dụng dữ liệu. Ví dụ, các tiêu chuẩn về cách trình bày ngày tháng và số liệu có thể khác nhau tùy theo quốc gia.

-  **Trùng lặp - Duplications**: Dữ liệu có nhiều hơn một lần xuất hiện có thể tạo ra kết quả không chính xác và thường phải được loại bỏ. Đây có thể là một sự cố thường gặp khi kết hợp hai hoặc nhiều tập dữ liệu với nhau. Tuy nhiên, có những trường hợp trùng lặp trong các tập dữ liệu đã kết hợp chứa các phần có thể cung cấp thông tin bổ sung và có thể cần được bảo toàn.

- **Thiếu dữ liệu - Missing Data**: Dữ liệu bị thiếu có thể gây ra sự không chính xác cũng như kết quả yếu hoặc sai lệch. Đôi khi, những điều này có thể được giải quyết bằng cách "tải lại" dữ liệu, điền các giá trị bị thiếu bằng phép tính và mã như Python hoặc chỉ cần xóa giá trị và dữ liệu tương ứng. Có nhiều lý do khiến dữ liệu có thể bị thiếu và các hành động được thực hiện để giải quyết các giá trị bị thiếu này có thể phụ thuộc vào cách thức và lý do tại sao chúng bị thiếu ngay từ đầu. 

## Exploring DataFrame information - Khám phá thông tin của DataFrame
> **Mục tiêu học tập:** Bạn sẽ biết cách tìm kiếm thông tin chung về dữ liệu bằng thư viện `pandas` trong DataFrames.

Sau khi bạn đã tải dữ liệu của mình vào pandas, nhiều khả năng dữ liệu đó sẽ nằm trong DataFrame (tham khảo [bài 07-Python](https://github.com/microsoft/Data-Science-For-Beginners/tree/main/2-Working-With-Data/07-python#dataframe) để biết thêm chi tiết). Tuy nhiên, nếu tập dữ liệu trong DataFrame của bạn có 60.000 hàng và 400 cột, làm sao bạn có thể bắt đầu hiểu được những gì mình đang làm việc? May mắn thay, [pandas](https://pandas.pydata.org/) cung cấp một số công cụ tiện lợi để nhanh chóng xem thông tin tổng thể về DataFrame ngoài một vài hàng đầu tiên và một vài hàng cuối cùng.

Để khám phá chức năng này, chúng ta sẽ nhập thư viện `scikit-learn` của Python và sử dụng một tập dữ liệu tên là: tập dữ liệu Iris (the **Iris data set**).

```python
import pandas as pd
from sklearn.datasets import load_iris

iris = load_iris()
iris_df = pd.DataFrame(data=iris['data'], columns=iris['feature_names'])
```
|                                        |sepal length (chiều dài lá - cm)|sepal width (chiều rộng lá - cm)|petal length (chiều dài hoa - cm)|petal width (chiều rộng hoa - cm)|
|----------------------------------------|-----------------|----------------|-----------------|----------------|
|0                                       |5.1              |3.5             |1.4              |0.2             |
|1                                       |4.9              |3.0             |1.4              |0.2             |
|2                                       |4.7              |3.2             |1.3              |0.2             |
|3                                       |4.6              |3.1             |1.5              |0.2             |
|4                                       |5.0              |3.6             |1.4              |0.2             |

- **DataFrame.info**: Để bắt đầu, hàm `info()` thường được sử dụng để xem tóm tắt nội dung có trong DataFrame. Hãy cùng xem tập dữ liệu này để xem chúng ta có gì:
```python
iris_df.info()
```
```
RangeIndex: 150 entries, 0 to 149
Data columns (total 4 columns):
 #   Column             Non-Null Count  Dtype  
---  ------             --------------  -----  
 0   sepal length (cm)  150 non-null    float64
 1   sepal width (cm)   150 non-null    float64
 2   petal length (cm)  150 non-null    float64
 3   petal width (cm)   150 non-null    float64
dtypes: float64(4)
memory usage: 4.8 KB
```
Từ đó, chúng ta biết rằng tập dữ liệu Iris có 150 mục trong bốn cột không có mục nào rỗng. Tất cả dữ liệu được lưu trữ dưới dạng số dấu phẩy động 64 bit.

- **DataFrame.head()**: Tiếp theo, để kiểm tra nội dung thực tế của DataFrame, chúng ta sử dụng hàm `head()`. Hãy xem 5 hàng đầu tiên của `iris_df` trông như thế nào:
```python
iris_df.head()
```
```
   sepal length (cm)  sepal width (cm)  petal length (cm)  petal width (cm)
0                5.1               3.5                1.4               0.2
1                4.9               3.0                1.4               0.2
2                4.7               3.2                1.3               0.2
3                4.6               3.1                1.5               0.2
4                5.0               3.6                1.4               0.2
```
- **DataFrame.tail()**: Ngược lại, để kiểm tra một vài hàng cuối cùng của DataFrame, chúng ta sử dụng hàm `tail()`:
```python
iris_df.tail()
```
```
     sepal length (cm)  sepal width (cm)  petal length (cm)  petal width (cm)
145                6.7               3.0                5.2               2.3
146                6.3               2.5                5.0               1.9
147                6.5               3.0                5.2               2.0
148                6.2               3.4                5.4               2.3
149                5.9               3.0                5.1               1.8
```
> **Takeaway - Điểm mấu chốt:** Thậm chí chỉ cần xem siêu dữ liệu về thông tin trong DataFrame hoặc giá trị đầu tiên và cuối cùng trong một DataFrame, bạn có thể biết ngay kích thước, hình dạng và nội dung của dữ liệu bạn đang xử lý.

## Dealing with Missing Data - Xử lý dữ liệu bị thiếu
> **Mục tiêu học tập:** Bạn sẽ biết cách thay thế hoặc xóa giá trị null ra khỏi DataFrame.

Hầu hết các tập dữ liệu bạn làm việc sau này đều có các giá trị bị thiếu. Cách xử lý dữ liệu bị thiếu mang theo những sự đánh đổi có thể ảnh hưởng đến phân tích cuối cùng và kết quả thực tế của bạn.

Pandas xử lý các giá trị bị thiếu theo hai cách. Cách đầu tiên bạn đã thấy trong các phần trước: `NaN` (Not a number). Đây thực ra là một giá trị đặc biệt nằm trong thông số kỹ thuật số dấu phẩy động IEEE và chỉ được sử dụng để chỉ ra các giá trị số phẩy động bị thiếu (hiểu đơn giản là nhẫm lẫn giữa dấu . và , dẫn đến một giá trị không phải ở định dạng số).

Ngoài các giá trị là số fload, pandas sử dụng xử lý theo cách 2 gọi là `None`. Khi bạn sẽ gặp phải hai loại giá trị khác nhau về cơ bản nói lên cùng một điều, nhưng có những lý do lập trình hợp lý cho lựa chọn thiết kế này và trên thực tế, việc đi theo hướng này cho phép pandas đưa ra một sự thỏa hiệp tốt cho phần lớn các trường hợp. Bất chấp điều này, cả hai `None` và `NaN` đều có những hạn chế mà bạn cần lưu ý liên quan đến cách chúng có thể được sử dụng.

Xem thêm về `NaN` và `None` từ [notebook bài 15](https://github.com/microsoft/Data-Science-For-Beginners/blob/main/4-Data-Science-Lifecycle/15-analyzing/notebook.ipynb)!

- **Phát hiện giá trị Null**: Trong `pandas`, các hàm `isnull()` và `notnull()` là các hàm thường được dùng để phát hiện dữ liệu 'null'. Cả hai đều trả về kết quả Boolean (tức là True or False) trên dữ liệu của bạn. Chúng tôi sẽ sử dụng thư viện `numpy` để phát hiện các giá trị NaN như sau:
```python
import numpy as np

example1 = pd.Series([0, np.nan, '', None])
example1.isnull()
```
```
0    False
1     True
2    False
3     True
dtype: bool
```
Hãy xem kỹ kết quả ở trên, bạn có ngạc nhiên không? Mặc dù `0` là số học biểu thị cho sự trống rỗng, nhưng nó vẫn là **số nguyên** và `pandas` coi nó là số chứ không phải `null`. Còn '' thì khác hơn một chút, trong Phần 1 thì ' ' biểu diễn một giá trị chuỗi rỗng, nó là một chuỗi theo như định nghĩa của `pandas`.

Bây giờ, hãy đảo ngược lại và sử dụng các phương pháp này theo cách giống như bạn sẽ sử dụng chúng trong thực tế. Bạn có thể sử dụng trực tiếp hàm Boolean cho các `Series` hoặc `DataFrame`, điều này có thể hữu ích khi cố gắng làm việc với các giá trị bị thiếu (hoặc hiện tại) bị cô lập.

> **Takeaway - Điểm mấu chốt**: Cả hai hàm `isnull()` và `notnull()` đều tạo ra kết quả tương tự khi bạn sử dụng chúng trong DataFrames: chúng hiển thị kết quả và chỉ mục của các kết quả đó, điều này sẽ giúp bạn rất nhiều khi xử lý dữ liệu.

- **Dropping null values - Xóa các giá trị null**: Ngoài việc xác định các giá trị bị thiếu, `pandas` cung cấp một số hàm để xóa các giá trị `null` ra khỏi `Series` và `DataFrames`. (Đặc biệt trên các tập dữ liệu lớn, thường thì việc xóa các giá trị [N/A] (Not available) bị thiếu khỏi phân tích của bạn sẽ hiệu quả hơn là xử lý chúng theo những cách khác.) Để xem cách thực hiện, chúng ta hãy quay lại example 1 như sau:
```python
example1 = example1.dropna()
example1
```
```
0    0
2     
dtype: object
```
Lưu ý rằng điều này sẽ trông giống như đầu ra của bạn từ `example3[example3.notnull()]`. Sự khác biệt ở đây là, thay vì chỉ lập chỉ mục trên các giá trị được che dấu, hàm `dropna()` đã xóa các giá trị bị thiếu đó khỏi Series `example1`.

Vì DataFrames này có hai chiều nên chúng ta có nhiều cách để loại bỏ dữ liệu.

```python
example2 = pd.DataFrame([[1,      np.nan, 7], 
                         [2,      5,      8], 
                         [np.nan, 6,      9]])
example2
```
|      | 0 | 1 | 2 |
|------|---|---|---|
|0     |1.0|NaN|7  |
|1     |2.0|5.0|8  |
|2     |NaN|6.0|9  |

Bạn có thể thấy pandas có 2 cột chứa NaNs là cột `0` và `1`.

Tuy nhiên bạn không thể xóa duy nhất 1 ô chứa NaN ra khỏi DataFrame, do đó bạn phải xóa toàn bộ hàng hoặc cột (tùy thuộc vào mục đích phân tích) và thư viện `pandas` cung cấp cho bạn các tùy chọn cho cả hai. Vì trong khoa học dữ liệu, các cột thường biểu diễn các biến và các hàng biểu diễn các quan sát, nên bạn thường nhiều khả năng xóa các hàng dữ liệu; mặc định trong hàm `dropna()` là xóa tất cả các hàng có chứa bất kỳ giá trị `null` nào:

```python
example2.dropna()
```
```
	0	1	2
1	2.0	5.0	8
```
Nếu cần, bạn có thể xóa cột chứa `null` thì bạn sử dụng `axis=1` để thực hiện:
```python
example2.dropna(axis='columns')
```
```
	2
0	7
1	8
2	9
```
Lưu ý rằng điều này có thể loại bỏ rất nhiều dữ liệu mà bạn có thể muốn giữ lại, đặc biệt là trong các tập dữ liệu nhỏ. Còn nếu bạn chỉ muốn loại bỏ các hàng hoặc cột chứa toàn bộ giá trị `null` thì sao? Bạn chỉ định các thiết lập đó bằng `dropna()` các tham số `how` và `thresh`.

Theo mặc định, `how='any'`(nếu bạn muốn tự kiểm tra hoặc xem phương thức có những tham số nào khác, hãy chạy `example4.dropna?` trong ô mã). Bạn cũng có thể chỉ định `how='all'`để chỉ xóa các hàng hoặc cột chứa tất cả các giá trị `null`. Hãy mở rộng ví dụ của `DataFrame` để xem điều này hoạt động như thế nào.

```python
example2[3] = np.nan
example2
```
|      |0  |1  |2  |3  |
|------|---|---|---|---|
|0     |1.0|NaN|7  |NaN|
|1     |2.0|5.0|8  |NaN|
|2     |NaN|6.0|9  |NaN|

Tham số `thresh` cung cấp cho bạn khả năng kiểm soát chi tiết hơn: bạn đặt số lượng giá trị `không null` mà một hàng hoặc cột cần có để được giữ lại, trong ví dụ này là giữ lại cột 3:
```python
example2.dropna(axis='rows', thresh=3)
```
```
	0	1	2	3
1	2.0	5.0	8	NaN
```
Ở đây, hàng đầu tiên và hàng cuối cùng đã bị loại bỏ vì chúng chỉ chứa hai giá trị không null.

- **Filling null values - Điền giá trị null**: Tùy thuộc vào tập dữ liệu của bạn, đôi khi có thể hợp lý hơn khi điền giá trị `null` bằng giá trị hợp lệ thay vì xóa chúng. Bạn có thể sử dụng `isnull()` để thực hiện việc này tại chỗ, nhưng điều đó có thể tốn nhiều công sức, đặc biệt là nếu bạn có nhiều giá trị cần điền. Vì đây là một tác vụ phổ biến trong khoa học dữ liệu, `pandas` cung cấp hàm `fillna()`, trả về một bản sao của `Series` hoặc `DataFrame` với các giá trị bị thiếu được thay thế bằng một trong những giá trị bạn chọn. Hãy tạo một ví dụ khác để xem cách thức hoạt động của nó trong thực tế.
```python
example3 = pd.Series([1, np.nan, 2, None, 3], index=list('abcde'))
example3
```
```
a    1.0
b    NaN
c    2.0
d    NaN
e    3.0
dtype: float64
```
Bạn có thể điền tất cả các mục `null` bằng một giá trị cụ thể, chẳng hạn như `0`:
```python
example3.fillna(0)
```
```
a    1.0
b    0.0
c    2.0
d    0.0
e    3.0
dtype: float64
```
Bạn có thể dùng phương thức `ffill` **(foward-fill)** để điền tất cả các mục `null` bằng các giá trị hợp lệ theo trình tự tăng dần, ví dụ là `1` rồi đến `2`:
```python
example3.fillna(method='ffill')
```
```
a    1.0
b    1.0
c    2.0
d    2.0
e    3.0
dtype: float64
```
Hoặc bạn có thể dùng phương thức `bfill` **(back-fill)** để điền tất cả các mục `null` bằng các giá trị hợp lệ theo trình tự giảm dần, ví dụ là `3` đến `2` rồi đến `1`:
```python
example3.fillna(method='bfill')
```
```
a    1.0
b    2.0
c    2.0
d    3.0
e    3.0
dtype: float64
```
Như bạn có thể đoán, điều này cũng hoạt động tương tự với `DataFrames`, nhưng bạn cũng có thể chỉ định một giá trị `axis` để điền vào các giá trị `null`. Lấy ví dụ trong `example2`, cột cần điền là cột 1, giá trị NaN ở dòng `0` được thay thế bằng giá trị '1' theo phương thức `ffill`:
```python
example2.fillna(method='ffill', axis=1)
```
```
	0	1	2	3
0	1.0	1.0	7.0	NaN
1	2.0	5.0	8.0	NaN
2	NaN	6.0	9.0	NaN
```
Lưu ý rằng khi giá trị trước đó không có sẵn để điền tiếp thì giá trị null vẫn giữ nguyên.

> **Takeaway - Điểm mấu chốt:** Có nhiều cách để xử lý các giá trị bị thiếu trong tập dữ liệu của bạn. Chiến lược cụ thể mà bạn sử dụng (xóa, thay thế hoặc thậm chí cách bạn thay thế) nên được quyết định bởi các chi tiết của dữ liệu đó. Bạn sẽ phát triển ý thức tốt hơn về cách xử lý các giá trị bị thiếu khi bạn xử lý và tương tác với tập dữ liệu nhiều hơn.

## Removing duplicate data - Xóa dữ liệu trùng

> **Mục tiêu:** Bạn sẽ biết cách xác định và loại bỏ các giá trị trùng lặp khỏi DataFrame.

Ngoài dữ liệu bị thiếu, bạn thường gặp dữ liệu trùng lặp trong các tập dữ liệu thực tế. May mắn thay, `pandas` cung cấp một phương tiện dễ dàng để phát hiện và loại bỏ các mục trùng lặp.

- **Identifying duplicates - Phát hiện trùng lặp**: Bạn có thể dễ dàng phát hiện các giá trị trùng lặp bằng hàm `duplicated()` trong pandas, hàm này trả về giá trị Boolean Y/N cho biết liệu một mục trong `DataFrame` có trùng lặp với mục trước đó (ở trong cùng 1 cột) hay không. Hãy tạo một ví dụ khác để xem điều này hoạt động như thế nào.
```python
example4 = pd.DataFrame({'letters': ['A','B'] * 2 + ['B'],
                         'numbers': [1, 2, 1, 3, 3]})
example4
```
|      |letters|numbers|
|------|-------|-------|
|0     |A      |1      |
|1     |B      |2      |
|2     |A      |1      |
|3     |B      |3      |
|4     |B      |3      |

```python
example4.duplicated()
```
```
0    False
1    False
2     True
3    False
4     True
dtype: bool
```
- **Dropping duplicates - Xóa dữ liệu trùng:** trả về một bản sao của dữ liệu có tất cả `duplicated` các giá trị là False:
```python
example4.drop_duplicates()
```
```
	letters	numbers
0	A	1
1	B	2
3	B	3
```
Cả hai hàm `duplicated` và `drop_duplicates` đều mặc định kiểm tra tất cả các cột bị trùng, hoặc là bạn có thể chỉ định chúng chỉ kiểm tra một cột bất kỳ trong DataFrame, ví dụ như cột `letters`:
```python
example4.drop_duplicates(['letters'])
```
```
	letters	numbers
0	A	1
1	B	2
```

> **Takeaway - Điểm mấu chốt:** Xóa dữ liệu trùng lặp là một phần thiết yếu của hầu hết mọi dự án khoa học dữ liệu. Dữ liệu trùng lặp có thể thay đổi kết quả phân tích của bạn và cung cấp cho bạn kết quả không chính xác!


## 🚀 Challenge - Thử thách

Tất cả các tài liệu được thảo luận đều được cung cấp ở [Jupyter Notebook](https://github.com/microsoft/Data-Science-For-Beginners/blob/main/2-Working-With-Data/08-data-preparation/notebook.ipynb).

## [Post-Lecture Quiz](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/15)



## Review & Self Study - Đánh giá & Tự học

Có nhiều cách để khám phá và tiếp cận việc chuẩn bị dữ liệu của bạn để phân tích và lập mô hình và việc làm sạch dữ liệu là một bước quan trọng, là trải nghiệm "thực hành". Hãy thử những thử thách này từ Kaggle để khám phá các kỹ thuật khác mà bài học này không đề cập đến.

- [Data Cleaning Challenge: Parsing Dates - Dữ liệu dạng ngày](https://www.kaggle.com/rtatman/data-cleaning-challenge-parsing-dates/)

- [Data Cleaning Challenge: Scale and Normalize Data - Mở rộng và chuẩn hóa dữ liệu](https://www.kaggle.com/rtatman/data-cleaning-challenge-scale-and-normalize-data)


## Assignment

[Evaluating Data from a Form - Đánh giá dữ liệu](https://github.com/hoanglong8/Microsoft-DS-for-beginners/blob/main/2-Working-With-Data/08-data-preparation/translations/Assignment.vn.md)
