# Đạo đức trong Khoa học dữ liệu

![Sketchnote by [(@sketchthedocs)](https://sketchthedocs.dev)](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/raw/main/sketchnotes/02-Ethics.png)
|:---:|
| Data Science Ethics - _Sketchnote by [@nitya](https://twitter.com/nitya)_ |

---

Chúng ta đều là công dân dữ liệu sống trong thế giới dữ liệu hóa.

Xu hướng thị trường cho chúng ta biết rằng đến năm 2022, 1/3 các tổ chức lớn sẽ mua và bán dữ liệu của họ thông qua [Marketplaces and Exchanges - sàn giao dịch](https://www.gartner.com/smarterwithgartner/gartner-top-10-trends-in-data-and-analytics-for-2020/) trực tuyến. Với vai trò **Nhà phát triển ứng dụng**, chúng ta sẽ thấy việc tích hợp thông tin chi tiết dựa trên dữ liệu và tự động hóa dựa trên thuật toán vào trải nghiệm người dùng hàng ngày dễ dàng và rẻ hơn. Nhưng khi AI trở nên phổ biến, chúng ta cũng cần hiểu những tác hại tiềm ẩn do việc [weaponization - vũ trang hóa](https://www.youtube.com/watch?v=TQHs8SA1qpk) các thuật toán như vậy ở quy mô lớn gây ra.

Xu hướng cũng chỉ ra rằng chúng ta sẽ tạo ra và tiêu thụ hơn [180 zettabytes](https://www.statista.com/statistics/871513/worldwide-data-created/) dữ liệu vào năm 2025. Với vai trò **Nhà khoa học dữ liệu**, điều này mang lại cho chúng ta mức độ truy cập chưa từng có vào dữ liệu cá nhân. Điều này có nghĩa là chúng ta có thể xây dựng hồ sơ hành vi của người dùng và tác động đến việc ra quyết định theo những cách tạo ra [ảo tưởng của sự lựa chọn](https://www.datasciencecentral.com/profiles/blogs/the-illusion-of-choice) trong khi có khả năng thúc đẩy người dùng hướng đến kết quả mà chúng ta mong muốn. Nó cũng đặt ra những câu hỏi rộng hơn về quyền riêng tư dữ liệu và bảo vệ người dùng.

Đạo đức dữ liệu hiện là rào cản cần thiết cho khoa học dữ liệu và kỹ thuật, giúp chúng ta giảm thiểu những tác hại tiềm ẩn và hậu quả không mong muốn từ các hành động dựa trên dữ liệu của mình. Chu trình [Cường điệu hóa AI của Gartner](https://www.gartner.com/smarterwithgartner/2-megatrends-dominate-the-gartner-hype-cycle-for-artificial-intelligence-2020/) xác định các xu hướng có liên quan trong đạo đức kỹ thuật số, AI có trách nhiệm và quản trị AI là những động lực chính cho các xu hướng lớn hơn xung quanh dân chủ hóa và công nghiệp hóa AI.

![Gartner's Hype Cycle for AI - 2020](https://images-cdn.newscred.com/Zz1mOWJhNzlkNDA2ZTMxMWViYjRiOGFiM2IyMjQ1YmMwZQ==)

Trong bài học này, chúng ta sẽ khám phá lĩnh vực đạo đức dữ liệu - từ các khái niệm và thách thức cốt lõi, đến các nghiên cứu tình huống (case-study) và khái niệm AI ứng dụng như quản trị - giúp thiết lập văn hóa đạo đức trong các nhóm/tổ chức làm việc với dữ liệu + AI.



## [Câu hỏi chuẩn bị trước bài giảng](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/2) 🎯

## Khái niệm cơ bản

Chúng ta hãy bắt đầu bằng cách hiểu các thuật ngữ cơ bản.

Từ "đạo đức" xuất phát từ ["ethikos" trong tiếng Hy Lạp](https://en.wikipedia.org/wiki/Ethics) (gốc từ "ethos") có nghĩa là tính cách hoặc bản chất đạo đức .

**Đạo đức** là về các giá trị chung và các nguyên tắc đạo đức chi phối hành vi của chúng ta trong xã hội. Đạo đức không dựa trên luật pháp mà dựa trên các chuẩn mực được chấp nhận rộng rãi về điều gì là "đúng so với sai". Tuy nhiên, các cân nhắc về đạo đức có thể ảnh hưởng đến các sáng kiến ​​quản trị doanh nghiệp và các quy định của chính phủ tạo ra nhiều động lực hơn để tuân thủ.

**Đạo đức khoa học dữ liệu** là một [nhánh của Đạo đức học](https://royalsocietypublishing.org/doi/full/10.1098/rsta.2016.0360#sec-1) "nghiên cứu và đánh giá các vấn đề đạo đức liên quan đến dữ liệu, thuật toán và các hoạt động tương ứng ". Ở đây, "dữ liệu" tập trung vào các hành động liên quan đến việc tạo, ghi lại, quản lý, xử lý, phổ biến, chia sẻ và sử dụng, "thuật toán" tập trung vào AI, tác nhân, máy học và rô-bốt, và "thực hành" tập trung vào các chủ đề như đổi mới có trách nhiệm, lập trình, hack và các quy tắc đạo đức.

**Vận dụng Đạo đức** là [ứng dụng đạo đức vào thực tế](https://en.wikipedia.org/wiki/Applied_ethics). Đó là quá trình chủ động điều tra các vấn đề đạo đức trong bối cảnh các hành động, sản phẩm và quy trình trong thế giới thực , và thực hiện các biện pháp khắc phục để đảm bảo chúng phù hợp với các giá trị đạo đức đã xác định của chúng tôi.

**Văn hóa đạo đức** là về [việc thực hành các quy tắc đạo đức](https://hbr.org/2019/05/how-to-design-an-ethical-organization) để đảm bảo rằng các nguyên tắc và thực hành đạo đức của chúng ta được áp dụng theo cách nhất quán và có thể mở rộng trên toàn bộ tổ chức. Văn hóa đạo đức thành công xác định các nguyên tắc đạo đức trên toàn tổ chức, cung cấp các động lực có ý nghĩa để tuân thủ và củng cố các chuẩn mực đạo đức bằng cách khuyến khích và khuếch đại các hành vi mong muốn ở mọi cấp độ của tổ chức.


## Khái niệm Đạo đức

Trong phần này, chúng ta sẽ thảo luận về các khái niệm như giá trị chung (nguyên tắc) và thách thức về mặt đạo đức (vấn đề) đối với đạo đức dữ liệu - và khám phá các nghiên cứu điển hình giúp bạn hiểu các khái niệm này trong bối cảnh thực tế.

### 1. Nguyên tắc đạo đức - Ethics Principles
Mọi chiến lược đạo đức dữ liệu đều bắt đầu bằng việc xác định các nguyên tắc đạo đức - "các giá trị chung" mô tả các hành vi có thể chấp nhận được và hướng dẫn các hành động tuân thủ trong các dự án dữ liệu & AI của chúng tôi. Bạn có thể xác định những điều này ở cấp độ cá nhân hoặc nhóm. Tuy nhiên, hầu hết các tổ chức lớn đều phác thảo những điều này trong một tuyên bố sứ mệnh hoặc khuôn khổ đạo đức AI được xác định ở cấp độ công ty và được thực thi nhất quán trên tất cả các nhóm.

Ví dụ: Tuyên bố của Microsoft về [nghĩa vụ của AI](https://www.microsoft.com/en-us/ai/responsible-ai) của Microsoft có nội dung: "Chúng tôi cam kết phát triển AI theo các nguyên tắc đạo đức đặt con người lên hàng đầu" - xác định 6 nguyên tắc đạo đức trong khuôn khổ bên dưới:

![Responsible AI at Microsoft](https://docs.microsoft.com/en-gb/azure/cognitive-services/personalizer/media/ethics-and-responsible-use/ai-values-future-computed.png)

Chúng ta hãy cùng khám phá những nguyên tắc này một cách ngắn gọn. Tính minh bạch và trách nhiệm giải trình là những giá trị nền tảng mà các nguyên tắc khác xây dựng dựa trên - vì vậy chúng ta hãy bắt đầu từ đó:

* [**Accountability - Trách nhiệm**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) khiến người thực hành phải chịu trách nhiệm về dữ liệu và hoạt động AI của mình, cũng như việc tuân thủ các nguyên tắc đạo đức này.
* [**Transparency - Minh bạch**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) đảm bảo rằng dữ liệu và hành động của AI có thể hiểu được (diễn giải được) đối với người dùng, giải thích mục đích và lý do đằng sau các quyết định.
* [**Fairness - Công bằng**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1%3aprimaryr6) tập trung vào việc đảm bảo AI đối xử công bằng với mọi người , giải quyết mọi thành kiến ​​xã hội - kỹ thuật có hệ thống hoặc tiềm ẩn trong dữ liệu và hệ thống.
* [**Reliability & Safety - An toàn và tin cậy**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) đảm bảo AI hoạt động nhất quán với các giá trị đã xác định, giảm thiểu tác hại tiềm ẩn hoặc hậu quả không mong muốn.
* [**Privacy & Security - Quyền riêng tư và bảo mật**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) là về việc hiểu nguồn gốc dữ liệu và cung cấp quyền riêng tư dữ liệu cùng các biện pháp bảo vệ liên quan cho người dùng.
* [**Inclusiveness - Toàn diện**](https://www.microsoft.com/en-us/ai/responsible-ai?activetab=pivot1:primaryr6) là về việc thiết kế các giải pháp AI có chủ đích, điều chỉnh chúng để đáp ứng nhiều nhu cầu và khả năng khác nhau của con người.

> 🚨 Hãy nghĩ về tuyên bố sứ mệnh đạo đức dữ liệu của bạn có thể là gì. Khám phá các khuôn khổ AI đạo đức từ các tổ chức khác - đây là các ví dụ từ [IBM](https://www.ibm.com/cloud/learn/ai-ethics), [Google](https://ai.google/principles), and [Facebook](https://ai.facebook.com/blog/facebooks-five-pillars-of-responsible-ai/). Họ có những giá trị chung nào? Những nguyên tắc này liên quan như thế nào đến sản phẩm hoặc ngành AI mà họ hoạt động?

### 2. Thách thức về Đạo đức - Ethics Challenges

Sau khi chúng ta đã xác định được các nguyên tắc đạo đức, bước tiếp theo là đánh giá dữ liệu và hành động AI của chúng ta để xem liệu chúng có phù hợp với các giá trị chung đó hay không. Hãy nghĩ về hành động của bạn theo hai loại: **thu thập dữ liệu** và **thiết kế thuật toán**.

Với việc thu thập dữ liệu, các hành động có thể liên quan đến dữ liệu cá nhân hoặc thông tin nhận dạng cá nhân (PII) đối với các cá nhân còn sống có thể nhận dạng được. Điều này bao gồm [nhiều loại dữ liệu phi cá nhân](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-personal-data_en) có thể nhận dạng chung một cá nhân. Các thách thức về mặt đạo đức có thể liên quan đến quyền riêng tư dữ liệu , quyền sở hữu dữ liệu và các chủ đề liên quan như sự đồng ý có thông tin và quyền sở hữu trí tuệ đối với người dùng.

Với thiết kế thuật toán, các hành động sẽ bao gồm việc thu thập và quản lý các tập dữ liệu , sau đó sử dụng chúng để đào tạo và triển khai các mô hình dữ liệu dự đoán kết quả hoặc tự động hóa các quyết định trong bối cảnh thế giới thực. Các thách thức về đạo đức có thể phát sinh từ sự thiên vị của tập dữ liệu , các vấn đề về chất lượng dữ liệu , sự không công bằng và sự trình bày sai lệch trong các thuật toán - bao gồm một số vấn đề mang tính hệ thống.

Trong cả hai trường hợp, những thách thức về đạo đức đều nêu bật những lĩnh vực mà hành động của chúng ta có thể gặp phải xung đột với các giá trị chung của chúng ta. Để phát hiện, giảm thiểu, tối thiểu hóa hoặc loại bỏ những mối quan tâm này - chúng ta cần đặt ra những câu hỏi "có/không" về mặt đạo đức liên quan đến hành động của mình, sau đó thực hiện các hành động khắc phục khi cần thiết. Hãy cùng xem xét một số thách thức về đạo đức và những câu hỏi đạo đức mà chúng nêu ra:


#### 2.1 Quyền sở hữu dữ liệu

Việc thu thập dữ liệu thường liên quan đến dữ liệu cá nhân có thể xác định chủ thể dữ liệu. [Quyền sở hữu](https://permission.io/blog/data-ownership) liên quan đến [_quyền người dùng_](https://permission.io/blog/data-ownership) liên quan đến việc tạo, xử lý và phổ biến dữ liệu.

Những câu hỏi đạo đức chúng ta cần hỏi là:

* Ai sở hữu dữ liệu? (người dùng hoặc tổ chức)
* Chủ thể dữ liệu có những quyền gì? (ví dụ: quyền truy cập, quyền xóa, quyền di chuyển)
* Các tổ chức có những quyền gì? (ví dụ: sửa các đánh giá độc hại của người dùng)

#### 2.2 Informed Consent - Sự đồng ý được thông báo

[Informed consent](https://legaldictionary.net/informed-consent/) định nghĩa hành động của người dùng đồng ý thực hiện một hành động (như thu thập dữ liệu) với sự hiểu biết đầy đủ về các sự kiện có liên quan bao gồm mục đích, rủi ro tiềm ẩn và các giải pháp thay thế.

Những câu hỏi cần khám phá ở đây là:

* Người dùng (chủ thể dữ liệu) có cấp quyền thu thập và sử dụng dữ liệu không?
* Người dùng có hiểu mục đích thu thập dữ liệu đó không?
* Người dùng có hiểu được những rủi ro tiềm ẩn khi tham gia không?

#### 2.3 Intellectual Property - Sở hữu trí tuệ

[Intellectual property](https://en.wikipedia.org/wiki/Intellectual_property) là những sáng tạo vô hình xuất phát từ sáng kiến ​​của con người, có thể có giá trị kinh tế đối với cá nhân hoặc doanh nghiệp.

Những câu hỏi cần khám phá ở đây là:

* Dữ liệu thu thập được có giá trị kinh tế đối với người dùng hoặc doanh nghiệp không?
* Người dùng có sở hữu trí tuệ ở đây không ?
* Tổ chức có sở hữu trí tuệ ở đây không ?
* Nếu những quyền này tồn tại, chúng ta sẽ bảo vệ chúng như thế nào?

#### 2.4 Data Privacy - Bảo mật dữ liệu

[Data privacy](https://www.northeastern.edu/graduate/blog/what-is-data-privacy/) hoặc quyền riêng tư thông tin đề cập đến việc bảo vệ quyền riêng tư của người dùng và bảo vệ danh tính người dùng đối với thông tin nhận dạng cá nhân.

Những câu hỏi cần khám phá ở đây là:

* Dữ liệu (cá nhân) của người dùng có được bảo mật trước nguy cơ bị hack và rò rỉ không?
* Dữ liệu của người dùng chỉ có người dùng và bối cảnh được ủy quyền mới có thể truy cập được phải không?
* Liệu tính ẩn danh của người dùng có được bảo vệ khi dữ liệu được chia sẻ hoặc phổ biến không?
* Người dùng có thể được xóa thông tin nhận dạng khỏi các tập dữ liệu ẩn danh không?


#### 2.5 Right To Be Forgotten - Quyền được quên/xóa bỏ

[Quyền được quên](https://en.wikipedia.org/wiki/Right_to_be_forgotten) hay [Quyền được xóa bỏ](https://www.gdpreu.org/right-to-be-forgotten/) cung cấp thêm quyền bảo vệ dữ liệu cá nhân cho người dùng. Cụ thể, nó trao cho người dùng quyền yêu cầu xóa hoặc gỡ bỏ dữ liệu cá nhân khỏi các tìm kiếm trên Internet và các vị trí khác, trong những trường hợp cụ thể - cho phép họ bắt đầu lại trực tuyến mà không bị xử lý các hành động trong quá khứ.

Những câu hỏi cần khám phá ở đây là:

* Hệ thống có cho phép chủ thể dữ liệu yêu cầu xóa dữ liệu không?
* Việc thu hồi sự đồng ý của người dùng có gây ra việc xóa tự động không?
* Dữ liệu được thu thập mà không có sự đồng ý hoặc bằng phương tiện bất hợp pháp?
* Chúng ta có tuân thủ các quy định của chính phủ về quyền riêng tư dữ liệu không?


#### 2.6 Dataset Bias - Sai lệch của tệp dữ liệu

Dataset or [Collection Bias](http://researcharticles.com/index.php/bias-in-data-collection-in-research/) về tập dữ liệu hoặc bộ sưu tập là về việc lựa chọn một tập hợp dữ liệu không đại diện để phát triển thuật toán, tạo ra sự bất công tiềm ẩn trong kết quả đầu ra cho các nhóm khác nhau. Các loại sai lệch bao gồm sai lệch lựa chọn hoặc lấy mẫu, sai lệch tình nguyện và sai lệch công cụ.

Những câu hỏi cần khám phá ở đây là:

* Chúng tôi có tuyển dụng được nhóm đối tượng dữ liệu đại diện không?
* Chúng tôi đã kiểm tra tập dữ liệu đã thu thập hoặc tuyển chọn của mình để tìm ra nhiều sai lệch khác nhau chưa?
* Chúng ta có thể giảm thiểu hoặc loại bỏ bất kỳ thành kiến ​​nào được phát hiện không?

#### 2.7 Data Quality - Chất lượng dữ liệu

[Data Quality](https://lakefs.io/data-quality-testing/) xem xét tính hợp lệ của tập dữ liệu được quản lý dùng để phát triển thuật toán của chúng tôi, kiểm tra xem các tính năng và bản ghi có đáp ứng các yêu cầu về mức độ chính xác và tính nhất quán cần thiết cho mục đích AI của chúng tôi hay không.

Những câu hỏi cần khám phá ở đây là:

* Chúng ta có nắm bắt được những tính năng hợp lệ cho trường hợp sử dụng của mình không ?
* Dữ liệu có được thu thập một cách nhất quán từ nhiều nguồn dữ liệu khác nhau không ?
* Bộ dữ liệu có đầy đủ cho nhiều điều kiện hoặc tình huống khác nhau không?
* Thông tin có được ghi lại chính xác và phản ánh đúng thực tế không?

#### 2.8 Algorithm Fairness - Thuật toán đảm bảo công bằng

[Algorithm Fairness](https://towardsdatascience.com/what-is-algorithm-fairness-3182e161cf9f) kiểm tra xem thiết kế thuật toán có phân biệt đối xử một cách có hệ thống với các nhóm đối tượng dữ liệu cụ thể dẫn đến [tác hại tiềm ẩn](https://docs.microsoft.com/en-us/azure/machine-learning/concept-fairness-ml) trong việc phân bổ (khi tài nguyên bị từ chối hoặc không được cung cấp cho nhóm đó) và chất lượng dịch vụ (khi AI không chính xác đối với một số nhóm đối tượng như các nhóm khác) hay không.

Những câu hỏi cần khám phá ở đây là:

* Chúng ta đã đánh giá độ chính xác của mô hình cho nhiều nhóm con và điều kiện khác nhau chưa?
* Chúng ta đã xem xét kỹ lưỡng hệ thống để tìm ra những tác hại tiềm ẩn (ví dụ: định kiến) chưa?
* Chúng ta có thể sửa đổi dữ liệu hoặc đào tạo lại các mô hình để giảm thiểu những tác hại đã xác định được không?

Khám phá các tài nguyên như [AI Fairness checklists](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4t6dA) để hiểu thêm.

#### 2.9 Misrepresentation - Suy diễn dữ liệu

[Data Misrepresentation](https://www.sciencedirect.com/topics/computer-science/misrepresentation) là về việc đặt câu hỏi liệu chúng ta có đang truyền đạt thông tin chi tiết từ dữ liệu được báo cáo trung thực theo cách gian dối để hỗ trợ cho một câu chuyện mong muốn hay không.

Những câu hỏi cần khám phá ở đây là:

* Chúng ta có báo cáo dữ liệu không đầy đủ hoặc không chính xác không?
* Chúng ta có đang trực quan hóa dữ liệu theo cách dẫn đến kết luận sai lệch không?
* Chúng ta có đang sử dụng các kỹ thuật thống kê có chọn lọc để thao túng kết quả không?
* Có lời giải thích nào khác có thể đưa ra kết luận khác không?

#### 2.10 Free Choice - Tự do lựa chọn
[Ảo tưởng tự do lựa chọn](https://www.datasciencecentral.com/profiles/blogs/the-illusion-of-choice) xảy ra khi "kiến trúc lựa chọn" của hệ thống sử dụng các thuật toán ra quyết định để thúc đẩy mọi người hướng đến kết quả mong muốn trong khi dường như trao cho họ các lựa chọn và quyền kiểm soát. Những mô hình đen tối này có thể gây ra tác hại về mặt xã hội và kinh tế cho người dùng. Vì các quyết định của người dùng tác động đến hồ sơ hành vi, những hành động này có khả năng thúc đẩy các lựa chọn trong tương lai có thể khuếch đại hoặc mở rộng tác động của những tác hại này.

Những câu hỏi cần khám phá ở đây là:

* Người dùng có hiểu được ý nghĩa của việc đưa ra lựa chọn đó không?
* Người dùng có biết về các lựa chọn (thay thế) và ưu, nhược điểm của từng lựa chọn không?
* Người dùng có thể đảo ngược lựa chọn tự động hoặc bị ảnh hưởng sau này không?

### 3. Case Studies - Các nghiên cứu tình huống

Để đưa những thách thức về đạo đức này vào bối cảnh thực tế, chúng ta cần xem xét các nghiên cứu điển hình nêu bật những tác hại và hậu quả tiềm ẩn đối với cá nhân và xã hội khi những vi phạm đạo đức như vậy bị bỏ qua.

Sau đây là một số ví dụ:

| Vấn đề về đạo đức | Tình huống thực tế  | 
|--- |--- |
| **Đồng ý nhận thông báo** | 1972 - [Tuskegee Syphilis Study](https://en.wikipedia.org/wiki/Tuskegee_Syphilis_Study) - Những người đàn ông Mỹ gốc Phi tham gia nghiên cứu được hứa hẹn sẽ được chăm sóc y tế miễn phí nhưng bị các nhà nghiên cứu lừa dối vì họ đã không thông báo cho đối tượng về chẩn đoán của mình hoặc về khả năng điều trị. Nhiều đối tượng đã tử vong và bạn tình hoặc con cái bị ảnh hưởng; nghiên cứu này kéo dài tới 40 năm. | 
| **Bảo mật dữ liệu** |  2007 - Nguồn dữ liệu [Netflix data prize](https://www.wired.com/2007/12/why-anonymous-data-sometimes-isnt/) cung cấp cho các nhà nghiên cứu 10 triệu bảng xếp hạng phim ẩn danh từ 50 nghìn khách hàng để giúp cải thiện thuật toán đề xuất. Tuy nhiên, các nhà nghiên cứu đã có thể liên kết dữ liệu ẩn danh này với dữ liệu nhận dạng cá nhân trong các tập dữ liệu bên ngoài (ví dụ: bình luận trên IMDb) - qua đó đã làm lộ thông tin một số người đăng ký Netflix.|
| **Thu thập dữ liệu bị thiên lệch**  | 2013 - Thành phố Boston [phát hành ứng dụng Street Bump](https://www.boston.gov/transportation/street-bump), một ứng dụng cho phép người dân báo cáo ổ gà, cung cấp cho thành phố dữ liệu đường bộ tốt hơn để tìm và khắc phục sự cố. Tuy nhiên [những người thu nhập thấp thì ít có cơ hội tiếp cận với ô tô và điện thoại](https://hbr.org/2013/04/the-hidden-biases-in-big-data), khiến các vấn đề về đường bộ của họ trở nên "vô hình" trong ứng dụng này. Các nhà phát triển đã làm việc với các học giả để tiếp cận công bằng và xóa bỏ khoảng cách kỹ thuật số vì sự công bằng. |
| **Thuật toán đảm bảo công bằng**  | 2018 - The MIT [Gender Shades Study](http://gendershades.org/overview.html) đã đánh giá độ chính xác của các sản phẩm AI phân loại giới tính, chỉ ra những khoảng cách về độ chính xác đối với phụ nữ và người da màu. Thẻ [2019 Apple Card](https://www.wired.com/story/the-apple-card-didnt-see-genderand-thats-the-problem/) dường như cung cấp ít chính xác hơn cho phụ nữ so với nam giới. Cả hai đều minh họa các vấn đề về thiên vị thuật toán dẫn đến tác hại kinh tế xã hội.|
| **Suy diễn dữ liệu** | 2020 - [Georgia Department of Public Health released COVID-19 charts](https://www.vox.com/covid-19-coronavirus-us-response-trump/2020/5/18/21262265/georgia-covid-19-cases-declining-reopening) dường như gây hiểu lầm cho người dân về xu hướng các ca bệnh được xác nhận với thứ tự không theo thứ tự thời gian trên trục x. Điều này minh họa cho việc trình bày sai lệch thông qua các thủ thuật trực quan hóa. |
| **Ảo tưởng tự do lựa chọn** | 2020 - Learning app [ABCmouse paid $10M to settle an FTC complaint](https://www.washingtonpost.com/business/2020/09/04/abcmouse-10-million-ftc-settlement/) trong đó phụ huynh bị mắc kẹt khi phải trả tiền cho các gói đăng ký mà họ không thể hủy. Điều này minh họa cho các mô hình đen tối trong kiến ​​trúc lựa chọn, nơi người dùng bị thúc đẩy đến các lựa chọn có khả năng gây hại. |
| **Quyền riêng tư của người dùng** | 2021 - Facebook [Data Breach](https://www.npr.org/2021/04/09/986005820/after-data-breach-exposes-530-million-facebook-says-it-will-not-notify-users) đã tiết lộ dữ liệu của 530 triệu người dùng, dẫn đến khoản thanh toán 5 tỷ đô la cho FTC. Tuy nhiên, công ty này đã từ chối thông báo cho người dùng về vụ vi phạm quyền của người dùng liên quan đến tính minh bạch và quyền truy cập dữ liệu. |

Bạn muốn khám phá thêm các nghiên cứu tình huống? Hãy xem các nguồn tài nguyên sau:
* [Ethics Unwrapped](https://ethicsunwrapped.utexas.edu/case-studies) - những vấn đề nan giải về đạo đức trong nhiều ngành công nghiệp khác nhau.
* [Data Science Ethics course](https://www.coursera.org/learn/data-science-ethics#syllabus) - khám phá các nghiên cứu điển hình mang tính bước ngoặt.
* [Where things have gone wrong](https://deon.drivendata.org/examples/) - danh sách kiểm tra phương pháp Deon với các ví dụ.

> 🚨 Hãy nghĩ về các nghiên cứu điển hình mà bạn đã thấy - bạn đã từng trải qua hay bị ảnh hưởng bởi một thách thức đạo đức tương tự trong cuộc sống của mình chưa? Bạn có thể nghĩ ra ít nhất một nghiên cứu điển hình khác minh họa cho một trong những thách thức đạo đức mà chúng ta đã thảo luận trong phần này không?

## Applied Ethics - Vận dụng các quy tắc đạo đức

Chúng ta đã nói về các khái niệm, thách thức và nghiên cứu tình huống về đạo đức trong bối cảnh thực tế. Nhưng làm thế nào để chúng ta bắt đầu áp dụng các nguyên tắc và thực hành đạo đức trong các dự án của mình? Và làm thế nào để chúng ta vận hành các thực hành này để quản lý tốt hơn? Hãy cùng khám phá một số giải pháp thực tế:

### 1. Professional Codes - Quy tắc chuyên nghiệp

Bộ quy tắc chuyên nghiệp cung cấp một lựa chọn cho các tổ chức để "khuyến khích" các thành viên ủng hộ các nguyên tắc đạo đức và tuyên bố sứ mệnh của họ. Bộ quy tắc là các hướng dẫn đạo đức cho hành vi chuyên nghiệp, giúp nhân viên hoặc thành viên đưa ra quyết định phù hợp với các nguyên tắc của tổ chức. Chúng chỉ tốt khi các thành viên tự nguyện tuân thủ; tuy nhiên, nhiều tổ chức cung cấp thêm phần thưởng và hình phạt để thúc đẩy sự tuân thủ của các thành viên.

Các ví dụ bao gồm:

 * [Oxford Munich](http://www.code-of-ethics.org/code-of-conduct/) Code of Ethics - Quy tắc đạo đức
 * [Data Science Association](http://datascienceassn.org/code-of-conduct.html) Code of Conduct - Quy tắc ứng xử (created 2013)
 * [ACM Code of Ethics and Professional Conduct](https://www.acm.org/code-of-ethics) (since 1993)

> 🚨 Bạn có thuộc về một tổ chức khoa học dữ liệu hoặc kỹ thuật chuyên nghiệp không? Hãy khám phá trang web của họ để xem liệu họ có định nghĩa một bộ quy tắc đạo đức nghề nghiệp hay không. Điều này nói lên điều gì về các nguyên tắc đạo đức của họ? Họ "khuyến khích" các thành viên tuân theo bộ quy tắc như thế nào?

### 2. Ethics Checklists - Kiểm tra đạo đức

Trong khi các quy tắc chuyên nghiệp xác định hành vi đạo đức bắt buộc từ những người hành nghề, họ có [những hạn chế biết trước](https://resources.oreilly.com/examples/0636920203964/blob/master/of_oaths_and_checklists.md) trong việc thực thi, đặc biệt là trong các dự án quy mô lớn. Thay vào đó, nhiều chuyên gia khoa học dữ liệu [ủng hộ phương pháp checklists](https://resources.oreilly.com/examples/0636920203964/blob/master/of_oaths_and_checklists.md), có thể kết nối các nguyên tắc với thực hành theo những cách xác định và có thể hành động hơn.

Danh sách kiểm tra chuyển đổi các câu hỏi thành các nhiệm vụ "có/không" có thể được vận hành, cho phép theo dõi chúng như một phần của quy trình phát hành sản phẩm tiêu chuẩn.

Các ví dụ bao gồm:
 * [Deon](https://deon.drivendata.org/) - danh sách kiểm tra đạo đức dữ liệu đa năng được tạo ra từ [industry recommendations](https://deon.drivendata.org/#checklist-citations) với công cụ dòng lệnh để tích hợp dễ dàng.
 * [Privacy Audit Checklist](https://cyber.harvard.edu/ecommerce/privacyaudit.html) - cung cấp hướng dẫn chung về các hoạt động xử lý thông tin theo quan điểm pháp lý và xã hội.
 * [AI Fairness Checklist](https://www.microsoft.com/en-us/research/project/ai-fairness-checklist/) -  do các chuyên gia AI tạo ra để hỗ trợ việc áp dụng và tích hợp các kiểm tra tính công bằng vào chu kỳ phát triển AI.
 * [22 questions for ethics in data and AI](https://medium.com/the-organization/22-questions-for-ethics-in-data-and-ai-efb68fd19429) - khuôn khổ mở hơn, được xây dựng để khám phá ban đầu các vấn đề đạo đức trong bối cảnh thiết kế, triển khai và tổ chức.

### 3. Ethics Regulations - Quy định về đạo đức

Đạo đức là về việc xác định các giá trị chung và làm điều đúng đắn một cách tự nguyện . Tuân thủ là về việc tuân thủ luật pháp nếu và ở nơi được xác định. Quản trị bao gồm rộng rãi tất cả các cách thức mà các tổ chức hoạt động để thực thi các nguyên tắc đạo đức và tuân thủ các luật đã được thiết lập.

Ngày nay, quản trị có hai hình thức trong các tổ chức. Đầu tiên, đó là về việc xác định các nguyên tắc AI có đạo đức và thiết lập các hoạt động để vận hành việc áp dụng trên tất cả các dự án liên quan đến AI trong tổ chức. Thứ hai, đó là về việc tuân thủ tất cả các quy định bảo vệ dữ liệu do chính phủ yêu cầu đối với các khu vực mà tổ chức hoạt động.

Ví dụ về quy định bảo vệ dữ liệu và quyền riêng tư:

 * `1974`, [US Privacy Act - Đạo luật](https://www.justice.gov/opcl/privacy-act-1974) - điều chỉnh việc thu thập, sử dụng và tiết lộ thông tin cá nhân của chính quyền liên bang .
 * `1996`, [US Health Insurance Portability & Accountability Act (HIPAA)](https://www.cdc.gov/phlp/publications/topic/hipaa.html) - bảo vệ dữ liệu sức khỏe cá nhân.
 * `1998`, [US Children's Online Privacy Protection Act (COPPA)](https://www.ftc.gov/enforcement/rules/rulemaking-regulatory-reform-proceedings/childrens-online-privacy-protection-rule) - bảo vệ quyền riêng tư dữ liệu của trẻ em dưới 13 tuổi.
 * `2018`, [General Data Protection Regulation (GDPR)](https://gdpr-info.eu/) - cung cấp quyền của người dùng, bảo vệ dữ liệu và quyền riêng tư.
 * `2018`, [California Consumer Privacy Act (CCPA)](https://www.oag.ca.gov/privacy/ccpa) trao cho người tiêu dùng nhiều quyền hơn đối với dữ liệu (cá nhân) của họ.
 * `2021`, China's [Personal Information Protection Law](https://www.reuters.com/world/china/china-passes-new-personal-data-privacy-law-take-effect-nov-1-2021-08-20/) vừa được thông qua, tạo ra một trong những quy định về quyền riêng tư dữ liệu trực tuyến mạnh mẽ nhất trên toàn thế giới.

> 🚨 GDPR (Quy định bảo vệ dữ liệu chung) do Liên minh châu Âu định nghĩa vẫn là một trong những quy định về quyền riêng tư dữ liệu có ảnh hưởng nhất hiện nay. Bạn có biết quy định này cũng định nghĩa [8 user rights](https://www.freeprivacypolicy.com/blog/8-user-rights-gdpr) để bảo vệ quyền riêng tư kỹ thuật số và dữ liệu cá nhân của công dân không? Tìm hiểu về những quyền này và lý do tại sao chúng quan trọng.


### 4. Ethics Culture - Văn hóa đạo đức

Lưu ý rằng vẫn còn một khoảng cách vô hình giữa việc tuân thủ (thực hiện đủ để đáp ứng "đúng theo luật") và giải quyết [systemic issues - vấn đề có tính hệ thống](https://www.coursera.org/learn/data-science-ethics/home/week/4) (như sự cứng nhắc, bất đối xứng thông tin và bất công trong phân phối) có thể đẩy nhanh quá trình vũ khí hóa AI.

Điều sau đòi hỏi [các biện pháp tiếp cận ở khía cạnh ethics cultures](https://towardsdatascience.com/why-ai-ethics-requires-a-culture-driven-approach-26f451afa29f) xây dựng các kết nối cảm xúc và các giá trị chung nhất quán giữa các tổ chức trong ngành. Điều này đòi hỏi [sự định hình văn hóa đạo đức](https://www.codeforamerica.org/news/formalizing-an-ethical-data-culture/) nhiều hơn trong các tổ chức - cho phép bất kỳ ai cũng có thể kéo [pull the Andon cord - gióng lên hồi chuông cảnh báo](https://en.wikipedia.org/wiki/Andon_(manufacturing)) (để nêu ra các mối quan tâm về đạo đức ngay từ đầu quá trình) và biến các đánh giá đạo đức (ví dụ, khi tuyển dụng) thành một tiêu chí cốt lõi trong việc hình thành nhóm trong các dự án AI.

---
## [Kiểm tra sau bài giảng](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/3) 🎯
## Review & Self Study - Đánh giá & Tự học

Các khóa học và sách giúp hiểu các khái niệm và thách thức cốt lõi về đạo đức, trong khi các nghiên cứu tình huống và công cụ giúp thực hành đạo đức ứng dụng trong bối cảnh thực tế. Sau đây là một số tài nguyên để bắt đầu.

* [Machine Learning For Beginners](https://github.com/microsoft/ML-For-Beginners/blob/main/1-Introduction/3-fairness/README.md) - bài học về Công bằng, từ Microsoft.
* [Principles of Responsible AI](https://docs.microsoft.com/en-us/learn/modules/responsible-ai-principles/) - lộ trình học miễn phí từ Microsoft Learn.
* [Ethics and Data Science](https://resources.oreilly.com/examples/0636920203964) - Sách điện tử O'Reilly (M. Loukides, H. Mason và cộng sự)
* [Data Science Ethics](https://www.coursera.org/learn/data-science-ethics#syllabus) - khóa học trực tuyến từ Đại học Michigan.
* [Ethics Unwrapped](https://ethicsunwrapped.utexas.edu/case-studies) -  các nghiên cứu điển hình từ Đại học Texas.

# Assignment - Bài tập phân công

[Bạn hãy viết một case-study về chủ đề đạo đức dữ liệu](https://github.com/hoanglong8/Microsoft-courses_Data-Science-For-Beginners/blob/main/1-Introduction/02-ethics/translations/Assignment.vn.md)
