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

**Creating new computable columns**. We can easily create new computable columns for our DataFrame by using intuitive expression like this:
```python
df['DivA'] = df['A']-df['A'].mean() 
``` 
This example calculates divergence of A from its mean value. What actually happens here is we are computing a series, and then assigning this series to the left-hand-side, creating another column. Thus, we cannot use any operations that are not compatible with series, for example, the code below is wrong:
```python
# Wrong code -> df['ADescr'] = "Low" if df['A'] < 5 else "Hi"
df['LenB'] = len(df['B']) # <- Wrong result
``` 
The latter example, while being syntactically correct, gives us wrong result, because it assigns the length of series `B` to all values in the column, and not the length of individual elements as we intended.

If we need to compute complex expressions like this, we can use `apply` function. The last example can be written as follows:
```python
df['LenB'] = df['B'].apply(lambda x : len(x))
# or 
df['LenB'] = df['B'].apply(len)
```

After operations above, we will end up with the following DataFrame:

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

**Selecting rows based on numbers** can be done using `iloc` construct. For example, to select first 5 rows from the DataFrame:
```python
df.iloc[:5]
```

**Grouping** is often used to get a result similar to *pivot tables* in Excel. Suppose that we want to compute mean value of column `A` for each given number of `LenB`. Then we can group our DataFrame by `LenB`, and call `mean`:
```python
df.groupby(by='LenB').mean()
```
If we need to compute mean and the number of elements in the group, then we can use more complex `aggregate` function:
```python
df.groupby(by='LenB') \
 .aggregate({ 'DivA' : len, 'A' : lambda x: x.mean() }) \
 .rename(columns={ 'DivA' : 'Count', 'A' : 'Mean'})
```
This gives us the following table:

| LenB | Count | Mean     |
| ---- | ----- | -------- |
| 1    | 1     | 1.000000 |
| 2    | 1     | 3.000000 |
| 3    | 2     | 5.000000 |
| 4    | 3     | 6.333333 |
| 6    | 2     | 6.000000 |

### Getting Data

We have seen how easy it is to construct Series and DataFrames from Python objects. However, data usually comes in the form of a text file, or an Excel table. Luckily, Pandas offers us a simple way to load data from disk. For example, reading CSV file is as simple as this:
```python
df = pd.read_csv('file.csv')
```
We will see more examples of loading data, including fetching it from external web sites, in the "Challenge" section


### Printing and Plotting

A Data Scientist often has to explore the data, thus it is important to be able to visualize it. When DataFrame is big, many times we want just to make sure we are doing everything correctly by printing out the first few rows. This can be done by calling `df.head()`. If you are running it from Jupyter Notebook, it will print out the DataFrame in a nice tabular form.

We have also seen the usage of `plot` function to visualize some columns. While `plot` is very useful for many tasks, and supports many different graph types via `kind=` parameter, you can always use raw `matplotlib` library to plot something more complex. We will cover data visualization in detail in separate course lessons.

This overview covers most important concepts of Pandas, however, the library is very rich, and there is no limit to what you can do with it! Let's now apply this knowledge for solving specific problem.

## 🚀 Challenge 1: Analyzing COVID Spread

First problem we will focus on is modelling of epidemic spread of COVID-19. In order to do that, we will use the data on the number of infected individuals in different countries, provided by the [Center for Systems Science and Engineering](https://systems.jhu.edu/) (CSSE) at [Johns Hopkins University](https://jhu.edu/). Dataset is available in [this GitHub Repository](https://github.com/CSSEGISandData/COVID-19).

Since we want to demonstrate how to deal with data, we invite you to open [`notebook-covidspread.ipynb`](notebook-covidspread.ipynb) and read it from top to bottom. You can also execute cells, and do some challenges that we have left for you at the end.

![COVID Spread](images/covidspread.png)

> If you do not know how to run code in Jupyter Notebook, have a look at [this article](https://soshnikov.com/education/how-to-execute-notebooks-from-github/).

## Working with Unstructured Data

While data very often comes in tabular form, in some cases we need to deal with less structured data, for example, text or images. In this case, to apply data processing techniques we have seen above, we need to somehow **extract** structured data. Here are a few examples:

* Extracting keywords from text, and seeing how often those keywords appear
* Using neural networks to extract information about objects on the picture
* Getting information on emotions of people on video camera feed

## 🚀 Challenge 2: Analyzing COVID Papers

In this challenge, we will continue with the topic of COVID pandemic, and focus on processing scientific papers on the subject. There is [CORD-19 Dataset](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge) with more than 7000 (at the time of writing) papers on COVID, available with metadata and abstracts (and for about half of them there is also full text provided).

A full example of analyzing this dataset using [Text Analytics for Health](https://docs.microsoft.com/azure/cognitive-services/text-analytics/how-tos/text-analytics-for-health/?WT.mc_id=academic-77958-bethanycheum) cognitive service is described [in this blog post](https://soshnikov.com/science/analyzing-medical-papers-with-azure-and-text-analytics-for-health/). We will discuss simplified version of this analysis.

> **NOTE**: We do not provide a copy of the dataset as part of this repository. You may first need to download the [`metadata.csv`](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge?select=metadata.csv) file from [this dataset on Kaggle](https://www.kaggle.com/allen-institute-for-ai/CORD-19-research-challenge). Registration with Kaggle may be required. You may also download the dataset without registration [from here](https://ai2-semanticscholar-cord-19.s3-us-west-2.amazonaws.com/historical_releases.html), but it will include all full texts in addition to metadata file.

Open [`notebook-papers.ipynb`](notebook-papers.ipynb) and read it from top to bottom. You can also execute cells, and do some challenges that we have left for you at the end.

![Covid Medical Treatment](images/covidtreat.png)

## Processing Image Data

Recently, very powerful AI models have been developed that allow us to understand images. There are many tasks that can be solved using pre-trained neural networks, or cloud services. Some examples include:

* **Image Classification**, which can help you categorize the image into one of the pre-defined classes. You can easily train your own image classifiers using services such as [Custom Vision](https://azure.microsoft.com/services/cognitive-services/custom-vision-service/?WT.mc_id=academic-77958-bethanycheum)
* **Object Detection** to detect different objects in the image. Services such as [computer vision](https://azure.microsoft.com/services/cognitive-services/computer-vision/?WT.mc_id=academic-77958-bethanycheum) can detect a number of common objects, and you can train [Custom Vision](https://azure.microsoft.com/services/cognitive-services/custom-vision-service/?WT.mc_id=academic-77958-bethanycheum) model to detect some specific objects of interest.
* **Face Detection**, including Age, Gender and Emotion detection. This can be done via [Face API](https://azure.microsoft.com/services/cognitive-services/face/?WT.mc_id=academic-77958-bethanycheum).

All those cloud services can be called using [Python SDKs](https://docs.microsoft.com/samples/azure-samples/cognitive-services-python-sdk-samples/cognitive-services-python-sdk-samples/?WT.mc_id=academic-77958-bethanycheum), and thus can be easily incorporated into your data exploration workflow. 

Here are some examples of exploring data from Image data sources:
* In the blog post [How to Learn Data Science without Coding](https://soshnikov.com/azure/how-to-learn-data-science-without-coding/) we explore Instagram photos, trying to understand what makes people give more likes to a photo. We first extract as much information from pictures as possible using [computer vision](https://azure.microsoft.com/services/cognitive-services/computer-vision/?WT.mc_id=academic-77958-bethanycheum), and then use [Azure Machine Learning AutoML](https://docs.microsoft.com/azure/machine-learning/concept-automated-ml/?WT.mc_id=academic-77958-bethanycheum) to build interpretable model.
* In [Facial Studies Workshop](https://github.com/CloudAdvocacy/FaceStudies) we use [Face API](https://azure.microsoft.com/services/cognitive-services/face/?WT.mc_id=academic-77958-bethanycheum) to extract emotions on people on photographs from events, in order to try to understand what makes people happy. 

## Conclusion

Whether you already have structured or unstructured data, using Python you can perform all steps related to data processing and understanding. It is probably the most flexible way of data processing, and that is the reason the majority of data scientists use Python as their primary tool. Learning Python in depth is probably a good idea if you are serious about your data science journey!



## [Post-lecture quiz](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/13)

## Review & Self Study

**Books**
* [Wes McKinney. Python for Data Analysis: Data Wrangling with Pandas, NumPy, and IPython](https://www.amazon.com/gp/product/1491957662)

**Online Resources**
* Official [10 minutes to Pandas](https://pandas.pydata.org/pandas-docs/stable/user_guide/10min.html) tutorial
* [Documentation on Pandas Visualization](https://pandas.pydata.org/pandas-docs/stable/user_guide/visualization.html)

**Learning Python**
* [Learn Python in a Fun Way with Turtle Graphics and Fractals](https://github.com/shwars/pycourse)
* [Take your First Steps with Python](https://docs.microsoft.com/learn/paths/python-first-steps/?WT.mc_id=academic-77958-bethanycheum) Learning Path on [Microsoft Learn](http://learn.microsoft.com/?WT.mc_id=academic-77958-bethanycheum)

## Assignment

[Perform more detailed data study for the challenges above](assignment.md)

## Credits

This lesson has been authored with ♥️ by [Dmitry Soshnikov](http://soshnikov.com)
