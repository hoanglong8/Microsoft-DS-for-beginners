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

Trong bài học này, chúng ta sẽ khám phá lĩnh vực đạo đức dữ liệu hấp dẫn - từ các khái niệm và thách thức cốt lõi, đến các nghiên cứu tình huống và khái niệm AI ứng dụng như quản trị - giúp thiết lập văn hóa đạo đức trong các nhóm và tổ chức làm việc với dữ liệu và AI.



## [Câu hỏi chuẩn bị trước bài giảng](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/2) 🎯

## Khái niệm cơ bản

Chúng ta hãy bắt đầu bằng cách hiểu thuật ngữ cơ bản.

Từ "đạo đức" xuất phát từ ["ethikos" trong tiếng Hy Lạp](https://en.wikipedia.org/wiki/Ethics) (gốc từ "ethos") có nghĩa là tính cách hoặc bản chất đạo đức .

**Đạo đức** là về các giá trị chung và các nguyên tắc đạo đức chi phối hành vi của chúng ta trong xã hội. Đạo đức không dựa trên luật pháp mà dựa trên các chuẩn mực được chấp nhận rộng rãi về điều gì là "đúng so với sai". Tuy nhiên, các cân nhắc về đạo đức có thể ảnh hưởng đến các sáng kiến ​​quản trị doanh nghiệp và các quy định của chính phủ tạo ra nhiều động lực hơn để tuân thủ.

**Đạo đức dữ liệu học** là một [nhánh của Đạo đức học](https://royalsocietypublishing.org/doi/full/10.1098/rsta.2016.0360#sec-1) "nghiên cứu và đánh giá các vấn đề đạo đức liên quan đến dữ liệu, thuật toán và các hoạt động tương ứng ". Ở đây, "dữ liệu" tập trung vào các hành động liên quan đến việc tạo, ghi lại, quản lý, xử lý, phổ biến, chia sẻ và sử dụng, "thuật toán" tập trung vào AI, tác nhân, máy học và rô-bốt, và "thực hành" tập trung vào các chủ đề như đổi mới có trách nhiệm, lập trình, hack và các quy tắc đạo đức.

**Vận dụng Đạo đức** là [ứng dụng đạo đức vào thực tế](https://en.wikipedia.org/wiki/Applied_ethics). Đó là quá trình chủ động điều tra các vấn đề đạo đức trong bối cảnh các hành động, sản phẩm và quy trình trong thế giới thực , và thực hiện các biện pháp khắc phục để đảm bảo chúng phù hợp với các giá trị đạo đức đã xác định của chúng tôi.

**Văn hóa đạo đức** là về [việc thực hành các quy tắc đạo đức](https://hbr.org/2019/05/how-to-design-an-ethical-organization) để đảm bảo rằng các nguyên tắc và thực hành đạo đức của chúng ta được áp dụng theo cách nhất quán và có thể mở rộng trên toàn bộ tổ chức. Văn hóa đạo đức thành công xác định các nguyên tắc đạo đức trên toàn tổ chức, cung cấp các động lực có ý nghĩa để tuân thủ và củng cố các chuẩn mực đạo đức bằng cách khuyến khích và khuếch đại các hành vi mong muốn ở mọi cấp độ của tổ chức.


## Khái niệm Đạo đức

Trong phần này, chúng ta sẽ thảo luận về các khái niệm như giá trị chung (nguyên tắc) và thách thức về mặt đạo đức (vấn đề) đối với đạo đức dữ liệu - và khám phá các nghiên cứu điển hình giúp bạn hiểu các khái niệm này trong bối cảnh thực tế.

### 1. Nguyên tắc đạo đức
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

### 2. Ethics Challenges

Once we have ethical principles defined, the next step is to evaluate our data and AI actions to see if they align with those shared values. Think about your actions in two categories: _data collection_ and _algorithm design_. 

With data collection, actions will likely involve **personal data** or personally identifiable information (PII) for identifiable living individuals. This includes [diverse items of non-personal data](https://ec.europa.eu/info/law/law-topic/data-protection/reform/what-personal-data_en) that _collectively_ identify an individual. Ethical challenges can relate to _data privacy_, _data ownership_, and related topics like _informed consent_ and _intellectual property rights_ for users.

With algorithm design, actions will involve collecting & curating **datasets**, then using them to train & deploy **data models** that predict outcomes or automate decisions in real-world contexts. Ethical challenges can arise from _dataset bias_, _data quality_ issues, _unfairness_ ,and _misrepresentation_ in algorithms - including some issues that are systemic in nature.

In both cases, ethics challenges highlight areas where our actions may encounter conflict with our shared values. To detect, mitigate, minimize, or eliminate, these concerns - we need to ask moral "yes/no" questions related to our actions, then take corrective actions as needed. Let's take a look at some ethical challenges and the moral questions they raise:


#### 2.1 Data Ownership

Data collection often involves personal data that can identify the data subjects. [Data ownership](https://permission.io/blog/data-ownership) is about _control_ and [_user rights_](https://permission.io/blog/data-ownership) related to the creation, processing ,and dissemination of data. 

The moral questions we need to ask are: 
 * Who owns the data? (user or organization)
 * What rights do data subjects have? (ex: access, erasure, portability)
 * What rights do organizations have? (ex: rectify malicious user reviews)

#### 2.2 Informed Consent

[Informed consent](https://legaldictionary.net/informed-consent/) defines the act of users agreeing to an action (like data collection) with a _full understanding_ of relevant facts including the purpose, potential risks, and alternatives. 

Questions to explore here are:
 * Did the user (data subject) give permission for data capture and usage?
 * Did the user understand the purpose for which that data was captured?
 * Did the user understand the potential risks from  their participation?

#### 2.3 Intellectual Property

[Intellectual property](https://en.wikipedia.org/wiki/Intellectual_property) refers to intangible creations resulting from the human initiative, that may _have economic value_ to individuals or businesses. 

Questions to explore here are:
 * Did the collected data have economic value to a user or business?
 * Does the **user** have intellectual property here?
 * Does the **organization** have intellectual property here?
 * If these rights exist, how are we protecting them?

#### 2.4 Data Privacy

[Data privacy](https://www.northeastern.edu/graduate/blog/what-is-data-privacy/) or information privacy refers to the preservation of user privacy and protection of user identity with respect to personally identifiable information. 

Questions to explore here are:
 * Is users' (personal) data secured against hacks and leaks?
 * Is users' data accessible only to authorized users and contexts?
 * Is users' anonymity preserved when data is shared or disseminated?
 * Can a user be de-identified from anonymized datasets?


#### 2.5 Right To Be Forgotten

The [Right To Be Forgotten](https://en.wikipedia.org/wiki/Right_to_be_forgotten) or [Right to Erasure](https://www.gdpreu.org/right-to-be-forgotten/) provides additional personal data protection to users. Specifically, it gives users the right to request deletion or removal of personal data from Internet searches and other locations, _under specific circumstances_ - allowing them a fresh start online without past actions being held against them.

Questions to explore here are:
 * Does the system allow data subjects to request erasure?
 * Should the withdrawal of user consent trigger automated erasure?
 * Was data collected without consent or by unlawful means?
 * Are we compliant with government regulations for data privacy?


#### 2.6 Dataset Bias

Dataset or [Collection Bias](http://researcharticles.com/index.php/bias-in-data-collection-in-research/) is about selecting a _non-representative_ subset of data for algorithm development, creating potential  unfairness in result outcomes for diverse groups. Types of bias include selection or sampling bias, volunteer bias, and instrument bias. 

Questions to explore here are:
 * Did we recruit a representative set of data subjects?
 * Did we test our collected or curated dataset for various biases?
 * Can we mitigate or remove any discovered biases?

#### 2.7 Data Quality

[Data Quality](https://lakefs.io/data-quality-testing/) looks at the validity of the curated dataset used to develop our algorithms, checking to see if features and records meet requirements for the level of accuracy and consistency needed for our AI purpose.

Questions to explore here are:
 * Did we capture valid _features_ for our use case?
 * Was data captured _consistently_ across diverse data sources?
 * Is the dataset _complete_ for diverse conditions or scenarios?
 * Is information captured _accurately_ in reflecting reality?

#### 2.8 Algorithm Fairness

[Algorithm Fairness](https://towardsdatascience.com/what-is-algorithm-fairness-3182e161cf9f) checks to see if the algorithm design systematically discriminates against specific subgroups of data subjects leading to [potential harms](https://docs.microsoft.com/en-us/azure/machine-learning/concept-fairness-ml) in _allocation_ (where resources are denied or withheld from that group) and _quality of service_ (where AI is not as accurate for some subgroups as it is for others). 

Questions to explore here are:
 * Did we evaluate model accuracy for diverse subgroups and conditions?
 * Did we scrutinize the system for potential harms (e.g., stereotyping)?
 * Can we revise data or retrain models to mitigate identified harms?

Explore resources like [AI Fairness checklists](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE4t6dA) to learn more.

#### 2.9 Misrepresentation

[Data Misrepresentation](https://www.sciencedirect.com/topics/computer-science/misrepresentation) is about asking whether we are communicating insights from honestly reported data in a deceptive manner to support a desired narrative. 

Questions to explore here are:
 * Are we reporting incomplete or inaccurate data?
 * Are we visualizing data in a manner that drives misleading conclusions?
 * Are we using selective statistical techniques to manipulate outcomes?
 * Are there alternative explanations that may offer a different conclusion?

#### 2.10 Free Choice
The [Illusion of Free Choice](https://www.datasciencecentral.com/profiles/blogs/the-illusion-of-choice) occurs when system "choice architectures" use decision-making algorithms to nudge people towards taking a preferred outcome while seeming to give them options and control. These [dark patterns](https://www.darkpatterns.org/) can cause social and economic harm to users. Because user decisions impact behavior profiles, these actions potentially drive future choices that can amplify or extend the impact of these harms.

Questions to explore here are:
 * Did the user understand the implications of making that choice?
 * Was the user aware of (alternative) choices and the pros & cons of each?
 * Can the user reverse an automated or influenced choice later?

### 3. Case Studies

To put these ethical challenges in real-world contexts, it helps to look at case studies that highlight the potential harms and consequences to individuals and society, when such ethics violations are overlooked. 

Here are a few examples:

| Ethics Challenge | Case Study  | 
|--- |--- |
| **Informed Consent** | 1972 - [Tuskegee Syphilis Study](https://en.wikipedia.org/wiki/Tuskegee_Syphilis_Study) - African American men who participated in the study were promised free medical care _but deceived_ by researchers who failed to inform subjects of their diagnosis or about availability of treatment. Many subjects died & partners or children were affected; the study lasted 40 years. | 
| **Data Privacy** |  2007 - The [Netflix data prize](https://www.wired.com/2007/12/why-anonymous-data-sometimes-isnt/) provided researchers with _10M anonymized movie rankings from 50K customers_ to help improve recommendation algorithms. However, researchers were able to correlate anonymized data with personally-identifiable data in _external datasets_ (e.g., IMDb comments) - effectively "de-anonymizing" some Netflix subscribers.|
| **Collection Bias**  | 2013 - The City of Boston [developed Street Bump](https://www.boston.gov/transportation/street-bump), an app that let citizens report potholes, giving the city better roadway data to find and fix issues. However, [people in lower income groups had less access to cars and phones](https://hbr.org/2013/04/the-hidden-biases-in-big-data), making their roadway issues invisible in this app. Developers worked with academics to _equitable access and digital divides_ issues for fairness. |
| **Algorithmic Fairness**  | 2018 - The MIT [Gender Shades Study](http://gendershades.org/overview.html) evaluated the accuracy of gender classification AI products, exposing gaps in accuracy for women and persons of color. A [2019 Apple Card](https://www.wired.com/story/the-apple-card-didnt-see-genderand-thats-the-problem/) seemed to offer less credit to women than men. Both illustrated issues in algorithmic bias leading to socio-economic harms.|
| **Data Misrepresentation** | 2020 - The [Georgia Department of Public Health released COVID-19 charts](https://www.vox.com/covid-19-coronavirus-us-response-trump/2020/5/18/21262265/georgia-covid-19-cases-declining-reopening) that appeared to mislead citizens about trends in confirmed cases with non-chronological ordering on the x-axis. This illustrates misrepresentation through visualization tricks. |
| **Illusion of free choice** | 2020 - Learning app [ABCmouse paid $10M to settle an FTC complaint](https://www.washingtonpost.com/business/2020/09/04/abcmouse-10-million-ftc-settlement/) where parents were trapped into paying for subscriptions they couldn't cancel. This illustrates dark patterns in choice architectures, where users were nudged towards potentially harmful choices. |
| **Data Privacy & User Rights** | 2021 - Facebook [Data Breach](https://www.npr.org/2021/04/09/986005820/after-data-breach-exposes-530-million-facebook-says-it-will-not-notify-users) exposed data from 530M users, resulting in a $5B settlement to the FTC. It however refused to notify users of the breach violating user rights around data transparency and access. |

Want to explore more case studies? Check out these resources:
* [Ethics Unwrapped](https://ethicsunwrapped.utexas.edu/case-studies) - ethics dilemmas across diverse industries. 
* [Data Science Ethics course](https://www.coursera.org/learn/data-science-ethics#syllabus) - landmark case studies explored.
* [Where things have gone wrong](https://deon.drivendata.org/examples/) - deon checklist with examples

> 🚨 Think about the case studies you've seen - have you experienced, or been affected by, a similar ethical challenge in your life? Can you think of at least one other case study that illustrates one of the ethical challenges we've discussed in this section?

## Applied Ethics

We've talked about ethics concepts, challenges ,and case studies in real-world contexts. But how do we get started _applying_ ethical principles and practices in our projects? And how do we _operationalize_ these practices for better governance? Let's explore some real-world solutions: 

### 1. Professional Codes

Professional Codes offer one option for organizations to "incentivize" members to support their ethical principles and mission statement. Codes are _moral guidelines_ for professional behavior, helping employees or members make decisions that align with their organization's principles. They are only as good as the voluntary compliance from members; however, many organizations offer additional rewards and penalties to motivate compliance from members.

Examples include:

 * [Oxford Munich](http://www.code-of-ethics.org/code-of-conduct/) Code of Ethics
 * [Data Science Association](http://datascienceassn.org/code-of-conduct.html) Code of Conduct (created 2013)
 * [ACM Code of Ethics and Professional Conduct](https://www.acm.org/code-of-ethics) (since 1993)

> 🚨 Do you belong to a professional engineering or data science organization? Explore their site to see if they define a professional code of ethics. What does this say about their ethical principles? How are they "incentivizing" members to follow the code?

### 2. Ethics Checklists

While professional codes define required _ethical behavior_ from practitioners, they [have known limitations](https://resources.oreilly.com/examples/0636920203964/blob/master/of_oaths_and_checklists.md) in enforcement, particularly in large-scale projects. Instead, many data Science experts [advocate for checklists](https://resources.oreilly.com/examples/0636920203964/blob/master/of_oaths_and_checklists.md), that can **connect principles to practices** in more deterministic and actionable ways. 

Checklists convert questions into "yes/no" tasks that can be operationalized, allowing them to be tracked as part of standard product release workflows. 

Examples include:
 * [Deon](https://deon.drivendata.org/) - a general-purpose data ethics checklist created from [industry recommendations](https://deon.drivendata.org/#checklist-citations) with a command-line tool for easy integration.
 * [Privacy Audit Checklist](https://cyber.harvard.edu/ecommerce/privacyaudit.html) - provides general guidance for information handling practices from legal and social exposure perspectives.
 * [AI Fairness Checklist](https://www.microsoft.com/en-us/research/project/ai-fairness-checklist/) - created by AI practitioners to support the adoption and integration of fairness checks into AI development cycles.
 * [22 questions for ethics in data and AI](https://medium.com/the-organization/22-questions-for-ethics-in-data-and-ai-efb68fd19429) - more open-ended framework, structured for initial exploration of ethical issues in design, implementation, and organizational, contexts.

### 3. Ethics Regulations

Ethics is about defining shared values and doing the right thing _voluntarily_. **Compliance** is about _following the law_ if and where defined. **Governance** broadly covers all the ways in which organizations operate to enforce ethical principles and comply with established laws.

Today, governance takes two forms within organizations. First, it's about defining **ethical AI** principles and establishing practices to operationalize adoption across all AI-related projects in the organization. Second, it's about complying with all government-mandated **data protection regulations** for regions it operates in.

Examples of data protection and privacy regulations:

 * `1974`, [US Privacy Act](https://www.justice.gov/opcl/privacy-act-1974) - regulates _federal govt._ collection, use ,and disclosure of personal information.
 * `1996`, [US Health Insurance Portability & Accountability Act (HIPAA)](https://www.cdc.gov/phlp/publications/topic/hipaa.html) - protects personal health data.
 * `1998`, [US Children's Online Privacy Protection Act (COPPA)](https://www.ftc.gov/enforcement/rules/rulemaking-regulatory-reform-proceedings/childrens-online-privacy-protection-rule) - protects data privacy of children under 13.
 * `2018`, [General Data Protection Regulation (GDPR)](https://gdpr-info.eu/) - provides user rights, data protection ,and privacy.
 * `2018`, [California Consumer Privacy Act (CCPA)](https://www.oag.ca.gov/privacy/ccpa) gives consumers more _rights_ over their (personal) data.
 * `2021`, China's [Personal Information Protection Law](https://www.reuters.com/world/china/china-passes-new-personal-data-privacy-law-take-effect-nov-1-2021-08-20/) just passed, creating one of the strongest online data privacy regulations worldwide.

> 🚨 The European Union defined GDPR (General Data Protection Regulation) remains one of the most influential data privacy regulations today. Did you know it also defines [8 user rights](https://www.freeprivacypolicy.com/blog/8-user-rights-gdpr) to protect citizens' digital privacy and personal data? Learn about what these are, and why they matter.


### 4. Ethics Culture

Note that there remains an intangible gap between _compliance_ (doing enough to meet "the letter of the law") and addressing [systemic issues](https://www.coursera.org/learn/data-science-ethics/home/week/4) (like ossification, information asymmetry, and distributional unfairness) that can speed up the weaponization of AI. 

The latter requires [collaborative approaches to defining ethics cultures](https://towardsdatascience.com/why-ai-ethics-requires-a-culture-driven-approach-26f451afa29f) that build emotional connections and consistent shared values _across organizations_ in the industry. This calls for more [formalized data ethics cultures](https://www.codeforamerica.org/news/formalizing-an-ethical-data-culture/) in organizations - allowing _anyone_ to [pull the Andon cord](https://en.wikipedia.org/wiki/Andon_(manufacturing)) (to raise ethics concerns early in the process) and making _ethical assessments_ (e.g., in hiring) a core criteria team formation in AI projects.

---
## [Post-lecture quiz](https://purple-hill-04aebfb03.1.azurestaticapps.net/quiz/3) 🎯
## Review & Self Study 

Courses and books help with understanding core ethics concepts and challenges, while case studies and tools help with applied ethics practices in real-world contexts. Here are a few resources to start with.

* [Machine Learning For Beginners](https://github.com/microsoft/ML-For-Beginners/blob/main/1-Introduction/3-fairness/README.md) - lesson on Fairness, from Microsoft.
* [Principles of Responsible AI](https://docs.microsoft.com/en-us/learn/modules/responsible-ai-principles/) - free learning path from Microsoft Learn.
* [Ethics and Data Science](https://resources.oreilly.com/examples/0636920203964) - O'Reilly EBook (M. Loukides, H. Mason et. al)
* [Data Science Ethics](https://www.coursera.org/learn/data-science-ethics#syllabus) - online course from the University of Michigan.
* [Ethics Unwrapped](https://ethicsunwrapped.utexas.edu/case-studies) - case studies from the University of Texas.

# Assignment 

[Write A Data Ethics Case Study](assignment.md)
