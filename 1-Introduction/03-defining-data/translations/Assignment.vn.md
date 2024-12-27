# Classifying Datasets - Phân loại tập dữ liệu

## Instructions (Hướng dẫn)

Thực hiện theo các hướng dẫn trong bài tập này để xác định và phân loại dữ liệu theo một trong các kiểu dữ liệu sau:

* **Theo cấu trúc:** Có cấu trúc, Bán cấu trúc hoặc Không có cấu trúc.

* **Theo loại giá trị:** Định tính hoặc định lượng.

* **Theo loại nguồn gốc:** Sơ cấp (Primary) hoặc thứ cấp (Secondary).

**1. Bảng thông tin khách hàng**

Một công ty đã được mua lại và hiện có công ty mẹ. Các nhà khoa học dữ liệu đã nhận được bảng tính số điện thoại khách hàng từ công ty mẹ.

![Hình ảnh](https://blog.slimcrm.vn/sites/default/files/inline/images/mau-quan-ly-thong-tin-khach-hang-bang-excel-5.jpg)

Dataset 1: [Global Customer Demographics and Registration Data](https://www.kaggle.com/datasets/sitaramaraju789/global-customer-demographics-and-registration-data) 

Dataset 2: [Phone Book Dataset](https://www.kaggle.com/datasets/vidyaargade/phonebookdataset)

Structure Type (Loại cấu trúc): **Có cấu trúc** vì dataset này được tổ chức thông tin theo hàng và cột, với mỗi cột đại diện cho một thuộc tính (như số điện thoại, tên khách hàng, địa chỉ, v.v.), giúp dễ dàng truy cập và phân tích.

Value Type (Loại giá trị): Mặc dù số điện thoại chứa các chữ số, chúng được coi là dữ liệu **định tính** (dữ liệu dạng văn bản) vì không tham gia vào các phép tính toán học. Trong Excel, số điện thoại thường được định dạng dưới dạng văn bản để giữ nguyên các ký tự đặc biệt hoặc số 0 ở đầu.

Source Type (Loại nguồn): Dữ liệu này được thu thập ban đầu bởi công ty mẹ và sau đó chia sẻ với công ty con, do đó được coi là **dữ liệu thứ cấp**.

---

**2. Dữ liệu nhịp tim của một người**

Một chiếc đồng hồ thông minh đã thu thập dữ liệu nhịp tim từ người đeo và dữ liệu thô có định dạng JSON.

![Hình ảnh](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/blob/main/1-Introduction/03-defining-data/translations/Heartbeat_json.png)

Dataset 1: [Heart Rate Prediction](https://www.kaggle.com/datasets/saurav9786/heart-rate-prediction?utm_source=chatgpt.com)

Dataset 2: [ECG Heartbeat Categorization Dataset](https://www.kaggle.com/datasets/shayanfazeli/heartbeat?utm_source=chatgpt.com)

Dataset 3: [MIT-BIH Arrhythmia Database](https://www.kaggle.com/datasets/protobioengineering/mit-bih-arrhythmia-database-modern-2023?utm_source=chatgpt.com)

Structure Type (Loại cấu trúc): JSON tổ chức dữ liệu **theo cấu trúc rõ ràng** với các cặp khóa-giá trị, giúp dễ dàng truy cập và phân tích.

Value Type (Loại giá trị): **Định lượng** vì nhịp tim được biểu thị bằng số lần đập mỗi phút (bpm), là dữ liệu số học phản ánh các phép đo lường cụ thể.

Source Type (Loại nguồn): Dữ liệu này được thu thập trực tiếp từ thiết bị đeo của người dùng, không qua trung gian, nên được coi là **dữ liệu sơ cấp**.

---

**3. Khảo sát tinh thần làm việc của nhân viên được lưu trữ trong tệp CSV.**

![Hình ảnh](https://miro.medium.com/v2/resize:fit:612/1*DfJ6Dkxdg2wiQ0Vb0rfCcg.jpeg)

![Hình ảnh](https://kpim.vn/wp-content/uploads/2020/08/1-1.png)

Dataset 1: [Employee Engagement Survey](https://www.kaggle.com/datasets/thekischt/ai-performance)

Dataset 2: [Employee Survey Data](https://www.kaggle.com/datasets/pmenshih/statistical-data-mbti-of-33k-retail-salespeople)

Structure Type (Loại cấu trúc): **Có cấu trúc** vì tệp CSV (Comma-Separated Values) lưu trữ dữ liệu dưới dạng bảng với các hàng và cột, mỗi cột đại diện cho một thuộc tính (ví dụ: mức độ hài lòng, động lực làm việc), giúp dễ dàng truy cập và phân tích.

Value Type (Loại giá trị): Khảo sát về tinh thần làm việc thường bao gồm cả **dữ liệu định tính** (như phản hồi mở về môi trường làm việc) và **dữ liệu định lượng** (như điểm số đánh giá mức độ hài lòng trên thang điểm).

Source Type (Loại nguồn): Dữ liệu này được thu thập trực tiếp từ nhân viên thông qua khảo sát, không qua trung gian, nên được coi là **dữ liệu sơ cấp**.

---

**4. Dữ liệu số lượng hành tinh trong mỗi thiên hà**

Các nhà vật lý thiên văn đang truy cập vào cơ sở dữ liệu về các thiên hà được thu thập bởi một tàu thăm dò không gian. Dữ liệu chứa số lượng hành tinh trong mỗi thiên hà.

Structure Type (Loại cấu trúc): **Có cấu trúc** vì Dataset này được tổ chức thông tin theo các bảng với các hàng và cột, mỗi cột đại diện cho một thuộc tính (ví dụ: tên thiên hà, số lượng hành tinh), giúp dễ dàng truy cập và phân tích.

Value Type (Loại giá trị): **Định lượng** vì số lượng hành tinh là dữ liệu số học, phản ánh mức độ và có thể tính toán giá trị trung bình, tổng, v.v.

Source Type (Loại nguồn): Dữ liệu này được thu thập trực tiếp từ tàu thăm dò không gian, không qua trung gian, nên được coi là **dữ liệu sơ cấp**.

---

5. Ứng dụng tài chính cá nhân sử dụng API để kết nối với tài khoản tài chính của người dùng nhằm tính giá trị tài sản ròng của họ. Họ có thể xem tất cả các giao dịch của mình theo định dạng hàng và cột và trông giống như bảng tính.

Structure Type (Loại cấu trúc):

Value Type (Loại giá trị): 

Source Type (Loại nguồn):

## Rubric - Thang chấm điểm

Exemplary - Mẫu mực | Adequate - Đạt yêu cầu | Needs Improvement - Cần cải thiện
--- | --- | -- |
Xác định chính xác tất cả các cấu trúc, giá trị và nguồn |Xác định đúng 3 cấu trúc, giá trị và nguồn|Xác định đúng 2 hoặc ít hơn tất cả các cấu trúc, giá trị và nguồn|
