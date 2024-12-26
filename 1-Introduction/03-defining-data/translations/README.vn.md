# Định nghĩa Dữ liệu

![Sketchnote by [(@sketchthedocs)](https://sketchthedocs.dev) ](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/raw/main/sketchnotes/03-DefiningData.png)
|:---:|
|Defining Data - _Sketchnote by [@nitya](https://twitter.com/nitya)_ |

**Dữ liệu** là các sự kiện, thông tin, quan sát và phép đo được sử dụng để đưa ra các khám phá và hỗ trợ các quyết định sáng suốt. 

**Điểm dữ liệu** là một đơn vị dữ liệu duy nhất trong một tập dữ liệu, là tập hợp các điểm dữ liệu. Các **tập dữ liệu** có thể có nhiều định dạng và cấu trúc khác nhau và thường dựa trên nguồn dữ liệu hoặc nơi dữ liệu đến. 

Ví dụ: thu nhập hàng tháng của một công ty có thể nằm trong **bảng tính** nhưng dữ liệu nhịp tim hàng giờ từ đồng hồ thông minh có thể ở định dạng [JSON](https://stackoverflow.com/a/383699). Các nhà khoa học dữ liệu thường làm việc với các loại dữ liệu khác nhau trong một tập dữ liệu.

Bài học này tập trung vào việc xác định và phân loại dữ liệu theo đặc điểm và nguồn dữ liệu.

## [Câu hỏi chuẩn bị trước bài giảng](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/4)
## How Data is Described - Dữ liệu được mô tả như thế nào

### Raw Data - Dữ liệu thô
Dữ liệu thô là dữ liệu đến từ nguồn ở trạng thái ban đầu và chưa được phân tích hoặc sắp xếp. Để hiểu được những gì đang xảy ra với một tập dữ liệu, dữ liệu cần được sắp xếp theo định dạng mà con người cũng như công nghệ mà họ có thể sử dụng để phân tích thêm có thể hiểu được. Cấu trúc của một tập dữ liệu mô tả cách thức tổ chức và có thể được phân loại thành có cấu trúc, không có cấu trúc và bán cấu trúc. Các loại cấu trúc này sẽ khác nhau, tùy thuộc vào nguồn nhưng cuối cùng sẽ phù hợp với ba loại này.

### Quantitative Data - Dữ liệu định lượng
Dữ liệu định lượng là các quan sát số trong một tập dữ liệu và thường có thể được phân tích, đo lường và sử dụng theo toán học. Một số ví dụ về dữ liệu định lượng là: dân số của một quốc gia, chiều cao của một người hoặc thu nhập hàng quý của một công ty. Với một số phân tích bổ sung, dữ liệu định lượng có thể được sử dụng để khám phá xu hướng theo mùa của Chỉ số chất lượng không khí (AQI) hoặc ước tính xác suất lưu lượng giao thông vào giờ cao điểm trong một ngày làm việc thông thường.

### Qualitative Data - Dữ liệu định tính
Dữ liệu định tính, còn được gọi là dữ liệu phân loại, là dữ liệu không thể đo lường một cách khách quan như quan sát dữ liệu định lượng. Nhìn chung, đó là nhiều định dạng dữ liệu chủ quan khác nhau nắm bắt chất lượng của một thứ gì đó, chẳng hạn như sản phẩm hoặc quy trình. Đôi khi, dữ liệu định tính là số và thường không được sử dụng theo phương pháp toán học, như số điện thoại hoặc dấu thời gian. Một số ví dụ về dữ liệu định tính là: bình luận video, nhãn hiệu và kiểu xe hoặc màu sắc yêu thích của bạn thân nhất. Dữ liệu định tính có thể được sử dụng để hiểu người tiêu dùng thích sản phẩm nào nhất hoặc xác định các từ khóa phổ biến trong sơ yếu lý lịch xin việc.

### Structured Data - Dữ liệu có cấu trúc
Dữ liệu có cấu trúc là dữ liệu được sắp xếp thành các hàng và cột, trong đó mỗi hàng sẽ có cùng một tập hợp các cột. Các cột biểu thị một giá trị của một loại cụ thể và sẽ được xác định bằng tên mô tả giá trị biểu thị, trong khi các hàng chứa các giá trị thực tế. Các cột thường sẽ có một tập hợp các quy tắc hoặc hạn chế cụ thể đối với các giá trị, để đảm bảo rằng các giá trị biểu thị chính xác cho cột. Ví dụ, hãy tưởng tượng một bảng tính về khách hàng, trong đó mỗi hàng phải có một số điện thoại và các số điện thoại không bao giờ chứa các ký tự chữ cái. Có thể có các quy tắc được áp dụng cho cột số điện thoại để đảm bảo rằng nó không bao giờ trống và chỉ chứa các số.

[Trong hình ảnh sau, một bảng có dữ liệu về điểm số lấy dữ liệu từ bảng tên học sinh và bảng dữ liệu lớp học bằng cách sử dụng các cột khóa.](https://learn.microsoft.com/en-us/training/modules/choose-storage-approach-in-azure/media/relational-database.png)

Một lợi ích của dữ liệu có cấu trúc là nó có thể được sắp xếp theo cách có thể liên quan đến dữ liệu có cấu trúc khác. Tuy nhiên, vì dữ liệu được thiết kế để sắp xếp theo một cách cụ thể, nên việc thay đổi cấu trúc tổng thể của nó có thể tốn nhiều công sức. Ví dụ, thêm một cột email vào bảng tính khách hàng không được để trống có nghĩa là bạn sẽ cần tìm ra cách thêm các giá trị này vào các hàng khách hàng hiện có trong tập dữ liệu.

Ví dụ về dữ liệu có cấu trúc: bảng tính, cơ sở dữ liệu quan hệ, số điện thoại, sao kê ngân hàng...

### Unstructured Data - Dữ liệu phi cấu trúc
Dữ liệu phi cấu trúc thường không thể được phân loại thành các hàng hoặc cột và không chứa định dạng hoặc bộ quy tắc để tuân theo. Vì dữ liệu phi cấu trúc có ít hạn chế hơn về cấu trúc nên việc thêm thông tin mới dễ dàng hơn so với tập dữ liệu có cấu trúc. Nếu một cảm biến thu thập dữ liệu về áp suất khí quyển cứ sau 2 phút đã nhận được bản cập nhật hiện cho phép đo và ghi lại nhiệt độ, thì không cần phải thay đổi dữ liệu hiện có nếu dữ liệu đó không có cấu trúc. Tuy nhiên, điều này có thể khiến việc phân tích hoặc điều tra loại dữ liệu này mất nhiều thời gian hơn. Ví dụ, một nhà khoa học muốn tìm nhiệt độ trung bình của tháng trước từ dữ liệu cảm biến, nhưng phát hiện ra rằng cảm biến đã ghi lại chữ "e" trong một số dữ liệu đã ghi của mình để lưu ý rằng nó đã bị hỏng thay vì một số thông thường, điều đó có nghĩa là dữ liệu không đầy đủ.

Ví dụ về dữ liệu phi cấu trúc: tệp văn bản, tin nhắn văn bản, tệp âm thanh, tệp video, tệp hình ảnh...

### Semi-structured - Dữ liệu bán cấu trúc
Dữ liệu bán cấu trúc có các tính năng khiến nó trở thành sự kết hợp giữa dữ liệu có cấu trúc và không có cấu trúc. Dữ liệu này thường không tuân theo định dạng hàng và cột nhưng được sắp xếp theo cách được coi là có cấu trúc và có thể tuân theo một định dạng hoặc bộ quy tắc cố định. Cấu trúc sẽ thay đổi tùy theo nguồn, chẳng hạn như hệ thống phân cấp được xác định rõ ràng đến thứ gì đó linh hoạt hơn cho phép tích hợp dễ dàng thông tin mới. Siêu dữ liệu là các chỉ báo giúp quyết định cách dữ liệu được sắp xếp và lưu trữ và sẽ có nhiều tên khác nhau, dựa trên loại dữ liệu. Một số tên phổ biến cho siêu dữ liệu là thẻ, phần tử, thực thể và thuộc tính. Ví dụ: một email thông thường sẽ có chủ đề, nội dung và một tập hợp người nhận và có thể được sắp xếp theo người hoặc thời điểm gửi.

Ví dụ về dữ liệu bán cấu trúc: HTML, tệp CSV, JavaScript Object Notation (JSON)...

## Sources of Data - Nguồn dữ liệu

Nguồn dữ liệu là vị trí ban đầu nơi dữ liệu được tạo ra hoặc nơi dữ liệu "sống" và sẽ thay đổi tùy theo cách thức và thời điểm dữ liệu được thu thập. Dữ liệu do người dùng tạo ra được gọi là dữ liệu chính trong khi dữ liệu thứ cấp đến từ một nguồn đã thu thập dữ liệu để sử dụng chung. Ví dụ, một nhóm các nhà khoa học thu thập dữ liệu quan sát trong một khu rừng nhiệt đới sẽ được coi là chính và nếu họ quyết định chia sẻ dữ liệu đó với các nhà khoa học khác thì dữ liệu đó sẽ được coi là thứ cấp đối với những người sử dụng dữ liệu đó.

Cơ sở dữ liệu là một nguồn phổ biến và dựa vào hệ thống quản lý cơ sở dữ liệu để lưu trữ và duy trì dữ liệu, trong đó người dùng sử dụng các lệnh gọi là truy vấn để khám phá dữ liệu. Tệp làm nguồn dữ liệu có thể là tệp âm thanh, hình ảnh và video cũng như bảng tính như Excel. Nguồn Internet là vị trí phổ biến để lưu trữ dữ liệu, nơi có thể tìm thấy cả cơ sở dữ liệu cũng như tệp. Giao diện lập trình ứng dụng, còn được gọi là API, cho phép lập trình viên tạo ra các cách chia sẻ dữ liệu với người dùng bên ngoài thông qua Internet, trong khi quá trình thu thập dữ liệu web trích xuất dữ liệu từ một trang web. Các bài trong phần 2 [Working with Data](/2-Working-With-Data) tập trung vào cách sử dụng các nguồn dữ liệu khác nhau. 

## Conclusion - Kết luận

Trong bài học này chúng ta đã học:

* Dữ liệu là gì?
* Dữ liệu được mô tả như thế nào?
* Dữ liệu được phân loại và sắp xếp như thế nào?
* Nơi dữ liệu có thể được tìm thấy?

## 🚀 Challenge - Hoạt động thử thách

Kaggle là một nguồn tuyệt vời của các tập dữ liệu mở. Sử dụng [dataset search tool](https://www.kaggle.com/datasets) để tìm một số tập dữ liệu thú vị và phân loại 3-5 tập dữ liệu theo tiêu chí này:

* Dữ liệu này là dữ liệu định lượng hay định tính?
* Dữ liệu có cấu trúc, không cấu trúc hay bán cấu trúc?

## [Câu hỏi sau bài giảng](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/5)



## Review & Self Study - Đánh giá & Tự học

- Đơn vị Microsoft Learn này có tên là [Classify your Data](https://docs.microsoft.com/en-us/learn/modules/choose-storage-approach-in-azure/2-classify-data) có phân tích chi tiết về dữ liệu có cấu trúc, bán cấu trúc và không có cấu trúc.

## Assignment - Bài tập phân công

[Bạn hãy thực hành phân loại các tập dữ liệu](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/blob/main/1-Introduction/03-defining-data/translations/Assignment.vn.md)
