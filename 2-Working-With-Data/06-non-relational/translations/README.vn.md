# Làm việc với Dữ liệu - dạng phi quan hệ (NoSQL)

![Sketchnote by [(@sketchthedocs)](https://sketchthedocs.dev)](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/sketchnotes/06-NoSQL.png)
|:---:|
|Working with NoSQL Data - _Sketchnote by [@nitya](https://twitter.com/nitya)_ |

## [Chuẩn bị trước bài giảng](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/10)

Dữ liệu không chỉ giới hạn ở cơ sở dữ liệu quan hệ. Bài học này sẽ tập trung vào dữ liệu không quan hệ và sẽ đề cập đến những điều cơ bản về **Bảng tính và NoSQL**.

## 1.Spreadsheets - Bảng tính

Bảng tính là một cách phổ biến để lưu trữ và khám phá dữ liệu vì nó đòi hỏi ít công sức hơn để thiết lập và bắt đầu. Trong bài học này, bạn sẽ tìm hiểu các thành phần cơ bản của bảng tính, cũng như các công thức và hàm. Các ví dụ sẽ được minh họa bằng Microsoft Excel, nhưng hầu hết các phần và chủ đề sẽ có tên và các bước tương tự khi so sánh với các phần mềm bảng tính khác. 

![An empty Microsoft Excel workbook with two worksheets](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/06-non-relational/images/parts-of-spreadsheet.png)

Bảng tính là một tệp và có thể truy cập được trong hệ thống tệp của máy tính, thiết bị hoặc hệ thống tệp dựa trên đám mây. Bản thân phần mềm có thể dựa trên trình duyệt hoặc là một ứng dụng phải được cài đặt trên máy tính hoặc tải xuống dưới dạng ứng dụng. Trong Excel, các tệp này cũng được định nghĩa là **sổ làm việc (Workbook)** và thuật ngữ này sẽ được sử dụng trong phần còn lại của bài học này.

Một sổ làm việc chứa một hoặc nhiều **trang tính (Sheet)** , trong đó mỗi trang tính được gắn nhãn bằng các tab. Trong một trang tính có các hình chữ nhật được gọi là **ô (Cell)** , sẽ chứa dữ liệu thực tế. Một ô là giao điểm của một hàng và cột, trong đó các cột được gắn nhãn bằng các ký tự chữ cái và các hàng được gắn nhãn bằng số. Một số bảng tính sẽ chứa các tiêu đề trong một vài hàng đầu tiên để mô tả dữ liệu trong một ô.

Với các thành phần cơ bản của bảng tính Excel, chúng ta sẽ sử dụng một ví dụ từ [Microsoft Templates](https://templates.office.com/) tập trung vào kiểm kê để xem xét một số phần bổ sung của bảng tính. 

**Ví dụ: Managing an Inventory - Quản lý hàng tồn kho**

Tệp bảng tính có tên "InventoryExample" là bảng tính được định dạng của các mục trong một kho chứa ba trang tính, trong đó các tab được gắn nhãn "Danh sách kho", "Danh sách chọn kho" và "Tra cứu thùng". Hàng 4 của trang tính Danh sách kho là tiêu đề, mô tả giá trị của từng ô trong cột tiêu đề.

![A highlighted formula from an example inventory list in Microsoft Excel](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/06-non-relational/images/formula-excel.png)

Có những trường hợp mà một ô phụ thuộc vào giá trị của các ô khác để tạo ra giá trị của nó. Bảng tính Inventory List theo dõi chi phí của mọi mặt hàng trong kho của nó, nhưng nếu chúng ta cần biết giá trị của mọi thứ trong kho thì sao? [**Công thức**](https://support.microsoft.com/en-us/office/overview-of-formulas-34519a4e-1e8d-4f4b-84d4-d642c4f63263) thực hiện các hành động trên dữ liệu ô và được sử dụng để tính chi phí của kho trong ví dụ này. Bảng tính này sử dụng một công thức trong cột Inventory Value để tính giá trị của từng mặt hàng bằng cách nhân số lượng dưới tiêu đề QTY và chi phí của nó với các ô dưới tiêu đề COST. Nhấp đúp hoặc tô sáng một ô sẽ hiển thị công thức. Bạn sẽ nhận thấy rằng các công thức bắt đầu bằng dấu bằng, theo sau là phép tính hoặc phép toán. 

![A highlighted function from an example inventory list in Microsoft Excel](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/06-non-relational/images/function-excel.png)

Chúng ta có thể sử dụng một công thức khác để cộng tất cả các giá trị của Inventory Value lại với nhau để có được tổng giá trị của nó. Điều này có thể được tính bằng cách cộng từng ô để tạo tổng, nhưng đó có thể là một nhiệm vụ tẻ nhạt. Excel có [**các hàm**](https://support.microsoft.com/en-us/office/sum-function-043e1c7d-7726-4e80-8f32-07b23e057f89), hoặc các công thức được xác định trước để thực hiện các phép tính trên các giá trị ô. Các hàm yêu cầu các đối số, là các giá trị bắt buộc được sử dụng để thực hiện các phép tính này. Khi các hàm yêu cầu nhiều hơn một đối số, chúng sẽ cần được liệt kê theo một thứ tự cụ thể hoặc hàm có thể không tính toán được giá trị chính xác. Ví dụ này sử dụng hàm SUM và sử dụng các giá trị của Inventory Value làm đối số để thêm tạo tổng được liệt kê dưới hàng 3, cột B (còn được gọi là B3).

## 2.NoSQL

NoSQL là thuật ngữ chung cho các cách khác nhau để lưu trữ dữ liệu phi quan hệ và có thể được hiểu là "phi SQL", "phi quan hệ" hoặc "không chỉ SQL". Các hệ thống cơ sở dữ liệu loại này có thể được phân loại thành 4 loại:
* Key-Value databases (Cơ sở dữ liệu dạng khóa-giá trị)
* Graph databases (Cơ sở dữ liệu đồ thị)
* Column-family databases (Cơ sở dữ liệu dạng cột)
* Document-based databases (Cơ sở dữ liệu dạng tài liệu)

**2.1.Key-value (dạng khóa - giá trị)**

[2.1.Key-value (dạng khóa - giá trị)](https://docs.microsoft.com/en-us/azure/architecture/data-guide/big-data/non-relational-data#keyvalue-data-stores) ghép cặp các khóa duy nhất, là một mã định danh duy nhất được liên kết với một giá trị. Các cặp này được lưu trữ bằng [hash table (bảng băm)](https://www.hackerearth.com/practice/data-structures/hash-tables/basics-of-hash-tables/tutorial/) có hàm băm thích hợp.

![Graphical representation of a key-value data store showing 4 unique numerical keys that are associated with 4 various values](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/06-non-relational/images/kv-db.png)

> Minh họa key - value: [Michał Białecki Blog](https://www.michalbialecki.com/2018/03/18/azure-cosmos-db-key-value-database-cloud/)

**2.2.Graph (dạng đồ thị)**

[2.2.Graph (dạng đồ thị)](https://docs.microsoft.com/en-us/azure/architecture/data-guide/big-data/non-relational-data#graph-data-stores) mô tả các mối quan hệ trong dữ liệu và được biểu diễn dưới dạng tập hợp các nút và đoạn nối (edge). Một nút biểu diễn một thực thể, một thứ tồn tại trong thế giới thực như sao kê của sinh viên hoặc ngân hàng. Các đoạn nối biểu diễn mối quan hệ giữa hai thực thể.

![Graphical representation of a graph data store showing the relationships between people, their interests and locations](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/06-non-relational/images/graph-db.png)

> Minh họa graph [Microsoft](https://docs.microsoft.com/en-us/azure/cosmos-db/graph/graph-introduction#graph-database-by-example)

**2.3.Columnar (dạng cột)**

[2.3.Columnar (dạng cột)](https://docs.microsoft.com/en-us/azure/architecture/data-guide/big-data/non-relational-data#columnar-data-stores) sắp xếp dữ liệu thành các cột và hàng giống như cấu trúc dữ liệu quan hệ nhưng mỗi cột được chia thành các nhóm gọi là họ cột, trong đó tất cả dữ liệu trong một cột có liên quan và có thể được truy xuất và thay đổi trong một đơn vị. 

![Graphical representation of a columnar data store showing a customer database with two column families named Identity and Contact Info](https://github.com/hoanglong8/Microsoft-DS-for-beginners/blob/main/2-Working-With-Data/06-non-relational/images/columnar-db.png)

**2.4.Document-based (dạng tài liệu)**

Dữ liệu được lưu trữ dưới dạng tài liệu (thường là JSON hoặc BSON) và các tài liệu này có thể chứa các trường dữ liệu khác nhau, như là: MongoDB, CouchDB...

**Ví dụ 1: Document Data Stores with the Azure Cosmos DB** 

[Document](https://docs.microsoft.com/en-us/azure/architecture/data-guide/big-data/non-relational-data#document-data-stores) được xây dựng dựa trên khái niệm kho dữ liệu khóa-giá trị và bao gồm một loạt các trường và đối tượng. Phần này sẽ khám phá cơ sở dữ liệu tài liệu với trình giả lập Cosmos DB.

Cơ sở dữ liệu Cosmos DB phù hợp với định nghĩa "Không SQL", trong đó cơ sở dữ liệu tài liệu của Cosmos DB dựa vào SQL để truy vấn dữ liệu. [Bài học 5.CSDL quan hệ](https://github.com/hoanglong8/Microsoft-DS-for-beginners/blob/main/2-Working-With-Data/05-relational-databases/README.md) đã bao gồm các kiến ​​thức cơ bản về ngôn ngữ này và chúng ta sẽ có thể áp dụng một số truy vấn tương tự vào cơ sở dữ liệu tài liệu tại đây. Chúng ta sẽ sử dụng Cosmos DB Emulator, cho phép chúng ta tạo và khám phá cơ sở dữ liệu tài liệu cục bộ trên máy tính. Đọc thêm về Emulator [tại đây](https://docs.microsoft.com/en-us/azure/cosmos-db/local-emulator?tabs=ssl-netstd21).

Tài liệu là tập hợp các trường và giá trị đối tượng, trong đó các trường mô tả giá trị đối tượng biểu diễn điều gì. Dưới đây là ví dụ về một tài liệu.

```json
{
    "firstname": "Eva",
    "age": 44,
    "id": "8c74a315-aebf-4a16-bb38-2430a9896ce5",
    "_rid": "bHwDAPQz8s0BAAAAAAAAAA==",
    "_self": "dbs/bHwDAA==/colls/bHwDAPQz8s0=/docs/bHwDAPQz8s0BAAAAAAAAAA==/",
    "_etag": "\"00000000-0000-0000-9f95-010a691e01d7\"",
    "_attachments": "attachments/",
    "_ts": 1630544034
}
```

Các trường quan tâm trong tài liệu này là: `firstname`, `id`, và `age`. Các trường còn lại có dấu gạch dưới được tạo bởi Cosmos DB.

**Ví dụ 2: Khám phá dữ liệu với Cosmos DB Emulator**

Bạn có thể tải xuống và cài đặt trình giả lập [for Windows here](https://aka.ms/cosmosdb-emulator). Tham khảo tài liệu [documentation](https://docs.microsoft.com/en-us/azure/cosmos-db/local-emulator?tabs=ssl-netstd21#run-on-linux-macos) này để biết các tùy chọn về cách chạy Trình giả lập cho macOS và Linux.

Trình giả lập sẽ mở một cửa sổ trình duyệt, tại đó chế độ xem Explorer cho phép bạn khám phá tài liệu.

![The Explorer view of the Cosmos DB Emulator](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/06-non-relational/images/cosmosdb-emulator-explorer.png)

Nếu bạn đang theo dõi, hãy nhấp vào "Bắt đầu với Sample" để tạo cơ sở dữ liệu mẫu có tên là SampleDB. Nếu bạn mở rộng Sample DB bằng cách nhấp vào mũi tên, bạn sẽ thấy một vùng chứa có tên là `Persons`, một vùng chứa chứa một bộ sưu tập các mục, là các tài liệu trong vùng chứa. Bạn có thể khám phá bốn tài liệu riêng lẻ trong `Items`.

![Exploring sample data in the Cosmos DB Emulator](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/06-non-relational/images/cosmosdb-emulator-persons.png)

**Ví dụ 3: Truy vấn dữ liệu tài liệu với Cosmos DB Emulator**

Chúng ta cũng có thể truy vấn dữ liệu mẫu bằng cách nhấp vào nút Truy vấn SQL mới (nút thứ hai từ bên trái).

`SELECT * FROM c` trả về tất cả các tài liệu trong vùng chứa. Hãy thêm một mệnh đề where và tìm tất cả những người dưới 40 tuổi.

`SELECT * FROM c where c.age < 40`

 ![Running a SELECT query on sample data in the Cosmos DB Emulator to find documents that have an age field value that is less than 40](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/06-non-relational/images/cosmosdb-emulator-persons-query.png)

Truy vấn trả về hai tài liệu, lưu ý giá trị độ tuổi của mỗi tài liệu đều nhỏ hơn 40.

**Ví dụ 4: JSON and Tài liệu**

Nếu bạn quen thuộc với JavaScript Object Notation (JSON), bạn sẽ thấy rằng các tài liệu trông giống với JSON. Có một `PersonsData.json` tệp trong thư mục này với nhiều dữ liệu hơn mà bạn có thể tải lên vùng chứa Persons trong Emulator thông qua `Upload Item` nút.

Trong hầu hết các trường hợp, API trả về dữ liệu JSON có thể được chuyển trực tiếp và lưu trữ trong cơ sở dữ liệu tài liệu. Dưới đây là một tài liệu khác, nó đại diện cho các tweet từ tài khoản Twitter của Microsoft được truy xuất bằng API Twitter, sau đó được chèn vào Cosmos DB.

```json
{
    "created_at": "2021-08-31T19:03:01.000Z",
    "id": "1432780985872142341",
    "text": "Blank slate. Like this tweet if you’ve ever painted in Microsoft Paint before. https://t.co/cFeEs8eOPK",
    "_rid": "dhAmAIUsA4oHAAAAAAAAAA==",
    "_self": "dbs/dhAmAA==/colls/dhAmAIUsA4o=/docs/dhAmAIUsA4oHAAAAAAAAAA==/",
    "_etag": "\"00000000-0000-0000-9f84-a0958ad901d7\"",
    "_attachments": "attachments/",
    "_ts": 1630537000
```

Các thành phần khác trong tài liệu này là: `created_at`, `id`, and `text`.

## 🚀 Challenge - Thử thách


Có một `TwitterData.json` tệp mà bạn có thể tải lên cơ sở dữ liệu SampleDB. Bạn nên thêm tệp đó vào một vùng chứa riêng. Bạn có thể thực hiện việc này bằng cách:

* Nhấp vào nút vùng chứa mới ở trên cùng bên phải
* Chọn cơ sở dữ liệu hiện có (SampleDB) tạo ID vùng chứa cho vùng chứa
* Đặt khóa phân vùng thành `/id`
* Nhấp vào OK (bạn có thể bỏ qua phần thông tin còn lại trong chế độ xem này vì đây là một tập dữ liệu nhỏ chạy cục bộ trên máy của bạn)
Mở container mới của bạn và tải tệp Dữ liệu Twitter lên bằng nút `Upload Item`.

Hãy thử chạy một vài truy vấn chọn lọc để tìm các tài liệu có Microsoft trong trường văn bản. Gợi ý: hãy thử sử dụng [LIKE keyword](https://docs.microsoft.com/en-us/azure/cosmos-db/sql/sql-query-keywords#using-like-with-the--wildcard-character)


## [Kiểm tra sau bài giảng](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/11)



## Review & Self Study - Đánh giá và tự học

- Có một số định dạng và tính năng bổ sung được thêm vào bảng tính này mà bài học này không đề cập đến. Microsoft có một [large library of documentation and videos](https://support.microsoft.com/excel) về Excel nếu bạn muốn tìm hiểu thêm.

- Tài liệu kiến ​​trúc này trình bày chi tiết các đặc điểm trong các loại dữ liệu phi quan hệ khác nhau: [Non-relational Data and NoSQL](https://docs.microsoft.com/en-us/azure/architecture/data-guide/big-data/non-relational-data)

- Cosmos DB là một cơ sở dữ liệu phi quan hệ dựa trên đám mây cũng có thể lưu trữ các loại NoSQL khác nhau được đề cập trong bài học này. Tìm hiểu thêm về các loại này trong [Cosmos DB Microsoft Learn Module](https://docs.microsoft.com/en-us/learn/paths/work-with-nosql-data-in-azure-cosmos-db/)

## Assignment - Bài tập thực hành

[Dữ liệu lợi nhuận của Công ty Soda](https://github.com/hoanglong8/Microsoft-DS-for-beginners/blob/main/2-Working-With-Data/06-non-relational/assignment.md)
