# Displaying airport data - Làm việc với cơ sở dữ liệu về các sân bay

Bạn đã được cung cấp một [database](https://raw.githubusercontent.com/Microsoft/Data-Science-For-Beginners/main/2-Working-With-Data/05-relational-databases/airports.db) được xây dựng trên [SQLite](https://sqlite.org/index.html) chứa thông tin về các sân bay. Sơ đồ được hiển thị bên dưới. Bạn sẽ sử dụng [SQLite extension](https://marketplace.visualstudio.com/items?itemName=alexcvzz.vscode-sqlite&WT.mc_id=academic-77958-bethanycheum) trong [Visual Studio Code](https://code.visualstudio.com?WT.mc_id=academic-77958-bethanycheum) để hiển thị thông tin về các sân bay của các thành phố khác nhau.

## Instructions - Hướng dẫn

Để bắt đầu bài tập, bạn sẽ cần thực hiện một vài bước. Bạn sẽ cần cài đặt một số công cụ và tải xuống cơ sở dữ liệu mẫu.

### Setup your system - Thiết lập hệ thống của bạn

Bạn có thể sử dụng Visual Studio Code và tiện ích mở rộng SQLite để tương tác với cơ sở dữ liệu.

1. Truy cập [code.visualstudio.com](https://code.visualstudio.com?WT.mc_id=academic-77958-bethanycheum) và làm theo hướng dẫn để cài đặt Visual Studio Code.
1. Cài đặt [SQLite extension](https://marketplace.visualstudio.com/items?itemName=alexcvzz.vscode-sqlite&WT.mc_id=academic-77958-bethanycheum) theo hướng dẫn trên trang Marketplace.

### Download and open the database - Tải xuống và mở cơ sở dữ liệu

Tiếp theo bạn sẽ tải xuống và mở cơ sở dữ liệu.

1. Download [database file from GitHub](https://raw.githubusercontent.com/Microsoft/Data-Science-For-Beginners/main/2-Working-With-Data/05-relational-databases/airports.db) và lưu vào một thư mục.
2. Mở Visual Studio Code
3. Mở cơ sở dữ liệu trong phần mở rộng SQLite bằng cách chọn **Ctl-Shift-P** (hoặc **Cmd-Shift-P** trên máy Mac) và nhập `SQLite: Open database`
4. Chọn **cơ sở dữ liệu từ tệp** và mở tệp `airports.db` mà bạn đã tải xuống trước đó
5. Sau khi mở cơ sở dữ liệu (bạn sẽ không thấy bản cập nhật trên màn hình), hãy tạo một cửa sổ truy vấn mới bằng cách chọn **Ctl-Shift-P** (hoặc **Cmd-Shift-P** trên máy Mac) và nhập `SQLite: New query`

Sau khi mở, cửa sổ truy vấn mới có thể được sử dụng để chạy các câu lệnh SQL đối với cơ sở dữ liệu. Bạn có thể sử dụng lệnh **Ctl-Shift-Q** (hoặc **Cmd-Shift-Q** trên máy Mac) để chạy các truy vấn đối với cơ sở dữ liệu.

> [!NOTE] Để biết thêm thông tin về tiện ích mở rộng SQLite, bạn có thể tham khảo [tài liệu](https://marketplace.visualstudio.com/items?itemName=alexcvzz.vscode-sqlite&WT.mc_id=academic-77958-bethanycheum)

## Database schema

A database's schema is its table design and structure. The **airports** database as two tables, `cities`, which contains a list of cities in the United Kingdom and Ireland, and `airports`, which contains the list of all airports. Because some cities may have multiple airports, two tables were created to store the information. In this exercise you will use joins to display information for different cities.

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

## Assignment

Create queries to return the following information:

1. all city names in the `Cities` table
1. all cities in Ireland in the `Cities` table
1. all airport names with their city and country
1. all airports in London, United Kingdom

## Rubric

| Exemplary | Adequate | Needs Improvement |
| --------- | -------- | ----------------- |
