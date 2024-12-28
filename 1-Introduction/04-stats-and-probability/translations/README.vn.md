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

## Law of Large Numbers and Central Limit Theorem - Luật số lớn và định lý giới hạn trung tâm

Một trong những lý do tại sao phân phối chuẩn lại quan trọng như vậy là cái gọi là **định lý giới hạn trung tâm**. Giả sử chúng ta có một mẫu lớn gồm N giá trị độc lập X 1 , ..., X N , được lấy mẫu từ bất kỳ phân phối nào có trung bình μ và phương sai σ 2 . Khi đó, đối với N đủ lớn (nói cách khác, khi N→∞), trung bình Σ i X i sẽ được phân phối chuẩn, với trung bình μ và phương sai σ 2 /N.

> Một cách khác để diễn giải định lý giới hạn trung tâm là nói rằng bất kể phân phối nào, khi bạn tính giá trị trung bình của tổng các giá trị biến ngẫu nhiên, bạn sẽ thu được phân phối chuẩn.

Từ định lý giới hạn trung tâm, ta cũng suy ra rằng khi N→∞, xác suất trung bình mẫu bằng μ trở thành 1. Điều này được gọi là **định luật số lớn** .

## Covariance and Correlation - Hiệp phương sai và tương quan

Một trong những việc mà Khoa học dữ liệu làm là tìm ra mối quan hệ giữa dữ liệu. Chúng ta nói rằng hai chuỗi **tương quan** khi chúng thể hiện hành vi tương tự nhau cùng một lúc, tức là chúng tăng/giảm đồng thời, hoặc một chuỗi tăng khi chuỗi khác giảm và ngược lại. Nói cách khác, có vẻ như có một số mối quan hệ giữa hai chuỗi.

> Tương quan không nhất thiết chỉ ra mối quan hệ nhân quả giữa hai chuỗi; đôi khi cả hai biến có thể phụ thuộc vào một số nguyên nhân bên ngoài, hoặc có thể hoàn toàn ngẫu nhiên khi hai chuỗi tương quan. Tuy nhiên, tương quan toán học mạnh là một dấu hiệu tốt cho thấy hai biến có liên quan với nhau theo một cách nào đó.

Về mặt toán học, khái niệm chính thể hiện mối quan hệ giữa hai biến ngẫu nhiên là **hiệp phương sai**, được tính như sau: Cov(X,Y) = E [(X- E (X))(Y- E (Y))]. Chúng ta tính độ lệch của cả hai biến so với giá trị trung bình của chúng, sau đó tính tích của các độ lệch đó. Nếu cả hai biến cùng lệch, tích sẽ luôn là một giá trị dương, tổng hợp sẽ thành **hiệp phương sai dương**. Nếu cả hai biến đều lệch không đồng bộ (tức là một biến giảm xuống dưới mức trung bình khi biến kia tăng lên trên mức trung bình), chúng ta sẽ luôn nhận được các số âm, tổng hợp sẽ thành **hiệp phương sai âm**. Nếu các độ lệch không phụ thuộc, tổng hợp của chúng sẽ gần bằng không.

Giá trị tuyệt đối của hiệp phương sai không cho chúng ta biết nhiều về mức độ tương quan lớn như thế nào, vì nó phụ thuộc vào độ lớn của các giá trị thực tế. Để chuẩn hóa nó, chúng ta có thể chia hiệp phương sai cho độ lệch chuẩn của cả hai biến, để có được tương quan . Điều tốt là tương quan luôn nằm trong phạm vi [-1,1], trong đó 1 biểu thị tương quan dương mạnh giữa các giá trị, -1 - tương quan âm mạnh và 0 - không có tương quan nào cả **(các biến độc lập)**.

**Ví dụ :** Chúng ta có thể tính toán mối tương quan giữa cân nặng và chiều cao của cầu thủ bóng chày từ tập dữ liệu được đề cập ở trên:
```python
print(np.corrcoef(weights,heights))
```
As a result, we get **correlation matrix** like this one:
```
array([[1.        , 0.52959196],
       [0.52959196, 1.        ]])
```

> Ma trận tương quan C có thể được tính toán cho bất kỳ số lượng chuỗi đầu vào nào S 1 , ..., S n . Giá trị của C ij là tương quan giữa S i và S j , và các phần tử đường chéo luôn là 1 (cũng là tự tương quan của S i ).

Trong trường hợp này, giá trị 0,53 cho biết có một số mối tương quan giữa cân nặng và chiều cao của một cầu thủ. Chúng ta cũng có thể tạo biểu đồ phân tán của một giá trị so với giá trị kia để xem mối quan hệ trực quan:

![Relationship between weight and height](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/raw/main/1-Introduction/04-stats-and-probability/images/weight-height-relationship.png)

> Có thể tìm thêm ví dụ về tương quan và hiệp phương sai trong [notebook](notebook.ipynb).

## Conclusion - Kết luận

Trong phần này, chúng ta đã học:

* Các thuộc tính thống kê cơ bản của dữ liệu, chẳng hạn như trung bình, phương sai, mốt và tứ phân vị;
* Các phân phối khác nhau của các biến ngẫu nhiên, bao gồm phân phối chuẩn;
* Làm thế nào để tìm mối tương quan giữa các thuộc tính khác nhau;
* Cách sử dụng công cụ toán học và thống kê để chứng minh một số giả thuyết;
* Cách tính khoảng tin cậy cho biến ngẫu nhiên với mẫu dữ liệu cho trước;

Mặc dù đây không phải là danh sách đầy đủ các chủ đề trong xác suất và thống kê, nhưng nó cũng đủ để giúp bạn bắt đầu khóa học này.

## 🚀 Challenge - Thử thách thực hành

Sử dụng mã mẫu trong sổ tay để kiểm tra giả thuyết khác rằng:

1. Cầu thủ gôn đầu tiên lớn tuổi hơn cầu thủ gôn thứ hai
2. Cầu thủ gôn đầu tiên cao hơn cầu thủ gôn thứ ba
3. Cầu thủ chặn bóng đầu tiên thấp hơn cầu thủ chặn bóng thứ hai

## [Câu hỏi sau bài giảng](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/7)

## Review & Self Study - Đánh giá & Tự học

Xác suất và thống kê là một chủ đề rộng đến mức nó xứng đáng có một khóa học riêng. Nếu bạn muốn tìm hiểu sâu hơn về lý thuyết, bạn có thể muốn tiếp tục đọc một số cuốn sách sau:

1. [Carlos Fernandez-Granda](https://cims.nyu.edu/~cfgranda/) từ Đại học New York có các bài giảng tuyệt vời [Probability and Statistics for Data Science](https://cims.nyu.edu/~cfgranda/pages/stuff/probability_stats_for_DS.pdf) (available online)
1. [Peter and Andrew Bruce. Practical Statistics for Data Scientists.](https://www.oreilly.com/library/view/practical-statistics-for/9781491952955/) [[sample code in R](https://github.com/andrewgbruce/statistics-for-data-scientists)]. 
1. [James D. Miller. Statistics for Data Science](https://www.packtpub.com/product/statistics-for-data-science/9781788290678) [[sample code in R](https://github.com/PacktPublishing/Statistics-for-Data-Science)]

## Assignment - Bài tập phân công

[Nghiên cứu nhỏ về bệnh tiểu đường](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/blob/main/1-Introduction/04-stats-and-probability/translations/Assignment.vn.md)

## Credits

Bài học này đã được biên soạn ♥️ bởi [Dmitry Soshnikov](http://soshnikov.com)
