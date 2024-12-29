# Displaying airport data - Làm việc với cơ sở dữ liệu về các sân bay

Bạn đã được cung cấp một [database](https://raw.githubusercontent.com/Microsoft/Data-Science-For-Beginners/main/2-Working-With-Data/05-relational-databases/airports.db) được xây dựng trên [SQLite](https://sqlite.org/index.html) chứa thông tin về các sân bay. Sơ đồ được hiển thị bên dưới. Bạn sẽ sử dụng [SQLite extension](https://marketplace.visualstudio.com/items?itemName=alexcvzz.vscode-sqlite&WT.mc_id=academic-77958-bethanycheum) trong [Visual Studio Code](https://code.visualstudio.com?WT.mc_id=academic-77958-bethanycheum) để hiển thị thông tin về các sân bay của các thành phố khác nhau.

## Instructions - Hướng dẫn

Để bắt đầu bài tập, bạn sẽ cần thực hiện một vài bước. Bạn sẽ cần cài đặt một số công cụ và tải xuống cơ sở dữ liệu mẫu.

### Setup your system - Thiết lập hệ thống của bạn

Bạn có thể sử dụng Visual Studio Code và tiện ích mở rộng SQLite để tương tác với cơ sở dữ liệu.

1. Truy cập [code.visualstudio.com](https://code.visualstudio.com?WT.mc_id=academic-77958-bethanycheum) và làm theo hướng dẫn để cài đặt Visual Studio Code.
2. Cài đặt [SQLite extension](https://marketplace.visualstudio.com/items?itemName=alexcvzz.vscode-sqlite&WT.mc_id=academic-77958-bethanycheum) theo hướng dẫn trên trang Marketplace.

### Download and open the database - Tải xuống và mở cơ sở dữ liệu

Tiếp theo bạn sẽ tải xuống và mở cơ sở dữ liệu.

1. Download [database file from GitHub](https://raw.githubusercontent.com/Microsoft/Data-Science-For-Beginners/main/2-Working-With-Data/05-relational-databases/airports.db) và lưu vào một thư mục.
2. Mở Visual Studio Code
3. Mở cơ sở dữ liệu trong phần mở rộng SQLite bằng cách chọn **Ctl-Shift-P** (hoặc **Cmd-Shift-P** trên máy Mac) và nhập `SQLite: Open database`
4. Chọn **cơ sở dữ liệu từ tệp** và mở tệp `airports.db` mà bạn đã tải xuống trước đó
5. Sau khi mở cơ sở dữ liệu (bạn sẽ không thấy bản cập nhật trên màn hình), hãy tạo một cửa sổ truy vấn mới bằng cách chọn **Ctl-Shift-P** (hoặc **Cmd-Shift-P** trên máy Mac) và nhập `SQLite: New query`

Sau khi mở, cửa sổ truy vấn mới có thể được sử dụng để chạy các câu lệnh SQL đối với cơ sở dữ liệu. Bạn có thể sử dụng lệnh **Ctl-Shift-Q** (hoặc **Cmd-Shift-Q** trên máy Mac) để chạy các truy vấn đối với cơ sở dữ liệu.

Hoặc cách 2: Sử dụng DB Browser for SQLite:
* Tải và cài đặt [DB Browser for SQLite](https://sqlitebrowser.org/).
* Mở ứng dụng, chọn "Open Database" và chọn tệp `.db`.
* Sử dụng giao diện đồ họa để thực hiện các truy vấn SQL.

> [!NOTE] Để biết thêm thông tin về tiện ích mở rộng SQLite, bạn có thể tham khảo tài liệu trên [Marketplace](https://marketplace.visualstudio.com/items?itemName=alexcvzz.vscode-sqlite&WT.mc_id=academic-77958-bethanycheum) hoặc [GitHub](https://github.com/nalgeon/sqlean/blob/main/docs/time.md)

Giao diện phần mềm

## Database schema - Sơ đồ dữ liệu

Sơ đồ của cơ sở dữ liệu là thiết kế và cấu trúc bảng của nó. Cơ sở dữ liệu sân bay gồm hai bảng: `cities` chứa danh sách các thành phố ở Vương quốc Anh + Ireland và `airports` chứa danh sách tất cả các sân bay. Vì một số thành phố có thể có nhiều sân bay, nên hai bảng được tạo ra để lưu trữ thông tin. Trong bài tập này, bạn sẽ sử dụng các phép nối để hiển thị thông tin cho các thành phố khác nhau.

| Cities           |
| ---------------- |
| id (PK, integer) |
| city (text)      |
| country (text)   |

| Airports                         |
| -------------------------------- |
| id (PK, integer)                 |
| name (text)                      |
| code (text)                      |
| city_id (FK to id in **Cities**) |

## Assignment - Bài tập tạo câu lệnh truy vấn trong SQL

**1. Hiển thị tất cả các cột trong bảng Cities, bảng Airports:**

`SELECT * FROM Cities`

Kết quả:

| id | City | Country |
|---|---|---|
|2|	Belfast|	United Kingdom|
|3|	Enniskillen|	United Kingdom|
|5|	Londonderry|	United Kingdom|
|6|	Birmingham|	United Kingdom|
| ...|	...|	...|

`SELECT * FROM Airports`

Kết quả:

|id|name|code|city_id|
|---|---|---|---|
|183|	Belfast International Airport|	EGAA|	2|
|184|	St Angelo Airport|	EGAB|	3|
|185|	George Best Belfast City Airport|	EGAC|	2|
|186|	City of Derry Airport|	EGAE|	5|
|...|...|...|...|


**2. Tất cả tên thành phố trong bảng `Cities`, mỗi giá trị chỉ lấy 1 lần và sắp xếp theo thứ tự tăng dần**

`SELECT DISTINCT city FROM Cities ORDER BY city ASC`

Trong câu lệnh này:

**SELECT city:** Truy vấn cột `city`

**DISTINCT:** Chỉ lấy các giá trị một lần, loại bỏ các tên thành phố trùng lặp trong kết quả.

**FROM Cities:** Lấy từ bảng Cities

**ORDER BY city ASC:** Sắp xếp theo thứ tự tăng dần (A-Z).

Kết quả 1

**3. Tất cả các thành phố ở Ireland trong bảng `Cities`**

`SELECT city FROM Cities WHERE country = 'Ireland'`

Trong câu lệnh này:

**WHERE country = 'Ireland':** Chỉ lấy các thành phố ở Ireland.

Kết quả 2

**4. Tất cả tên sân bay cùng với thành phố và quốc gia của chúng**

`SELECT Airports.name, Cities.city, Cities.country

FROM Airports

INNER JOIN Cities ON Airports.city_id = Cities.id`

Trong câu lệnh này:

* **SELECT Airports.name, Cities.city, Cities.country:** Chọn các cột name từ bảng Airports, city và country từ bảng Cities.

* **FROM Airports:** Xác định bảng chính là Airports.

* **INNER JOIN Cities ON Airports.city_id = Cities.id:** Thực hiện phép nối giữa bảng Airports và Cities dựa trên điều kiện city_id trong bảng Airports khớp với id trong bảng Cities.

Kết quả:

| name | city | country |
|---|---|---|
| Belfast International Airport | Belfast |	United Kingdom |
| St Angelo Airport | Enniskillen | United Kingdom |
| George Best Belfast City Airport |	Belfast |	United Kingdom |
| City of Derry Airport	| Londonderry |	United Kingdom |
| ... | ... | ... |


**4. Tất cả các sân bay ở London, Vương quốc Anh**

`SELECT Airports.name

FROM Airports

INNER JOIN Cities ON Airports.city_id = Cities.id

WHERE cities.city = 'London'`

Kết quả:

|Airports|
|---|
|London Luton Airport|
|London Gatwick Airport|
|London City Airport|
|London Heathrow Airport|
|London Stansted Airport|
|London Heliport|

## Rubric - Thang điểm

| Exemplary - Mẫu mực | Adequate - Đạt yêu cầu | Needs Improvement - Cần cải thiện|
| --------- | -------- | ----------------- |
| Tạo đủ 4 truy vấn chính xác | Tạo được 2-3 truy vấn chính xác | Tạo được 1 truy vấn chính xác |
