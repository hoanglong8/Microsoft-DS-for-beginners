# Làm việc với Cơ sở dữ liệu - dạng có quan hệ

![Sketchnote by [(@sketchthedocs)](https://sketchthedocs.dev)](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/sketchnotes/05-RelationalData.png)
|:---:|
| Working With Data: Relational Databases - _Sketchnote by [@nitya](https://twitter.com/nitya)_ |

Có khả năng là bạn đã từng sử dụng bảng tính để lưu trữ thông tin. Bạn có một tập hợp các hàng và cột, trong đó các hàng chứa thông tin (hoặc dữ liệu) và các cột mô tả thông tin (đôi khi được gọi là siêu dữ liệu). Cơ sở dữ liệu quan hệ được xây dựng dựa trên nguyên tắc cốt lõi này của các cột và hàng trong bảng, cho phép bạn có thông tin trải rộng trên nhiều bảng. Điều này cho phép bạn làm việc với dữ liệu phức tạp hơn, tránh trùng lặp và có tính linh hoạt trong cách bạn khám phá dữ liệu. Hãy cùng khám phá các khái niệm về cơ sở dữ liệu quan hệ.

## [Pre-lecture quiz](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/8)

## Bảng tính

Một cơ sở dữ liệu quan hệ có các bảng cốt lõi. Cũng giống như bảng tính, một bảng là một tập hợp các cột và hàng. Hàng chứa dữ liệu hoặc thông tin mà chúng ta muốn làm việc, chẳng hạn như tên của một thành phố hoặc lượng mưa. Các cột mô tả dữ liệu mà chúng lưu trữ.

Chúng ta hãy bắt đầu khám phá bằng cách lập một bảng để lưu trữ thông tin về các thành phố. Chúng ta có thể bắt đầu bằng tên và quốc gia của thành phố. Bạn có thể lưu trữ thông tin này trong một bảng như sau:

| City     | Country       |
| -------- | ------------- |
| Tokyo    | Japan         |
| Atlanta  | United States |
| Auckland | New Zealand   |

Lưu ý tên cột thành phố , quốc gia và dân số mô tả dữ liệu đang được lưu trữ và mỗi hàng có thông tin về một thành phố.

## Những hạn chế của phương pháp tiếp cận bảng đơn

Rất có thể, bảng trên có vẻ khá quen thuộc với bạn. Chúng ta hãy bắt đầu thêm một số dữ liệu bổ sung vào cơ sở dữ liệu đang phát triển của chúng ta - lượng mưa hàng năm (tính bằng milimét). Chúng ta sẽ tập trung vào các năm 2018, 2019 và 2020. Nếu chúng ta thêm nó cho Tokyo, nó có thể trông giống như thế này:

| City  | Country | Year | Amount |
| ----- | ------- | ---- | ------ |
| Tokyo | Japan   | 2020 | 1690   |
| Tokyo | Japan   | 2019 | 1874   |
| Tokyo | Japan   | 2018 | 1445   |

Bạn nhận thấy điều gì về bảng của chúng tôi? Bạn có thể nhận thấy chúng tôi sao chép tên và quốc gia của thành phố nhiều lần. Điều đó có thể chiếm khá nhiều dung lượng lưu trữ và phần lớn là không cần thiết để có nhiều bản sao. Xét cho cùng, Tokyo chỉ có một cái tên mà chúng tôi quan tâm.

Được rồi, chúng ta hãy thử cách khác. Hãy thêm các cột mới cho mỗi năm:

| City     | Country       | 2018 | 2019 | 2020 |
| -------- | ------------- | ---- | ---- | ---- |
| Tokyo    | Japan         | 1445 | 1874 | 1690 |
| Atlanta  | United States | 1779 | 1111 | 1683 |
| Auckland | New Zealand   | 1386 | 942  | 1176 |

Mặc dù điều này tránh được việc trùng lặp hàng, nhưng nó lại thêm một vài thách thức khác. Chúng ta sẽ cần phải sửa đổi cấu trúc bảng của mình mỗi khi có một năm mới. Ngoài ra, khi dữ liệu của chúng ta tăng lên, việc có các năm dưới dạng cột sẽ khiến việc truy xuất và tính toán giá trị trở nên khó khăn hơn.

Đây là lý do tại sao chúng ta cần nhiều bảng và mối quan hệ. Bằng cách chia nhỏ dữ liệu, chúng ta có thể tránh trùng lặp và linh hoạt hơn trong cách làm việc với dữ liệu.

## Khái niệm của mối quan hệ

Hãy quay lại dữ liệu của chúng ta và xác định cách chúng ta muốn chia nhỏ mọi thứ. Chúng ta biết rằng chúng ta muốn lưu trữ tên và quốc gia cho các thành phố của mình, vì vậy điều này có thể sẽ hiệu quả nhất trong một bảng.

| City     | Country       |
| -------- | ------------- |
| Tokyo    | Japan         |
| Atlanta  | United States |
| Auckland | New Zealand   |

Nhưng trước khi tạo bảng tiếp theo, chúng ta cần tìm ra cách tham chiếu đến từng thành phố. Chúng ta cần một số dạng mã định danh, ID hoặc (theo thuật ngữ cơ sở dữ liệu kỹ thuật) là **khóa chính (primary key)**. Khóa chính là giá trị được sử dụng để xác định một hàng cụ thể trong bảng. Mặc dù điều này có thể dựa trên chính giá trị (ví dụ, chúng ta có thể sử dụng tên thành phố), nhưng nó gần như luôn phải là một số hoặc mã định danh khác. Chúng ta không muốn id thay đổi vì nó sẽ phá vỡ mối quan hệ. Trong hầu hết các trường hợp, bạn sẽ thấy khóa chính hoặc id sẽ là một số được tạo tự động.

> ✅ Primary key thường được viết tắt là PK

### Bảng 1 - Thành phố

| city_id | City     | Country       |
| ------- | -------- | ------------- |
| 1       | Tokyo    | Japan         |
| 2       | Atlanta  | United States |
| 3       | Auckland | New Zealand   |

> ✅ Bạn sẽ thấy chúng ta sử dụng các thuật ngữ "id" và "primary key" thay thế cho nhau trong bài học này. Các khái niệm ở đây áp dụng cho DataFrames, mà bạn sẽ khám phá sau. DataFrames không sử dụng thuật ngữ "primary key", tuy nhiên bạn sẽ thấy chúng hoạt động theo cùng một cách.

Với bảng cities đã tạo, hãy lưu trữ lượng mưa. Thay vì sao chép toàn bộ thông tin về thành phố, chúng ta có thể sử dụng id. Chúng ta cũng nên đảm bảo bảng mới tạo cũng có một cột id , vì tất cả các bảng đều phải có id hoặc khóa chính.

### Bảng 2 - Lượng mưa

| rainfall_id | city_id | Year | Amount |
| ----------- | ------- | ---- | ------ |
| 1           | 1       | 2018 | 1445   |
| 2           | 1       | 2019 | 1874   |
| 3           | 1       | 2020 | 1690   |
| 4           | 2       | 2018 | 1779   |
| 5           | 2       | 2019 | 1111   |
| 6           | 2       | 2020 | 1683   |
| 7           | 3       | 2018 | 1386   |
| 8           | 3       | 2019 | 942    |
| 9           | 3       | 2020 | 1176   |

Lưu ý cột `city_id` bên trong **bảng 2 Lượng mưa** mới tạo . Cột này chứa các giá trị tham chiếu đến `ID` trong **bảng 1 Thành phố** . Theo thuật ngữ dữ liệu quan hệ kỹ thuật, đây được gọi là **khóa ngoại (Foreign key)**; đây là khóa chính từ một bảng khác. Bạn có thể coi nó như một tham chiếu hoặc một con trỏ (pointer). Ví dụ: city_id 1 tham chiếu đến Tokyo.

> ✅ Foreign key thường được viết tắt là FK

## Retrieving the data - Truy vấn dữ liệu

Với dữ liệu của chúng ta được chia thành hai bảng, bạn có thể tự hỏi làm thế nào chúng ta có thể truy xuất dữ liệu. Nếu chúng ta sử dụng cơ sở dữ liệu quan hệ như MySQL, SQL Server hoặc Oracle, chúng ta có thể sử dụng ngôn ngữ được gọi là Ngôn ngữ truy vấn có cấu trúc hoặc SQL. SQL (đôi khi được phát âm là sequel) là ngôn ngữ chuẩn được sử dụng để truy xuất và sửa đổi dữ liệu trong cơ sở dữ liệu quan hệ.

Để lấy dữ liệu, bạn sử dụng lệnh `SELECT`. Về cơ bản, bạn `Select` các cột bạn muốn xem `From` bảng chứa chúng. Nếu bạn chỉ muốn hiển thị tên các thành phố, bạn có thể sử dụng lệnh sau:

```sql
SELECT city
FROM cities;

-- Output:
-- Tokyo
-- Atlanta
-- Auckland
```

`SELECT` là nơi bạn liệt kê các cột và `FROM` là nơi bạn liệt kê các bảng.

> ✅ Cú pháp SQL không phân biệt chữ hoa chữ thường, có nghĩa `select` là `SELECT` giống nhau. Tuy nhiên, tùy thuộc vào loại cơ sở dữ liệu bạn đang sử dụng, các cột và bảng có thể phân biệt chữ hoa chữ thường. Do đó, cách thực hành tốt nhất là luôn xử lý mọi thứ trong lập trình như thể chúng phân biệt chữ hoa chữ thường. Khi viết các truy vấn SQL, quy ước chung là đặt tất cả các từ khóa bằng chữ in hoa.

Truy vấn trên sẽ hiển thị tất cả các thành phố. Hãy tưởng tượng chúng ta chỉ muốn hiển thị các thành phố ở New Zealand. Chúng ta cần một số dạng bộ lọc. Từ khóa SQL cho việc này là `WHERE`, hoặc "nơi cần chọn".

```sql
SELECT city
FROM cities
WHERE country = 'New Zealand';

-- Output:
-- Auckland
```

## Joining data - Nối dữ liệu

Cho đến bây giờ chúng ta đã lấy dữ liệu từ một bảng duy nhất. Bây giờ chúng ta muốn đưa dữ liệu từ cả thành phố và lượng mưa lại với nhau . Điều này được thực hiện bằng cách nối chúng lại với nhau. Bạn sẽ tạo ra một đường nối hiệu quả giữa hai bảng và khớp các giá trị từ một cột của mỗi bảng.

Trong ví dụ của chúng tôi, chúng tôi sẽ khớp cột `city_id` trong **bảng 2 Lượng mưa** với cột `city_id` trong **bảng 1 Thành phố** . Điều này sẽ khớp giá trị lượng mưa với thành phố tương ứng. Kiểu liên kết mà chúng tôi sẽ thực hiện được gọi là **liên kết bên trong - Inner Joiner** , nghĩa là nếu bất kỳ hàng nào không khớp với bất kỳ thứ gì từ bảng khác, chúng sẽ không được hiển thị. Trong trường hợp của chúng tôi, mọi thành phố đều có lượng mưa tương ứng, vì vậy mọi thứ sẽ được hiển thị.

Hãy cùng ước tính lượng mưa năm 2019 cho tất cả các thành phố của chúng ta.

Chúng ta sẽ thực hiện theo từng bước. Bước đầu tiên là nối dữ liệu lại với nhau bằng cách chỉ ra các cột cho đường nối - `city_id`.

```sql
SELECT cities.city
    rainfall.amount
FROM cities
    INNER JOIN rainfall ON cities.city_id = rainfall.city_id
```

Chúng tôi đã đánh dấu hai cột mà chúng tôi muốn và thực tế là chúng tôi muốn nối các bảng lại với nhau bằng `city_id` . Bây giờ chúng tôi có thể thêm `WHERE` câu lệnh để chỉ lọc ra năm 2019.

```sql
SELECT cities.city
    rainfall.amount
FROM cities
    INNER JOIN rainfall ON cities.city_id = rainfall.city_id
WHERE rainfall.year = 2019

-- Output

-- city     | amount
-- -------- | ------
-- Tokyo    | 1874
-- Atlanta  | 1111
-- Auckland |  942
```

## Summary - Tổng kết

Cơ sở dữ liệu quan hệ tập trung vào việc phân chia thông tin giữa nhiều bảng sau đó được đưa trở lại với nhau để hiển thị và phân tích. Điều này cung cấp mức độ linh hoạt cao để thực hiện tính toán và thao tác dữ liệu. Bạn đã thấy các khái niệm cốt lõi của cơ sở dữ liệu quan hệ và cách thực hiện nối giữa hai bảng.

## 🚀 Challenge

Có rất nhiều cơ sở dữ liệu quan hệ có sẵn trên [Microsoft](https://learn.microsoft.com/vi-vn/training/?WT.mc_id=academic-77958-bethanycheum). Bạn có thể khám phá dữ liệu bằng cách sử dụng các kỹ năng bạn đã học ở trên.

## Post-Lecture Quiz

[Kiểm tra sau bài giảng](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/9)

## Review & Self Study - Đánh giá & Tự học

Có một số tài nguyên có sẵn trên [Microsoft Learn](https://docs.microsoft.com/learn?WT.mc_id=academic-77958-bethanycheum) để bạn tiếp tục khám phá các khái niệm về SQL và cơ sở dữ liệu quan hệ:

- [Mô tả các khái niệm về dữ liệu quan hệ](https://docs.microsoft.com//learn/modules/describe-concepts-of-relational-data?WT.mc_id=academic-77958-bethanycheum)
- [Bắt đầu truy vấn với Transact-SQL (Transact-SQL là một phiên bản của SQL)](https://docs.microsoft.com//learn/paths/get-started-querying-with-transact-sql?WT.mc_id=academic-77958-bethanycheum)
- [Nội dung SQL trên Microsoft Learn](https://docs.microsoft.com/learn/browse/?products=azure-sql-database%2Csql-server&expanded=azure&WT.mc_id=academic-77958-bethanycheum)

## Assignment - Bài tập

[Tiêu đề bài tập](https://github.com/hoanglong8/Microsoft-DS-for-beginners/blob/main/2-Working-With-Data/05-relational-databases/translations/Assignment.vn.md)
