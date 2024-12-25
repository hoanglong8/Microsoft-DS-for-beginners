# Định nghĩa Khoa học dữ liệu

![Sketchnote by @sketchthedocs](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/raw/main/sketchnotes/01-Definitions.png)
| :----------------------------------------------------------------------------------------------------: |
|              Defining Data Science - _Sketchnote by [@nitya](https://twitter.com/nitya)_               |

---

[![Defining Data Science Video](https://raw.githubusercontent.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/main/1-Introduction/01-defining-data-science/images/video-def-ds.png)](https://youtu.be/beZ7Mb_oz9I)

## [Câu hỏi trước bài giảng](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/0)

## Dữ liệu là gì?
Trong cuộc sống hàng ngày, chúng ta liên tục bị bao quanh bởi dữ liệu. Văn bản bạn đang đọc hiện tại là dữ liệu. Danh sách số điện thoại của bạn bè trong điện thoại thông minh của bạn là dữ liệu, cũng như thời gian hiện tại hiển thị trên đồng hồ của bạn. Là con người, chúng ta hoạt động theo bản năng với dữ liệu bằng cách đếm số tiền mình có hoặc viết thư cho bạn bè.

Tuy nhiên, dữ liệu trở nên quan trọng hơn nhiều với sự ra đời của máy tính. Vai trò chính của máy tính là thực hiện tính toán, nhưng chúng cần dữ liệu để hoạt động. Do đó, chúng ta cần hiểu cách máy tính lưu trữ và xử lý dữ liệu.

Với sự ra đời của Internet, vai trò của máy tính như một thiết bị xử lý dữ liệu đã tăng lên. Nếu bạn nghĩ về điều đó, chúng ta hiện sử dụng máy tính ngày càng nhiều hơn để xử lý dữ liệu và giao tiếp, thay vì tính toán thực tế. Khi chúng ta viết email cho bạn bè hoặc tìm kiếm thông tin nào đó trên Internet - về cơ bản chúng ta đang tạo, lưu trữ, truyền và thao tác dữ liệu.
> Bạn có nhớ lần cuối cùng bạn sử dụng máy tính để tính toán một cái gì đó là khi nào không? 

## Khoa học dữ liệu là gì?

Theo [Wikipedia](https://en.wikipedia.org/wiki/Data_science), **Khoa học dữ liệu** được định nghĩa là lĩnh vực khoa học sử dụng các phương pháp khoa học để **trích xuất kiến ​​thức (knowledge) và hiểu biết thực tế (insights)** từ dữ liệu có cấu trúc và phi cấu trúc, đồng thời ứng dụng các kiến ​​thức đó vào nhiều lĩnh vực ứng dụng khác nhau.

Định nghĩa này nêu bật những khía cạnh quan trọng sau đây của khoa học dữ liệu:

* Mục tiêu chính của khoa học dữ liệu là **trích xuất kiến ​​thức** từ dữ liệu, nói cách khác là hiểu dữ liệu, tìm ra một số mối quan hệ ẩn và xây dựng mô hình .
* Khoa học dữ liệu sử dụng các phương pháp khoa học , chẳng hạn như **xác suất và thống kê**. Trên thực tế, khi thuật ngữ khoa học dữ liệu lần đầu tiên được giới thiệu, một số người cho rằng khoa học dữ liệu chỉ là một cái tên mới lạ cho thống kê. Ngày nay, rõ ràng là lĩnh vực này rộng hơn nhiều.
* Kiến thức thu được nên được áp dụng để đưa ra những **hiểu biết thực tế** , tức là những hiểu biết thiết thực mà bạn có thể áp dụng vào các tình huống kinh doanh thực tế.
* Chúng ta có thể vận hành trên cả dữ liệu **có cấu trúc và phi cấu trúc** . Chúng ta sẽ quay lại thảo luận về các loại dữ liệu khác nhau sau trong khóa học.
* **Lĩnh vực ứng dụng** là một khái niệm quan trọng và các nhà khoa học dữ liệu thường cần ít nhất một số mức độ chuyên môn trong lĩnh vực vấn đề, ví dụ: tài chính, y học, tiếp thị, v.v....

> Một khía cạnh quan trọng khác của Khoa học dữ liệu là nó nghiên cứu cách dữ liệu có thể được thu thập, lưu trữ và vận hành bằng máy tính. Trong khi thống kê cung cấp cho chúng ta nền tảng toán học, khoa học dữ liệu áp dụng các khái niệm toán học để thực sự rút ra hiểu biết từ dữ liệu.

Một trong những cách (được cho là của [Jim Gray](https://en.wikipedia.org/wiki/Jim_Gray_(computer_scientist))) để xem xét khoa học dữ liệu là coi nó như một mô hình khoa học riêng biệt:
* **Thực nghiệm** , trong đó chúng ta chủ yếu dựa vào quan sát và kết quả của các thí nghiệm
* **Lý thuyết** , nơi các khái niệm mới xuất hiện từ kiến ​​thức khoa học hiện có
* **Tính toán** , nơi chúng ta khám phá ra những nguyên lý mới dựa trên một số thí nghiệm tính toán
* **Dựa trên dữ liệu** , dựa trên việc khám phá các mối quan hệ và mô hình trong dữ liệu  

## Các lĩnh vực liên quan khác

Vì dữ liệu có tính phổ biến nên khoa học dữ liệu cũng là một lĩnh vực rộng lớn, liên quan đến nhiều ngành khác.

<dl>
<dt>Cơ sở dữ liệu</dt>
<dd>
Một cân nhắc quan trọng là **cách lưu trữ** dữ liệu, tức là cách cấu trúc dữ liệu theo cách cho phép xử lý nhanh hơn. Có nhiều loại cơ sở dữ liệu khác nhau lưu trữ dữ liệu có cấu trúc và không có cấu trúc, <a href="../../2-Working-With-Data/README.md">chúng ta sẽ xem xét trong phần tiếp theo của khóa học này</a>.
</dd>
<dt>Dữ liệu lớn</dt>
<dd>
Thông thường chúng ta cần lưu trữ và xử lý lượng dữ liệu rất lớn với cấu trúc tương đối đơn giản. Có những cách tiếp cận và công cụ đặc biệt để lưu trữ dữ liệu đó theo cách phân tán trên cụm máy tính và xử lý dữ liệu đó một cách hiệu quả.
</dd>
<dt>Máy học tập</dt>
<dd>
Một cách để hiểu dữ liệu là **xây dựng một mô hình** có thể dự đoán được kết quả mong muốn. Phát triển các mô hình từ dữ liệu được gọi là **học máy**. Bạn có thể muốn xem Chương trình <a href="https://aka.ms/ml-beginners">Machine Learning for Beginners</a> để tìm hiểu thêm về nó.
</dd>
<dt>Trí tuệ nhân tạo</dt>
<dd>
Một lĩnh vực học máy được gọi là trí tuệ nhân tạo (AI) cũng dựa vào dữ liệu và liên quan đến việc xây dựng các mô hình có độ phức tạp cao mô phỏng các quá trình suy nghĩ của con người. Các phương pháp AI thường cho phép chúng ta biến dữ liệu phi cấu trúc (ví dụ: ngôn ngữ tự nhiên) thành thông tin chi tiết có cấu trúc.
</dd>
<dt>Trực quan hóa</dt>
<dd>
Một lượng lớn dữ liệu là điều không thể hiểu được đối với con người, nhưng một khi chúng ta tạo ra các hình ảnh trực quan hữu ích bằng cách sử dụng dữ liệu đó, chúng ta có thể hiểu rõ hơn về dữ liệu và rút ra một số kết luận. Do đó, điều quan trọng là phải biết nhiều cách để trực quan hóa thông tin - điều mà chúng ta sẽ đề cập trong <a href="../../3-Data-Visualization/README.md">Section 3</a> của khóa học. Các lĩnh vực liên quan cũng bao gồm **Đồ họa thông tin** và **Tương tác giữa người và máy tính** nói chung. 
</dd>
</dl>

## Các loại dữ liệu

Như chúng tôi đã đề cập, dữ liệu ở khắp mọi nơi. Chúng ta chỉ cần nắm bắt nó theo đúng cách! Phân biệt giữa dữ liệu **có cấu trúc** và dữ liệu **phi cấu trúc** là rất hữu ích . Dữ liệu có cấu trúc thường được biểu diễn dưới dạng có cấu trúc tốt, thường là bảng hoặc một số bảng, trong khi dữ liệu không có cấu trúc chỉ là một tập hợp các tệp. Đôi khi chúng ta cũng có thể nói về dữ liệu **bán cấu trúc** , có một số loại cấu trúc có thể thay đổi rất nhiều.

| Có cấu trúc                                                                   | Bán cấu trúc                                                                                | Phi cấu trúc                            |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- | --------------------------------------- |
| Danh sách những người có số điện thoại của họ                                      | Các trang Wikipedia có liên kết                                                                     | Văn bản của Bách khoa toàn thư Britannica        |
| Nhiệt độ trong tất cả các phòng của một tòa nhà tại mọi phút trong 20 năm qua | Bộ sưu tập các bài báo khoa học ở định dạng JSON với tác giả, dữ liệu xuất bản và tóm tắt | Chia sẻ tập tin với các tài liệu của công ty     |
| Dữ liệu về độ tuổi và giới tính của tất cả mọi người vào tòa nhà                 | Các trang Internet                                                                                 | Nguồn cấp video thô từ camera giám sát |

## Nơi để thu thập Dữ liệu

Có nhiều nguồn dữ liệu có thể có và không thể liệt kê hết tất cả! Tuy nhiên, chúng ta hãy đề cập đến một số nơi điển hình mà bạn có thể lấy dữ liệu:

* **Có cấu trúc**
  - **Internet vạn vật (IoT)**, bao gồm dữ liệu từ các cảm biến khác nhau, chẳng hạn như cảm biến nhiệt độ hoặc áp suất, cung cấp rất nhiều dữ liệu hữu ích. Ví dụ, nếu một tòa nhà văn phòng được trang bị cảm biến IoT, chúng ta có thể tự động kiểm soát hệ thống sưởi ấm và chiếu sáng để giảm thiểu chi phí.
  - **Các cuộc khảo sát** mà chúng tôi yêu cầu người dùng hoàn thành sau khi mua hàng hoặc sau khi truy cập một trang web.
  - **Các phân tích hành vi** có thể giúp chúng ta hiểu được mức độ người dùng truy cập sâu vào một trang web và lý do điển hình khiến họ rời khỏi trang web đó là gì.

* **Phi cấu trúc**
  - **Văn bản** có thể là nguồn thông tin chi tiết phong phú, chẳng hạn như điểm số tình cảm chung hoặc trích xuất từ ​​khóa và ý nghĩa ngữ nghĩa.
  - **Hình ảnh hoặc Video** . Video từ camera giám sát có thể được sử dụng để ước tính lưu lượng giao thông trên đường và thông báo cho mọi người về tình trạng tắc đường tiềm ẩn.
  - **File Log (Nhật ký)** máy chủ web có thể được sử dụng để hiểu những trang nào trên trang web của chúng tôi được truy cập nhiều nhất và trong bao lâu.

* **Bán cấu trúc**
  - **Mạng xã hội** có thể là nguồn dữ liệu tuyệt vời về tính cách người dùng và hiệu quả tiềm năng trong việc truyền bá thông tin.
  - Khi chúng ta có một loạt ảnh chụp từ một bữa tiệc, chúng ta có thể thử trích xuất dữ liệu **Group Dynamics** bằng cách xây dựng biểu đồ về những người chụp ảnh với nhau.

Bằng cách biết nhiều nguồn dữ liệu khác nhau, bạn có thể thử nghĩ về các tình huống khác nhau mà các kỹ thuật khoa học dữ liệu có thể được áp dụng để hiểu rõ hơn về tình hình và cải thiện quy trình kinh doanh.


## Bạn có thể làm gì với Dữ liệu

Trong Khoa học dữ liệu, chúng ta cần tập trung vào các bước sau của quá trình làm việc với dữ liệu:

<dl>
<dt>1) Data Acquisition - Thu thập dữ liệu</dt>
<dd>
Bước đầu tiên là thu thập dữ liệu. Trong khi trong nhiều trường hợp, đây có thể là một quá trình đơn giản, như dữ liệu đến cơ sở dữ liệu từ ứng dụng web, đôi khi chúng ta cần sử dụng các kỹ thuật đặc biệt. Ví dụ, dữ liệu từ các cảm biến IoT có thể rất nhiều và việc sử dụng các điểm cuối đệm như IoT Hub để thu thập tất cả dữ liệu trước khi xử lý thêm là một biện pháp tốt.
</dd>
<dt>2) Data Storage - Lưu trữ dữ liệu</dt>
<dd>
Việc lưu trữ dữ liệu có thể là một thách thức, đặc biệt là khi chúng ta đang nói về dữ liệu lớn. Khi quyết định cách lưu trữ dữ liệu, bạn nên dự đoán cách bạn muốn truy vấn dữ liệu trong tương lai. Có một số cách dữ liệu có thể được lưu trữ:
<ul>
<li>A Cơ sở dữ liệu quan hệ lưu trữ một tập hợp các bảng và sử dụng một ngôn ngữ đặc biệt gọi là SQL để truy vấn chúng. Thông thường, các bảng được tổ chức thành các nhóm khác nhau gọi là lược đồ. Trong nhiều trường hợp, chúng ta cần chuyển đổi dữ liệu từ dạng ban đầu để phù hợp với lược đồ.</li>
<li><a href="https://en.wikipedia.org/wiki/NoSQL">Một cơ sở dữ liệu phi truy vấn NoSQL</a> (database), ví dụ như <a href="https://azure.microsoft.com/services/cosmos-db/?WT.mc_id=academic-77958-bethanycheum">CosmosDB</a>, không áp dụng lược đồ cho dữ liệu và cho phép lưu trữ dữ liệu phức tạp hơn, ví dụ như tài liệu JSON phân cấp hoặc đồ thị. Tuy nhiên, cơ sở dữ liệu NoSQL không có khả năng truy vấn phong phú của SQL và không thể áp dụng tính toàn vẹn tham chiếu, tức là các quy tắc về cách dữ liệu được cấu trúc trong các bảng và quản lý mối quan hệ giữa các bảng.</li>
<li><a href="https://en.wikipedia.org/wiki/Data_lake">Hồ dữ liệu</a> được sử dụng cho các bộ sưu tập dữ liệu lớn ở dạng thô, không có cấu trúc. Data lake thường được sử dụng với dữ liệu lớn, trong đó tất cả dữ liệu không thể vừa trên một máy và phải được lưu trữ và xử lý bởi một cụm máy chủ. <a href="https://en.wikipedia.org/wiki/Apache_Parquet">Parquet</a> là định dạng dữ liệu thường được sử dụng kết hợp với dữ liệu lớn.</li> 
</ul>
</dd>
<dt>3) Data Processing - Xử lý dữ liệu</dt>
<dd>
Đây là phần thú vị nhất của hành trình dữ liệu, bao gồm việc chuyển đổi dữ liệu từ dạng ban đầu sang dạng có thể sử dụng để trực quan hóa/đào tạo mô hình. Khi xử lý dữ liệu phi cấu trúc như văn bản hoặc hình ảnh, chúng ta có thể cần sử dụng một số kỹ thuật AI để trích xuất **các tính năng** từ dữ liệu, do đó chuyển đổi dữ liệu sang dạng có cấu trúc.
</dd>
<dt>4) Visualization for Human Insights - Hình dung, trực quan hóa cho phù hợp với nhận thức của con người</dt>
<dd>
Thông thường, để hiểu dữ liệu, chúng ta cần trực quan hóa dữ liệu. Có nhiều kỹ thuật trực quan hóa khác nhau trong hộp công cụ của mình, chúng ta có thể tìm ra chế độ xem phù hợp để đưa ra hiểu biết sâu sắc. Thông thường, một nhà khoa học dữ liệu cần "chơi với dữ liệu", trực quan hóa dữ liệu nhiều lần và tìm kiếm một số mối quan hệ. Ngoài ra, chúng ta có thể sử dụng các kỹ thuật thống kê để kiểm tra giả thuyết hoặc chứng minh mối tương quan giữa các phần dữ liệu khác nhau.   
</dd>
<dt>5) Training a predictive model - Huấn luyện mô hình dự đoán</dt>
<dd>
Vì mục tiêu cuối cùng của khoa học dữ liệu là có thể đưa ra quyết định dựa trên dữ liệu, chúng ta có thể muốn sử dụng các kỹ thuật của <a href="http://github.com/microsoft/ml-for-beginners">Machine Learning</a> để xây dựng một mô hình dự đoán. Sau đó, chúng ta có thể sử dụng mô hình này để đưa ra dự đoán bằng cách sử dụng các tập dữ liệu mới có cấu trúc tương tự.
</dd>
</dl>

Tất nhiên, tùy thuộc vào dữ liệu thực tế, một số bước có thể bị thiếu (ví dụ: khi chúng ta đã có dữ liệu trong cơ sở dữ liệu hoặc khi chúng ta không cần đào tạo mô hình) hoặc một số bước có thể được lặp lại nhiều lần (chẳng hạn như xử lý dữ liệu).

## Số hóa và chuyển đổi số

Trong thập kỷ qua, nhiều doanh nghiệp bắt đầu hiểu được tầm quan trọng của dữ liệu khi đưa ra quyết định kinh doanh. Để áp dụng các nguyên tắc khoa học dữ liệu vào việc điều hành doanh nghiệp, trước tiên người ta cần thu thập một số dữ liệu, tức là chuyển đổi các quy trình kinh doanh sang dạng kỹ thuật số. Điều này được gọi là số hóa . Việc áp dụng các kỹ thuật khoa học dữ liệu vào dữ liệu này để hướng dẫn các quyết định có thể dẫn đến sự gia tăng đáng kể về năng suất (hoặc thậm chí là sự thay đổi trong kinh doanh), được gọi là chuyển đổi kỹ thuật số .

Hãy xem xét một ví dụ. Giả sử chúng ta có một khóa học khoa học dữ liệu (như khóa học này) mà chúng ta cung cấp trực tuyến cho sinh viên và chúng ta muốn sử dụng khoa học dữ liệu để cải thiện khóa học đó. Chúng ta có thể làm như thế nào?

Chúng ta có thể bắt đầu bằng cách hỏi "Những gì có thể được số hóa?" Cách đơn giản nhất là đo thời gian mỗi học sinh hoàn thành từng mô-đun và đo lượng kiến ​​thức thu được bằng cách đưa ra bài kiểm tra trắc nghiệm vào cuối mỗi mô-đun. Bằng cách tính trung bình thời gian hoàn thành của tất cả học sinh, chúng ta có thể tìm ra mô-đun nào gây khó khăn nhất cho học sinh và thực hiện đơn giản hóa chúng.

> Bạn có thể cho rằng cách tiếp cận này không lý tưởng, vì các mô-đun có thể có độ dài khác nhau. Có lẽ công bằng hơn khi chia thời gian cho độ dài của mô-đun (theo số ký tự) và so sánh các giá trị đó.

Khi chúng ta bắt đầu phân tích kết quả của các bài kiểm tra trắc nghiệm, chúng ta có thể cố gắng xác định những khái niệm nào mà học sinh gặp khó khăn khi hiểu và sử dụng thông tin đó để cải thiện nội dung. Để làm được điều đó, chúng ta cần thiết kế các bài kiểm tra theo cách mà mỗi câu hỏi đều liên quan đến một khái niệm hoặc khối kiến ​​thức nhất định.

Nếu chúng ta muốn phức tạp hơn nữa, chúng ta có thể lập biểu đồ thời gian dành cho từng mô-đun so với nhóm tuổi của học sinh. Chúng ta có thể phát hiện ra rằng đối với một số nhóm tuổi, thời gian hoàn thành mô-đun là quá dài không phù hợp hoặc học sinh bỏ học trước khi hoàn thành. Điều này có thể giúp chúng ta đưa ra khuyến nghị về độ tuổi cho mô-đun và giảm thiểu sự không hài lòng của mọi người do kỳ vọng sai lầm.

## 🚀 Challenge - Thử thách cuối bài học

Trong thử thách này, chúng ta sẽ cố gắng tìm các khái niệm có liên quan đến lĩnh vực Khoa học dữ liệu bằng cách xem xét các văn bản. Chúng ta sẽ lấy một bài viết trên Wikipedia về Khoa học dữ liệu, tải xuống và xử lý văn bản, sau đó xây dựng một đám mây từ như thế này:

![Word Cloud for Data Science](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/blob/main/1-Introduction/01-defining-data-science/images/ds_wordcloud.png)

Truy cập [`notebook.ipynb`](/1-Introduction/01-defining-data-science/notebook.ipynb ':ignore') để đọc qua mã. Bạn cũng có thể chạy mã và xem cách nó thực hiện tất cả các chuyển đổi dữ liệu theo thời gian thực. 

> Nếu bạn không biết cách chạy mã trong Jupyter Notebook, hãy xem [this article](https://soshnikov.com/education/how-to-execute-notebooks-from-github/).



## [Kiểm tra sau bài giảng](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/1)

## Assignments - Bài tập thực hành

* **Task 1**: Hãy sửa code trong bài tập để vẽ biểu đồ các khái niệm liên quan tới lĩnh vực **Big Data** and **Machine Learning** => [Bài làm assignment 1](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/blob/main/1-Introduction/01-defining-data-science/task_1_vn.ipynb).
* **Task 2**: Hãy suy nghĩ về **các tình huống giả định** trong Khoa học dữ liệu (Why, How, What about Getting Data in...) => [Bài làm assignment 2](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/blob/main/1-Introduction/01-defining-data-science/translations/Assignment.vn.md).

## Credits

[Bài giảng này](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/blob/main/1-Introduction/01-defining-data-science/translations/README.vn.md) đã được biên soạn ♥️ bởi [Dmitry Soshnikov](http://soshnikov.com) và được dịch sang tiếng Việt bởi [hoanglong208](https://github.com/hoanglong8)
