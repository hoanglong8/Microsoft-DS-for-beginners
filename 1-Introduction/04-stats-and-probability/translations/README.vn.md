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

![Histogram of real world data](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/blob/main/1-Introduction/04-stats-and-probability/images/weight-histogram.png)

Từ biểu đồ này, bạn có thể thấy rằng tất cả các giá trị đều tập trung quanh một trọng số trung bình nhất định và càng xa trọng số đó thì càng ít trọng số của giá trị đó được tìm thấy. Tức là, rất khó có khả năng trọng lượng của một cầu thủ bóng chày sẽ khác nhiều so với trọng lượng trung bình. Phương sai của trọng số cho thấy mức độ mà trọng số có thể khác so với trọng lượng trung bình.

> Nếu chúng ta lấy trọng số của những người khác, không phải từ giải bóng chày, thì phân phối có thể sẽ khác. Tuy nhiên, hình dạng của phân phối sẽ giống nhau, nhưng giá trị trung bình và phương sai sẽ thay đổi. Vì vậy, nếu chúng ta đào tạo mô hình của mình trên các cầu thủ bóng chày, thì có khả năng sẽ đưa ra kết quả sai khi áp dụng cho sinh viên của một trường đại học, vì phân phối cơ bản là khác nhau.

## Normal Distribution - Phân phối chuẩn

Phân phối trọng số mà chúng ta đã thấy ở trên là rất điển hình, và nhiều phép đo từ thế giới thực tuân theo cùng một loại phân phối, nhưng có giá trị trung bình và phương sai khác nhau. Phân phối này được gọi là **phân phối chuẩn** , và nó đóng vai trò rất quan trọng trong thống kê.

Sử dụng phân phối chuẩn là cách đúng để tạo ra trọng số ngẫu nhiên của các cầu thủ bóng chày tiềm năng. Khi chúng ta biết trọng lượng trung bình `mean` và độ lệch chuẩn `std`, chúng ta có thể tạo ra 1000 mẫu trọng số theo cách sau:
```python
samples = np.random.normal(mean,std,1000)
``` 

Nếu chúng ta vẽ biểu đồ histogram của các mẫu được tạo ra, chúng ta sẽ thấy hình ảnh rất giống với hình ảnh được hiển thị ở trên. Và nếu chúng ta tăng số lượng `mẫu` và số lượng `bin` (giảm bước nhảy trọng số ở trục X), chúng ta có thể tạo ra hình ảnh phân phối chuẩn gần với lý tưởng hơn:

![Normal Distribution with mean=0 and std.dev=1](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/raw/main/1-Introduction/04-stats-and-probability/images/normal-histogram.png)

*Phân phối chuẩn với trung bình = 0 và độ lệch chuẩn = 1*

## Confidence Intervals - Khoảng tin cậy

Khi chúng ta nói về trọng lượng của các cầu thủ bóng chày, chúng ta giả định rằng có một **biến ngẫu nhiên W** nhất định tương ứng với phân phối xác suất lý tưởng của trọng lượng của tất cả các cầu thủ bóng chày (còn gọi là **tổng thể** ). Chuỗi trọng lượng của chúng ta tương ứng với một tập hợp con của tất cả các cầu thủ bóng chày mà chúng ta gọi là **mẫu** . Một câu hỏi thú vị là, chúng ta có thể biết các tham số phân phối của W, tức là trung bình và phương sai của quần thể không?

Câu trả lời dễ nhất là tính toán giá trị trung bình và phương sai của mẫu của chúng ta. Tuy nhiên, có thể mẫu ngẫu nhiên của chúng ta không đại diện chính xác cho toàn bộ dân số. Do đó, việc nói về **khoảng tin cậy** là hợp lý .

> **Khoảng tin cậy** là ước tính giá trị trung bình thực của quần thể dựa trên mẫu của chúng ta, độ chính xác là một xác suất nhất định (hoặc **mức độ tin cậy** ).

Giả sử chúng ta có một mẫu X 1 , ..., X n từ phân phối của chúng ta. Mỗi lần chúng ta lấy một mẫu từ phân phối của mình, chúng ta sẽ kết thúc với giá trị trung bình khác nhau μ. Do đó, μ có thể được coi là một biến ngẫu nhiên. **Khoảng tin cậy** với độ tin cậy p là một cặp giá trị (L p ,R p ), sao cho P (L p ≤μ≤R p ) = p, tức là xác suất giá trị trung bình đo được nằm trong khoảng bằng p.

Ngoài phần giới thiệu ngắn gọn của chúng tôi, chúng tôi sẽ thảo luận chi tiết về cách tính toán các khoảng tin cậy đó. Bạn có thể tìm thêm thông tin chi tiết [trên Wikipedia](https://en.wikipedia.org/wiki/Confidence_interval). Tóm lại, chúng tôi định nghĩa phân phối của giá trị trung bình mẫu được tính toán so với giá trị trung bình thực của quần thể, được gọi là **phân phối Student** .

> **Sự thật thú vị :** Phân phối sinh viên được đặt theo tên của nhà toán học William Sealy Gosset, người đã xuất bản bài báo của mình dưới bút danh "Student". Ông làm việc tại nhà máy bia Guinness và theo một trong những phiên bản, công ty của ông không muốn công chúng biết rằng họ đang sử dụng các bài kiểm tra thống kê để xác định chất lượng nguyên liệu thô.

Nếu chúng ta muốn ước tính giá trị trung bình μ của quần thể với độ tin cậy p, chúng ta cần lấy (1-p)/phần trăm thứ 2 của Phân phối Student A, có thể lấy từ bảng hoặc máy tính sử dụng một số hàm tích hợp của phần mềm thống kê (ví dụ: Python, R, v.v.). Khi đó, khoảng cho μ sẽ được đưa ra bởi X±A*D/√n, trong đó X là giá trị trung bình thu được của mẫu, D là độ lệch chuẩn.

> **Lưu ý :** Chúng tôi cũng bỏ qua phần thảo luận về một khái niệm quan trọng về [bậc tự do](https://en.wikipedia.org/wiki/Degrees_of_freedom_(statistics)), điều này rất quan trọng liên quan đến phân phối Student. Bạn có thể tham khảo các sách đầy đủ hơn về thống kê để hiểu sâu hơn về khái niệm này.

Một ví dụ về cách tính khoảng tin cậy cho cân nặng và chiều cao được đưa ra trong [notebooks](notebook.ipynb).

| p | Trọng lượng TB |
|-----|-----------|
| 0.85 | 201.73±0.94 |
| 0.90 | 201.73±1.08 |
| 0.95 | 201.73±1.28 |

Lưu ý rằng xác suất tin cậy càng cao thì khoảng tin cậy càng rộng.

## Hypothesis Testing - Kiểm định giả thuyết

Trong tập dữ liệu cầu thủ bóng chày của chúng tôi, có nhiều vai trò khác nhau của cầu thủ, có thể được tóm tắt bên dưới (hãy xem [notebook](notebook.ipynb) để biết cách tính bảng này):

| Vai trò | Chiều cao | Cân nặng | Số lượng |
|------|--------|--------|-------|
| Catcher | 72.723684 | 204.328947 | 76 |
| Designated_Hitter | 74.222222 | 220.888889 | 18 |
| First_Baseman (cầu thủ gôn đầu tiên) | 74.000000 | 213.109091 | 55 |
| Outfielder | 73.010309 | 199.113402 | 194 |
| Relief_Pitcher | 74.374603 | 203.517460 | 315 |
| Second_Baseman (cầu thủ gôn thứ hai) | 71.362069 | 184.344828 | 58 |
| Shortstop | 71.903846 | 182.923077 | 52 |
| Starting_Pitcher | 74.719457 | 205.163636 | 221 |
| Third_Baseman | 73.044444 | 200.955556 | 45 |

Chúng ta có thể nhận thấy rằng chiều cao trung bình của cầu thủ gôn đầu tiên cao hơn cầu thủ gôn thứ hai. Do đó, chúng ta dễ có khuynh hướng kết luận rằng **cầu thủ gôn đầu tiên cao hơn cầu thủ gôn thứ hai** .

> Câu phát biểu này được gọi là **giả thuyết** , vì chúng ta không biết liệu sự thật có thực sự đúng hay không.

Tuy nhiên, không phải lúc nào cũng rõ ràng liệu chúng ta có thể đưa ra kết luận này hay không. Từ thảo luận ở trên, chúng ta biết rằng mỗi giá trị trung bình có một khoảng tin cậy liên quan và do đó sự khác biệt này chỉ có thể là một lỗi thống kê. Chúng ta cần một số cách chính thức hơn để kiểm tra giả thuyết của mình.

Hãy tính toán riêng khoảng tin cậy cho chiều cao của cầu thủ gôn thứ nhất và thứ hai:

| Độ tin cậy | First Basemen (min-max) | Second Basemen (min-max) |
|------------|---------------|----------------|
| 0.85 | 73.62 - 74.38 | 71.04 - 71.69 |
| 0.90 | 73.56 - 74.44 | 70.99 - 71.73 |
| 0.95 | 73.47 - 74.53 | 70.92 - 71.81 |

Chúng ta có thể thấy rằng trong điều kiện không có sự tin cậy, các khoảng thời gian chồng chéo lên nhau. Điều đó chứng minh cho giả thuyết của chúng ta rằng cầu thủ gôn đầu tiên cao hơn cầu thủ gôn thứ hai.

Chính thức hơn, vấn đề chúng ta đang giải quyết là xem **hai phân phối xác suất có giống nhau** hay ít nhất là có cùng tham số hay không. Tùy thuộc vào phân phối, chúng ta cần sử dụng các phép thử khác nhau cho việc đó. Nếu chúng ta biết rằng phân phối của mình là chuẩn, chúng ta có thể áp dụng **[phép thử t của phân phối Student](https://en.wikipedia.org/wiki/Student%27s_t-test)**. 

Trong kiểm định t của Student, chúng ta tính toán cái gọi là **giá trị t** , biểu thị sự khác biệt giữa các giá trị trung bình, có tính đến phương sai. Điều này chứng minh rằng giá trị t tuân theo **phân phối Student** , cho phép chúng ta có được giá trị ngưỡng cho một mức độ tin cậy p nhất định (có thể tính toán hoặc tra cứu trong các bảng số). Sau đó, chúng ta so sánh giá trị t với ngưỡng này để chấp thuận hoặc bác bỏ giả thuyết.

Trong Python, chúng ta có thể sử dụng **thư viện SciPy** , bao gồm `hàm ttest_ind` (cùng với nhiều hàm thống kê hữu ích khác!). Nó tính toán giá trị t cho chúng ta và cũng thực hiện tra cứu ngược lại giá trị p của độ tin cậy, do đó chúng ta có thể chỉ cần xem độ tin cậy để rút ra kết luận.

Ví dụ, khi so sánh chiều cao của cầu thủ chơi ở vị trí gôn thứ nhất và thứ hai, chúng ta thu được kết quả sau:
```python
from scipy.stats import ttest_ind

tval, pval = ttest_ind(df.loc[df['Role']=='First_Baseman',['Height']], df.loc[df['Role']=='Designated_Hitter',['Height']],equal_var=False)
print(f"T-value = {tval[0]:.2f}\nP-value: {pval[0]}")
```
```
T-value = 7.65
P-value: 9.137321189738925e-12
```
Trong trường hợp của chúng tôi, giá trị p-value rất thấp, nghĩa là có bằng chứng mạnh mẽ chứng minh rằng cầu thủ chơi ở vị trí gôn đầu tiên cao hơn.

Ngoài ra còn có nhiều loại giả thuyết khác mà chúng ta có thể muốn kiểm tra, ví dụ:

* Để chứng minh rằng một mẫu nhất định tuân theo một số phân phối. Trong trường hợp của chúng tôi, chúng tôi đã giả định rằng chiều cao được phân phối bình thường, nhưng điều đó cần xác minh thống kê chính thức.
* Để chứng minh rằng giá trị trung bình của một mẫu tương ứng với một số giá trị được xác định trước
* Để so sánh giá trị trung bình của một số mẫu (ví dụ: mức độ hạnh phúc khác nhau giữa các nhóm tuổi khác nhau là bao nhiêu)

## Law of Large Numbers and Central Limit Theorem - 

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
