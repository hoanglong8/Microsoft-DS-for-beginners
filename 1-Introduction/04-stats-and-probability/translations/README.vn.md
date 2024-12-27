# A Brief Introduction to Statistics and Probability - Giới thiệu về Thống kê và Xác suất

![Sketchnote by [(@sketchthedocs)](https://sketchthedocs.dev) ](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/raw/main/sketchnotes/04-Statistics-Probability.png)
|:---:|
| Statistics and Probability - _Sketchnote by [@nitya](https://twitter.com/nitya)_ |

Thống kê và Lý thuyết xác suất là hai lĩnh vực liên quan chặt chẽ với nhau của Toán học và có liên quan chặt chẽ đến Khoa học dữ liệu. Có thể vận hành dữ liệu mà không cần kiến ​​thức sâu về toán học, nhưng vẫn tốt hơn nếu biết ít nhất một số khái niệm cơ bản. Sau đây chúng tôi sẽ giới thiệu một phần giới thiệu ngắn gọn giúp bạn bắt đầu.

[![Intro Video](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/blob/main/1-Introduction/04-stats-and-probability/images/video-prob-and-stats.png)](https://youtu.be/Z5Zy85g4Yjw)

## [Câu hỏi chuẩn bị trước bài giảng](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/6)

## Probability and Random Variables - Xác suất và Biến ngẫu nhiên

**Xác suất** là một con số từ 0 đến 1 thể hiện mức độ có thể xảy ra của một **sự kiện** . Xác suất được định nghĩa là số kết quả tích cực (dẫn đến sự kiện), chia cho tổng số kết quả, với điều kiện là tất cả các kết quả đều có xác suất như nhau. Ví dụ, khi chúng ta tung một con xúc xắc, xác suất chúng ta nhận được một số chẵn là 3/6 = 0,5.

Khi chúng ta nói về các sự kiện, chúng ta sử dụng các **biến ngẫu nhiên** . Ví dụ, biến ngẫu nhiên biểu diễn một số thu được khi tung xúc xắc sẽ lấy các giá trị từ 1 đến 6. Tập hợp các số từ 1 đến 6 được gọi là **không gian mẫu** . Chúng ta có thể nói về xác suất của một biến ngẫu nhiên lấy một giá trị nhất định, ví dụ P(X=3)=1/6.

Biến ngẫu nhiên trong ví dụ trước được gọi là **rời rạc** , vì nó có không gian mẫu đếm được, tức là có các giá trị riêng biệt có thể được liệt kê. Có những trường hợp khi không gian mẫu là một phạm vi các số thực hoặc toàn bộ tập hợp các số thực. Các biến như vậy được gọi là **liên tục** . Một ví dụ hay là thời gian xe buýt đến.

## Probability Distribution - Phân phối xác suất

Trong trường hợp các biến ngẫu nhiên rời rạc, rất dễ để mô tả xác suất của mỗi sự kiện bằng hàm P(X). Đối với mỗi giá trị s từ không gian mẫu S, nó sẽ đưa ra một số từ 0 đến 1, sao cho tổng của tất cả các giá trị của P(X=s) cho tất cả các sự kiện sẽ là 1.

Phân phối rời rạc được biết đến nhiều nhất là **phân phối đều** , trong đó có một không gian mẫu gồm N phần tử, với xác suất bằng nhau là 1/N cho mỗi phần tử.

Khó hơn để mô tả phân phối xác suất của một biến liên tục, với các giá trị được rút ra từ một khoảng [a,b], hoặc toàn bộ tập hợp các số thực ℝ. Hãy xem xét trường hợp thời gian đến của xe buýt. Trên thực tế, đối với mỗi thời gian đến chính xác t , xác suất xe buýt đến đúng thời điểm đó là 0!

> Bây giờ bạn biết rằng các sự kiện có xác suất bằng 0 xảy ra, và rất thường xuyên! Ít nhất là mỗi lần xe buýt đến!

Chúng ta chỉ có thể nói về xác suất của một biến rơi vào một khoảng giá trị nhất định, ví dụ: P(t 1 ≤X<t 2 ). Trong trường hợp này, phân phối xác suất được mô tả bằng **hàm mật độ xác suất** p(x), sao cho:

![P(t_1\le X<t_2)=\int_{t_1}^{t_2}p(x)dx](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/blob/main/1-Introduction/04-stats-and-probability/images/probability-density.png?raw=true)
  
Một phép tương tự liên tục của phân phối đều được gọi là **phân phối đều liên tục** , được định nghĩa trên một khoảng hữu hạn. Xác suất giá trị X rơi vào một khoảng có độ dài l tỷ lệ thuận với l và tăng lên đến 1.

Một phân phối quan trọng khác là **phân phối chuẩn** , chúng ta sẽ nói chi tiết hơn về phân phối này bên dưới.

## Mean (Giá trị kỳ vọng), Variance (Phương sai) and Standard Deviation (Độ lệch chuẩn)

Giả sử chúng ta vẽ một chuỗi n mẫu của một biến ngẫu nhiên X: x 1 , x 2 , ..., x n . Chúng ta có thể định nghĩa **giá trị trung bình** (hoặc **trung bình số học**) của chuỗi theo cách truyền thống là (x 1 + x 2 + x n )/n. Khi chúng ta tăng kích thước của mẫu (tức là lấy giới hạn với n→∞), chúng ta sẽ thu được giá trị trung bình (còn gọi là **kỳ vọng**) của phân phối. Chúng ta sẽ biểu thị kỳ vọng là **E (x)**.

> Có thể chứng minh rằng đối với bất kỳ phân phối rời rạc nào có các giá trị {x 1 , x 2 , ..., x N } và các xác suất tương ứng p 1 , p 2 , ..., p N , thì kỳ vọng sẽ bằng E(X)=x 1 p 1 +x 2 p 2 +...+x N p N .

Để xác định các giá trị được phân tán xa đến mức nào, chúng ta có thể tính toán phương sai σ^2 = ∑(x i - μ)^2 /n, trong đó μ là giá trị trung bình của chuỗi. Giá trị σ được gọi là **độ lệch chuẩn** và σ^2 được gọi là **phương sai**.

## Mode (Yếu vị), Median (Trung vị) and Quartiles (Tứ phân vị)

Đôi khi, giá trị trung bình không thể hiện đầy đủ giá trị "điển hình" cho dữ liệu. Ví dụ, khi có một vài giá trị cực trị nằm ngoài phạm vi, chúng có thể ảnh hưởng đến giá trị trung bình. Một chỉ báo tốt khác là **trung vị** , một giá trị sao cho một nửa số điểm dữ liệu thấp hơn nó và một nửa khác cao hơn.

Để giúp chúng ta hiểu được sự phân bổ dữ liệu, sẽ hữu ích khi nói về **tứ phân vị** :

* Tứ phân vị đầu tiên, hay Q1, là một giá trị sao cho 25% dữ liệu nằm dưới nó
* Tứ phân vị thứ ba, hay Q3, là giá trị mà 75% dữ liệu nằm dưới nó

Về mặt đồ họa, chúng ta có thể biểu diễn mối quan hệ giữa trung vị và tứ phân vị trong một sơ đồ gọi là **biểu đồ hộp** :

<img src="https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/blob/main/1-Introduction/04-stats-and-probability/images/boxplot_explanation.png?raw=true" width="75%"/>

Ở đây chúng ta cũng tính toán khoảng **tứ phân vị** IQR=Q3-Q1 và các **giá trị ngoại lai** nằm ngoài ranh giới [Q1-1,5 IQR,Q3+1,5 IQR].

Đối với phân phối hữu hạn chứa một số lượng nhỏ các giá trị có thể, một giá trị "điển hình" tốt là giá trị xuất hiện thường xuyên nhất, được gọi là **Mode (yếu vị)** . Nó thường được áp dụng cho dữ liệu phân loại, chẳng hạn như màu sắc. Hãy xem xét một tình huống khi chúng ta có hai nhóm người - một số người thích màu đỏ và những người khác thích màu xanh lam. Nếu chúng ta mã hóa màu theo số, giá trị trung bình cho một màu yêu thích sẽ nằm ở đâu đó trong quang phổ màu cam-xanh lục, điều này không chỉ ra sở thích thực tế của cả hai nhóm. Tuy nhiên, yếu vị sẽ là một trong hai màu hoặc cả hai màu, nếu số người bỏ phiếu cho chúng bằng nhau (trong trường hợp này, chúng ta gọi mẫu là **đa phương thức**).

Một ví dụ khác, trong tập dữ liệu {1, 3, 6, 6, 6, 7, 7, 12, 12, 17}, yếu vị (mốt) là 6, vì nó xuất hiện nhiều lần nhất. Yếu vị giúp xác định giá trị phổ biến nhất trong tập dữ liệu, đặc biệt hữu ích khi phân tích các tập dữ liệu phân loại hoặc khi cần xác định tần suất xuất hiện của một giá trị cụ thể. Và theo đó, một tập dữ liệu có thể có một hoặc nhiều yếu vị, hoặc không có yếu vị nào cả, tùy thuộc vào tần suất xuất hiện của các giá trị trong tập dữ liệu đó.

## Real-world Data (Dữ liệu trong thực tế)

Khi chúng ta phân tích dữ liệu từ cuộc sống thực, chúng thường không phải là các biến ngẫu nhiên, theo nghĩa là chúng ta không thực hiện các thí nghiệm với kết quả chưa biết. Ví dụ, hãy xem xét một đội cầu thủ bóng chày và dữ liệu cơ thể của họ, chẳng hạn như chiều cao, cân nặng và tuổi tác. Những con số đó không hoàn toàn ngẫu nhiên, nhưng chúng ta vẫn có thể áp dụng các khái niệm toán học tương tự. Ví dụ, một chuỗi cân nặng của mọi người có thể được coi là một chuỗi các giá trị được rút ra từ một số biến ngẫu nhiên. Dưới đây là chuỗi **cân nặng** của các cầu thủ bóng chày thực tế từ giải đấu [Major League Baseball](http://mlb.mlb.com/index.jsp), được lấy từ [dataset](http://wiki.stat.ucla.edu/socr/index.php/SOCR_Data_MLB_HeightsWeights) (để thuận tiện cho bạn, chỉ hiển thị 20 giá trị đầu tiên):

```
[180.0, 215.0, 210.0, 210.0, 188.0, 176.0, 209.0, 200.0, 231.0, 180.0, 188.0, 180.0, 185.0, 160.0, 180.0, 185.0, 197.0, 189.0, 185.0, 219.0]
```

> **Lưu ý :** Để xem ví dụ về cách làm việc với tập dữ liệu này, hãy xem [accompanying notebook](notebook.ipynb). Ngoài ra còn có một số thử thách trong suốt bài học này và bạn có thể hoàn thành chúng bằng cách thêm một số mã vào sổ tay đó. Nếu bạn không chắc chắn về cách vận hành dữ liệu, đừng lo lắng - chúng ta sẽ quay lại làm việc với dữ liệu bằng Python sau. Nếu bạn không biết cách chạy mã trong Jupyter Notebook, hãy xem [Hướng dẫn](https://soshnikov.com/education/how-to-execute-notebooks-from-github/).

Sau đây là biểu đồ hộp hiển thị giá trị trung bình, trung vị và tứ phân vị cho dữ liệu của chúng ta:

![Weight Box Plot](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/raw/main/1-Introduction/04-stats-and-probability/images/weight-boxplot.png)

Vì dữ liệu của chúng tôi chứa thông tin về các **vai trò** khác nhau của người chơi , chúng tôi cũng có thể thực hiện biểu đồ hộp theo vai trò - điều này sẽ cho phép chúng tôi hiểu được cách các giá trị tham số khác nhau giữa các vai trò. Lần này chúng tôi sẽ xem xét **chiều cao**:

![Box plot by role](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/blob/main/1-Introduction/04-stats-and-probability/images/boxplot_byrole.png)

Biểu đồ này cho thấy rằng, trung bình, chiều cao của cầu thủ _gôn đầu tiên_ cao hơn chiều cao của cầu thủ _gôn thứ hai_. Sau này trong bài học này, chúng ta sẽ tìm hiểu cách chúng ta có thể **kiểm định giả thuyết** này một cách chính thức hơn và cách chứng minh rằng dữ liệu của chúng ta có ý nghĩa thống kê để chứng minh điều đó.

> Khi làm việc với dữ liệu thực tế, chúng tôi giả định rằng tất cả các điểm dữ liệu đều là các mẫu được rút ra từ một số phân phối xác suất. Giả định này cho phép chúng tôi áp dụng các kỹ thuật học máy và xây dựng các mô hình dự đoán hoạt động.

Để xem phân phối dữ liệu của chúng ta là gì, chúng ta có thể vẽ một biểu đồ gọi là **biểu đồ histogram** . Trục X sẽ chứa một số khoảng trọng số khác nhau (còn gọi là **bin** ), và trục dọc sẽ hiển thị số lần mẫu biến ngẫu nhiên của chúng ta nằm trong một khoảng nhất định.

![Histogram of real world data](images/weight-histogram.png)

From this histogram you can see that all values are centered around certain mean weight, and the further we go from that weight - the fewer weights of that value are encountered. I.e., it is very improbable that the weight of a baseball player would be very different from the mean weight. Variance of weights show the extent to which weights are likely to differ from the mean.

> If we take weights of other people, not from the baseball league, the distribution is likely to be different. However, the shape of the distribution will be the same, but mean and variance would change. So, if we train our model on baseball players, it is likely to give wrong results when applied to students of a university, because the underlying distribution is different.
## Normal Distribution

The distribution of weights that we have seen above is very typical, and many measurements from real world follow the same type of distribution, but with different mean and variance. This distribution is called **normal distribution**, and it plays a very important role in statistics.

Using normal distribution is a correct way to generate random weights of potential baseball players. Once we know mean weight `mean` and standard deviation `std`, we can generate 1000 weight samples in the following way:
```python
samples = np.random.normal(mean,std,1000)
``` 

If we plot the histogram of the generated samples we will see the picture very similar to the one shown above. And if we increase the number of samples and the number of bins, we can generate a picture of a normal distribution that is more close to ideal:

![Normal Distribution with mean=0 and std.dev=1](images/normal-histogram.png)

*Normal Distribution with mean=0 and std.dev=1*

## Confidence Intervals

When we talk about weights of baseball players, we assume that there is certain **random variable W** that corresponds to ideal probability distribution of weights of all baseball players (so-called **population**). Our sequence of weights corresponds to a subset of all baseball players that we call **sample**. An interesting question is, can we know the parameters of distribution of W, i.e. mean and variance of the population?

The easiest answer would be to calculate mean and variance of our sample. However, it could happen that our random sample does not accurately represent complete population. Thus it makes sense to talk about **confidence interval**.

> **Confidence interval** is the estimation of true mean of the population given our sample, which is accurate is a certain probability (or **level of confidence**).

Suppose we have a sample X<sub>1</sub>, ..., X<sub>n</sub> from our distribution. Each time we draw a sample from our distribution, we would end up with different mean value &mu;. Thus &mu; can be considered to be a random variable. A **confidence interval** with confidence p is a pair of values (L<sub>p</sub>,R<sub>p</sub>), such that **P**(L<sub>p</sub>&leq;&mu;&leq;R<sub>p</sub>) = p, i.e. a probability of measured mean value falling within the interval equals to p.

It does beyond our short intro to discuss in detail how those confidence intervals are calculated. Some more details can be found [on Wikipedia](https://en.wikipedia.org/wiki/Confidence_interval). In short, we define the distribution of computed sample mean relative to the true mean of the population, which is called **student distribution**.

> **Interesting fact**: Student distribution is named after mathematician William Sealy Gosset, who published his paper under the pseudonym "Student". He worked in the Guinness brewery, and, according to one of the versions, his employer did not want general public to know that they were using statistical tests to determine the quality of raw materials.

If we want to estimate the mean &mu; of our population with confidence p, we need to take *(1-p)/2-th percentile* of a Student distribution A, which can either be taken from tables, or computer using some built-in functions of statistical software (eg. Python, R, etc.). Then the interval for &mu; would be given by X&pm;A*D/&radic;n, where X is the obtained mean of the sample, D is the standard deviation.

> **Note**: We also omit the discussion of an important concept of [degrees of freedom](https://en.wikipedia.org/wiki/Degrees_of_freedom_(statistics)), which is important in relation to Student distribution. You can refer to more complete books on statistics to understand this concept deeper.

An example of calculating confidence interval for weights and heights is given in the [accompanying notebooks](notebook.ipynb).

| p | Weight mean |
|-----|-----------|
| 0.85 | 201.73±0.94 |
| 0.90 | 201.73±1.08 |
| 0.95 | 201.73±1.28 |

Notice that the higher is the confidence probability, the wider is the confidence interval. 

## Hypothesis Testing 

In our baseball players dataset, there are different player roles, that can be summarized below (look at the [accompanying notebook](notebook.ipynb) to see how this table can be calculated):

| Role | Height | Weight | Count |
|------|--------|--------|-------|
| Catcher | 72.723684 | 204.328947 | 76 |
| Designated_Hitter | 74.222222 | 220.888889 | 18 |
| First_Baseman | 74.000000 | 213.109091 | 55 |
| Outfielder | 73.010309 | 199.113402 | 194 |
| Relief_Pitcher | 74.374603 | 203.517460 | 315 |
| Second_Baseman | 71.362069 | 184.344828 | 58 |
| Shortstop | 71.903846 | 182.923077 | 52 |
| Starting_Pitcher | 74.719457 | 205.163636 | 221 |
| Third_Baseman | 73.044444 | 200.955556 | 45 |

We can notice that the mean heights of first basemen is higher than that of second basemen. Thus, we may be tempted to conclude that **first basemen are higher than second basemen**.

> This statement is called **a hypothesis**, because we do not know whether the fact is actually true or not.

However, it is not always obvious whether we can make this conclusion. From the discussion above we know that each mean has an associated confidence interval, and thus this difference can just be a statistical error. We need some more formal way to test our hypothesis.

Let's compute confidence intervals separately for heights of first and second basemen:

| Confidence | First Basemen | Second Basemen |
|------------|---------------|----------------|
| 0.85 | 73.62..74.38 | 71.04..71.69 |
| 0.90 | 73.56..74.44 | 70.99..71.73 |
| 0.95 | 73.47..74.53 | 70.92..71.81 |

We can see that under no confidence the intervals overlap. That proves our hypothesis that first basemen are higher than second basemen.

More formally, the problem we are solving is to see if **two probability distributions are the same**, or at least have the same parameters. Depending on the distribution, we need to use different tests for that. If we know that our distributions are normal, we can apply **[Student t-test](https://en.wikipedia.org/wiki/Student%27s_t-test)**. 

In Student t-test, we compute so-called **t-value**, which indicates the difference between means, taking into account the variance. It is demonstrated that t-value follows **student distribution**, which allows us to get the threshold value for a given confidence level **p** (this can be computed, or looked up in the numerical tables). We then compare t-value to this threshold to approve or reject the hypothesis.

In Python, we can use the **SciPy** package, which includes `ttest_ind` function (in addition to many other useful statistical functions!). It computes the t-value for us, and also does the reverse lookup of confidence p-value, so that we can just look at the confidence to draw the conclusion.

For example, our comparison between heights of first and second basemen give us the following results: 
```python
from scipy.stats import ttest_ind

tval, pval = ttest_ind(df.loc[df['Role']=='First_Baseman',['Height']], df.loc[df['Role']=='Designated_Hitter',['Height']],equal_var=False)
print(f"T-value = {tval[0]:.2f}\nP-value: {pval[0]}")
```
```
T-value = 7.65
P-value: 9.137321189738925e-12
```
In our case, p-value is very low, meaning that there is strong evidence supporting that first basemen are taller.

There are also different other types of hypothesis that we might want to test, for example:
* To prove that a given sample follows some distribution. In our case we have assumed that heights are normally distributed, but that needs formal statistical verification. 
* To prove that a mean value of a sample corresponds to some predefined value
* To compare means of a number of samples (eg. what is the difference in happiness levels among different age groups)

## Law of Large Numbers and Central Limit Theorem

One of the reasons why normal distribution is so important is so-called **central limit theorem**. Suppose we have a large sample of independent N values X<sub>1</sub>, ..., X<sub>N</sub>, sampled from any distribution with mean &mu; and variance &sigma;<sup>2</sup>. Then, for sufficiently large N (in other words, when N&rarr;&infin;), the mean &Sigma;<sub>i</sub>X<sub>i</sub> would be normally distributed, with mean &mu; and variance &sigma;<sup>2</sup>/N.

> Another way to interpret the central limit theorem is to say that regardless of distribution, when you compute the mean of a sum of any random variable values you end up with normal distribution. 

From the central limit theorem it also follows that, when N&rarr;&infin;, the probability of the sample mean to be equal to &mu; becomes 1. This is known as **the law of large numbers**.

## Covariance and Correlation

One of the things Data Science does is finding relations between data. We say that two sequences **correlate** when they exhibit the similar behavior at the same time, i.e. they either rise/fall simultaneously, or one sequence rises when another one falls and vice versa. In other words, there seems to be some relation between two sequences.

> Correlation does not necessarily indicate causal relationship between two sequences; sometimes both variables can depend on some external cause, or it can be purely by chance the two sequences correlate. However, strong mathematical correlation is a good indication that two variables are somehow connected.

 Mathematically, the main concept that shows the relation between two random variables is **covariance**, that is computed like this: Cov(X,Y) = **E**\[(X-**E**(X))(Y-**E**(Y))\]. We compute the deviation of both variables from their mean values, and then product of those deviations. If both variables deviate together, the product would always be a positive value, that would add up to positive covariance. If both variables deviate out-of-sync (i.e. one falls below average when another one rises above average), we will always get negative numbers, that will add up to negative covariance. If the deviations are not dependent, they will add up to roughly zero.

The absolute value of covariance does not tell us much on how large the correlation is, because it depends on the magnitude of actual values. To normalize it, we can divide covariance by standard deviation of both variables, to get **correlation**. The good thing is that correlation is always in the range of [-1,1], where 1 indicates strong positive correlation between values, -1 - strong negative correlation, and 0 - no correlation at all (variables are independent). 

**Example**: We can compute correlation between weights and heights of baseball players from the dataset mentioned above:
```python
print(np.corrcoef(weights,heights))
```
As a result, we get **correlation matrix** like this one:
```
array([[1.        , 0.52959196],
       [0.52959196, 1.        ]])
```

> Correlation matrix C can be computed for any number of input sequences S<sub>1</sub>, ..., S<sub>n</sub>. The value of C<sub>ij</sub> is the correlation between S<sub>i</sub> and S<sub>j</sub>, and diagonal elements are always 1 (which is also self-correlation of S<sub>i</sub>).

In our case, the value 0.53 indicates that there is some correlation between weight and height of a person. We can also make the scatter plot of one value against the other to see the relationship visually:

![Relationship between weight and height](images/weight-height-relationship.png)

> More examples of correlation and covariance can be found in [accompanying notebook](notebook.ipynb).

## Conclusion

In this section, we have learnt:

* basic statistical properties of data, such as mean, variance, mode and quartiles
* different distributions of random variables, including normal distribution
* how to find correlation between different properties
* how to use sound apparatus of math and statistics in order to prove some hypotheses, 
* how to compute confidence intervals for random variable given data sample

While this is definitely not exhaustive list of topics that exist within probability and statistics, it should be enough to give you a good start into this course.

## 🚀 Challenge

Use the sample code in the notebook to test other hypothesis that: 
1. First basemen are older than second basemen
2. First basemen are taller than third basemen
3. Shortstops are taller than second basemen

## [Post-lecture quiz](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/7)

## Review & Self Study

Probability and statistics is such a broad topic that it deserves its own course. If you are interested to go deeper into theory, you may want to continue reading some of the following books:

1. [Carlos Fernandez-Granda](https://cims.nyu.edu/~cfgranda/) from New York University has great lecture notes [Probability and Statistics for Data Science](https://cims.nyu.edu/~cfgranda/pages/stuff/probability_stats_for_DS.pdf) (available online)
1. [Peter and Andrew Bruce. Practical Statistics for Data Scientists.](https://www.oreilly.com/library/view/practical-statistics-for/9781491952955/) [[sample code in R](https://github.com/andrewgbruce/statistics-for-data-scientists)]. 
1. [James D. Miller. Statistics for Data Science](https://www.packtpub.com/product/statistics-for-data-science/9781788290678) [[sample code in R](https://github.com/PacktPublishing/Statistics-for-Data-Science)]

## Assignment

[Small Diabetes Study](assignment.md)

## Credits

This lesson has been authored with ♥️ by [Dmitry Soshnikov](http://soshnikov.com)
