# Làm việc với Dữ liệu - dạng phi quan hệ (NoSQL)

![Sketchnote by [(@sketchthedocs)](https://sketchthedocs.dev)](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/sketchnotes/06-NoSQL.png)
|:---:|
|Working with NoSQL Data - _Sketchnote by [@nitya](https://twitter.com/nitya)_ |

## [Chuẩn bị trước bài giảng](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/10)

Dữ liệu không chỉ giới hạn ở cơ sở dữ liệu quan hệ. Bài học này sẽ tập trung vào dữ liệu không quan hệ và sẽ đề cập đến những điều cơ bản về bảng tính và NoSQL.

## Spreadsheets - Bảng tính

Bảng tính là một cách phổ biến để lưu trữ và khám phá dữ liệu vì nó đòi hỏi ít công sức hơn để thiết lập và bắt đầu. Trong bài học này, bạn sẽ tìm hiểu các thành phần cơ bản của bảng tính, cũng như các công thức và hàm. Các ví dụ sẽ được minh họa bằng Microsoft Excel, nhưng hầu hết các phần và chủ đề sẽ có tên và các bước tương tự khi so sánh với các phần mềm bảng tính khác. 

![An empty Microsoft Excel workbook with two worksheets](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/06-non-relational/images/parts-of-spreadsheet.png)

Bảng tính là một tệp và có thể truy cập được trong hệ thống tệp của máy tính, thiết bị hoặc hệ thống tệp dựa trên đám mây. Bản thân phần mềm có thể dựa trên trình duyệt hoặc là một ứng dụng phải được cài đặt trên máy tính hoặc tải xuống dưới dạng ứng dụng. Trong Excel, các tệp này cũng được định nghĩa là **sổ làm việc (Workbook)** và thuật ngữ này sẽ được sử dụng trong phần còn lại của bài học này.

Một sổ làm việc chứa một hoặc nhiều **trang tính (Sheet)** , trong đó mỗi trang tính được gắn nhãn bằng các tab. Trong một trang tính có các hình chữ nhật được gọi là **ô (Cell)** , sẽ chứa dữ liệu thực tế. Một ô là giao điểm của một hàng và cột, trong đó các cột được gắn nhãn bằng các ký tự chữ cái và các hàng được gắn nhãn bằng số. Một số bảng tính sẽ chứa các tiêu đề trong một vài hàng đầu tiên để mô tả dữ liệu trong một ô.

Với các thành phần cơ bản của bảng tính Excel, chúng ta sẽ sử dụng một ví dụ từ [Microsoft Templates](https://templates.office.com/) tập trung vào kiểm kê để xem xét một số phần bổ sung của bảng tính. 

### Managing an Inventory - Quản lý hàng tồn kho

Tệp bảng tính có tên "InventoryExample" là bảng tính được định dạng của các mục trong một kho chứa ba trang tính, trong đó các tab được gắn nhãn "Danh sách kho", "Danh sách chọn kho" và "Tra cứu thùng". Hàng 4 của trang tính Danh sách kho là tiêu đề, mô tả giá trị của từng ô trong cột tiêu đề.

![A highlighted formula from an example inventory list in Microsoft Excel](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/06-non-relational/images/formula-excel.png)

Có những trường hợp mà một ô phụ thuộc vào giá trị của các ô khác để tạo ra giá trị của nó. Bảng tính Inventory List theo dõi chi phí của mọi mặt hàng trong kho của nó, nhưng nếu chúng ta cần biết giá trị của mọi thứ trong kho thì sao? [**Công thức**](https://support.microsoft.com/en-us/office/overview-of-formulas-34519a4e-1e8d-4f4b-84d4-d642c4f63263) thực hiện các hành động trên dữ liệu ô và được sử dụng để tính chi phí của kho trong ví dụ này. Bảng tính này sử dụng một công thức trong cột Inventory Value để tính giá trị của từng mặt hàng bằng cách nhân số lượng dưới tiêu đề QTY và chi phí của nó với các ô dưới tiêu đề COST. Nhấp đúp hoặc tô sáng một ô sẽ hiển thị công thức. Bạn sẽ nhận thấy rằng các công thức bắt đầu bằng dấu bằng, theo sau là phép tính hoặc phép toán. 

![A highlighted function from an example inventory list in Microsoft Excel](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/06-non-relational/images/function-excel.png)

Chúng ta có thể sử dụng một công thức khác để cộng tất cả các giá trị của Inventory Value lại với nhau để có được tổng giá trị của nó. Điều này có thể được tính bằng cách cộng từng ô để tạo tổng, nhưng đó có thể là một nhiệm vụ tẻ nhạt. Excel có [**các hàm**](https://support.microsoft.com/en-us/office/sum-function-043e1c7d-7726-4e80-8f32-07b23e057f89), hoặc các công thức được xác định trước để thực hiện các phép tính trên các giá trị ô. Các hàm yêu cầu các đối số, là các giá trị bắt buộc được sử dụng để thực hiện các phép tính này. Khi các hàm yêu cầu nhiều hơn một đối số, chúng sẽ cần được liệt kê theo một thứ tự cụ thể hoặc hàm có thể không tính toán được giá trị chính xác. Ví dụ này sử dụng hàm SUM và sử dụng các giá trị của Inventory Value làm đối số để thêm tạo tổng được liệt kê dưới hàng 3, cột B (còn được gọi là B3).

## NoSQL

NoSQL là thuật ngữ chung cho các cách khác nhau để lưu trữ dữ liệu phi quan hệ và có thể được hiểu là "phi SQL", "phi quan hệ" hoặc "không chỉ SQL". Các hệ thống cơ sở dữ liệu loại này có thể được phân loại thành 4 loại:

![Graphical representation of a key-value data store showing 4 unique numerical keys that are associated with 4 various values](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/06-non-relational/images/kv-db.png)

> Minh họa key - value: [Michał Białecki Blog](https://www.michalbialecki.com/2018/03/18/azure-cosmos-db-key-value-database-cloud/)

* [Key-value (dạng khóa - giá trị)](https://docs.microsoft.com/en-us/azure/architecture/data-guide/big-data/non-relational-data#keyvalue-data-stores) ghép cặp các khóa duy nhất, là một mã định danh duy nhất được liên kết với một giá trị. Các cặp này được lưu trữ bằng [hash table (bảng băm)](https://www.hackerearth.com/practice/data-structures/hash-tables/basics-of-hash-tables/tutorial/) có hàm băm thích hợp.

![Graphical representation of a graph data store showing the relationships between people, their interests and locations](https://github.com/hoanglong8/Microsoft-DS-for-beginners/raw/main/2-Working-With-Data/06-non-relational/images/graph-db.png)

> Minh họa graph [Microsoft](https://docs.microsoft.com/en-us/azure/cosmos-db/graph/graph-introduction#graph-database-by-example)

* [Graph (dạng đồ thị)](https://docs.microsoft.com/en-us/azure/architecture/data-guide/big-data/non-relational-data#graph-data-stores) mô tả các mối quan hệ trong dữ liệu và được biểu diễn dưới dạng tập hợp các nút và đoạn nối (edge). Một nút biểu diễn một thực thể, một thứ tồn tại trong thế giới thực như sao kê của sinh viên hoặc ngân hàng. Các đoạn nối biểu diễn mối quan hệ giữa hai thực thể.

![Graphical representation of a columnar data store showing a customer database with two column families named Identity and Contact Info](images/columnar-db.png)

[Columnar](https://docs.microsoft.com/en-us/azure/architecture/data-guide/big-data/non-relational-data#columnar-data-stores) data stores organizes data into columns and rows like a relational data structure but each column is divided into groups called a column family, where all the data under one column is related and can be retrieved and changed in one unit. 


### Document Data Stores with the Azure Cosmos DB 

[Document](https://docs.microsoft.com/en-us/azure/architecture/data-guide/big-data/non-relational-data#document-data-stores) data stores build on the concept of a key-value data store and is made up of a series of fields and objects. This section will explore document databases with the Cosmos DB emulator. 

A Cosmos DB database fits the definition of "Not Only SQL", where Cosmos DB's document database relies on SQL to query the data. The [previous lesson](../05-relational-databases/README.md) on SQL covers the basics of the language, and we'll be able to apply some of the same queries to a document database here. We'll be using the Cosmos DB Emulator, which allows us to create and explore a document database locally on a computer. Read more about the Emulator [here](https://docs.microsoft.com/en-us/azure/cosmos-db/local-emulator?tabs=ssl-netstd21).

A document is a collection of fields and object values, where the fields describe what the object value represents. Below is an example of a document.

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

The fields of interest in this document are: `firstname`, `id`, and `age`. The rest of the fields with the underscores were generated by Cosmos DB.

#### Exploring Data with the Cosmos DB Emulator

You can download and install the emulator [for Windows here](https://aka.ms/cosmosdb-emulator). Refer to this [documentation](https://docs.microsoft.com/en-us/azure/cosmos-db/local-emulator?tabs=ssl-netstd21#run-on-linux-macos) for options on how to run the Emulator for macOS and Linux.

The Emulator launches a browser window, where the Explorer view allows you to explore documents.

![The Explorer view of the Cosmos DB Emulator](images/cosmosdb-emulator-explorer.png)

If you're following along, click on "Start with Sample" to generate a sample database called SampleDB. If you expand Sample DB by clicking on the arrow you'll find a container called `Persons`, a container holds a collection of items, which are the documents within the container. You can explore the four individual documents under `Items`. 

![Exploring sample data in the Cosmos DB Emulator](images/cosmosdb-emulator-persons.png)

#### Querying Document Data with the Cosmos DB Emulator

We can also query the sample data by clicking on the new SQL Query button (second button from the left).

`SELECT * FROM c` returns all the documents in the container. Let's add a where clause and find everyone younger than 40.

`SELECT * FROM c where c.age < 40`

 ![Running a SELECT query on sample data in the Cosmos DB Emulator to find documents that have an age field value that is less than 40](images/cosmosdb-emulator-persons-query.png)

The query returns two documents, notice the age value for each document is less than 40.

#### JSON and Documents

If you're familiar with JavaScript Object Notation (JSON) you'll notice that documents look similar to JSON. There is a `PersonsData.json` file in this directory with more data that you may upload to the Persons container in the Emulator via the `Upload Item` button.

In most instances, APIs that return JSON data can be directly transferred and stored in document databases. Below is another document, it represents tweets from the Microsoft Twitter account that was retrieved using the Twitter API, then inserted into Cosmos DB.

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

The fields of interest in this document are: `created_at`, `id`, and `text`.

## 🚀 Challenge


There is a `TwitterData.json` file that you can upload to the SampleDB database. It's recommended that you add it to a separate container. This can be done by:

1. Clicking the new container button in the top right
1. Selecting the existing database (SampleDB) creating a container id for the container
1. Setting the partition key to `/id`
1. Clicking OK (you can ignore rest of the information in this view as this is a small dataset running locally on your machine)
1. Open your new container and upload the Twitter Data file with `Upload Item` button

Try to run a few select queries to find the documents that have Microsoft in the text field. Hint: try to use the [LIKE keyword](https://docs.microsoft.com/en-us/azure/cosmos-db/sql/sql-query-keywords#using-like-with-the--wildcard-character)


## [Post-Lecture Quiz](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/11)



## Review & Self Study

- There are some additional formatting and features added to this spreadsheet that this lesson does not cover. Microsoft has a [large library of documentation and videos](https://support.microsoft.com/excel) on Excel if you're interested in learning more.

- This architectural documentation details the characteristics in the different types of non-relational data: [Non-relational Data and NoSQL](https://docs.microsoft.com/en-us/azure/architecture/data-guide/big-data/non-relational-data)

- Cosmos DB is a cloud based non-relational database that can also store the different NoSQL types mentioned in this lesson. Learn more about these types in this [Cosmos DB Microsoft Learn Module](https://docs.microsoft.com/en-us/learn/paths/work-with-nosql-data-in-azure-cosmos-db/)

## Assignment

[Soda Profits](assignment.md)
