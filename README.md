# Lab 21 - Phân tích rủi ro AI trong giáo dục

- Họ và tên: Lại Bá Quân
- MSSV / mã học viên: 2A202602495
- Lớp: Track 1
- Ngành đã chọn: Giáo dục / AI tutor và công cụ hỗ trợ học tập

## 1. Industry Risk Snapshot

| Nội dung | Đánh giá và lý do |
| --- | --- |
| Tác hại chính có thể xảy ra | AI có thể đưa ra lời giải sai hoặc khuyến nghị không phù hợp, khiến học sinh hiểu sai kiến thức; học sinh có thể phụ thuộc vào đáp án trực tiếp và giảm khả năng tự giải. Công cụ phát hiện bài viết AI có thể gắn nhãn nhầm bài tự viết, dẫn đến nghi ngờ hoặc xử lý bất công. |
| Mức độ high-stakes | Trung bình trong hoạt động luyện tập thông thường; cao hơn nếu đầu ra AI được dùng để chấm điểm, xét năng lực hoặc làm căn cứ kỷ luật. Mức độ phụ thuộc vào việc con người có kiểm tra và học sinh có được khiếu nại hay không. |
| Dữ liệu nhạy cảm có thể được sử dụng | Bài làm, câu hỏi, điểm số, lịch sử học tập, thông tin nhận dạng và nội dung trao đổi của học sinh. Không đưa dữ liệu cá nhân thật vào repo. |
| Nhu cầu human review | Cao khi AI đánh giá, chấm điểm, phát hiện gian lận hoặc đưa ra hướng dẫn có thể tác động đến kết quả học tập. Giáo viên cần kiểm tra nguồn/lời giải và không dùng nhãn AI làm bằng chứng duy nhất để kỷ luật học sinh. |

## 2. Case study 1 - GPT-4 không có guardrail trong luyện toán trung học

### Brief Case - nghiên cứu GPT-4 trong luyện toán

- Tổ chức / sản phẩm AI: GPT-4 trong thử nghiệm thực địa của Bastani và cộng sự; nghiên cứu so sánh giao diện GPT cơ bản với GPT Tutor có guardrail sư phạm.
- Thời gian, địa điểm / bối cảnh: Nghiên cứu thực nghiệm trên học sinh trung học học toán; bài báo được đăng trên PNAS năm 2025.
- AI được dùng để làm gì: Hỗ trợ học sinh trong các buổi luyện tập bài toán.
- Vấn đề hoặc sự kiện đáng chú ý: Nhóm dùng giao diện GPT-4 cơ bản có thể nhận lời giải trực tiếp và dùng AI như một "crutch" thay vì tự luyện. Nghiên cứu báo cáo điểm luyện tập tăng nhưng kết quả bài kiểm tra không có AI giảm so với nhóm đối chứng. Giao diện GPT Tutor được thiết kế để đưa gợi ý thay vì cho đáp án và giúp giảm tác động bất lợi này.
- Số liệu có nguồn: Thí nghiệm có gần 1.000 học sinh. Theo bài báo, nhóm GPT cơ bản có điểm luyện tập cao hơn 48% nhưng điểm bài kiểm tra không có AI thấp hơn 17% so với nhóm đối chứng. Các tỷ lệ này là kết quả của bối cảnh và thiết kế nghiên cứu này, không phải dự báo cho mọi trường học.
- Nguồn: Hamsa Bastani và cộng sự, "Generative AI without guardrails can harm learning: Evidence from high school mathematics," PNAS (2025). [Bài báo PNAS](https://doi.org/10.1073/pnas.2422633122). Tóm tắt và tài liệu nghiên cứu của tác giả: [trang nghiên cứu của Hamsa Bastani](https://hamsabastani.github.io/education_llm/).
- Phân biệt bằng chứng và nhận định: Bằng chứng của nghiên cứu là kết quả học tập trong thử nghiệm; nghiên cứu không chứng minh rằng mọi học sinh dùng AI sẽ giảm điểm. Nhận định của tôi là việc cho đáp án trực tiếp có thể khuyến khích phụ thuộc, nhất là nếu không có giáo viên hoặc cơ chế kiểm tra.

### Harm Map Worksheet - GPT-4 trong luyện toán

| Trường | Phân tích |
| --- | --- |
| High-risk moment | Học sinh dùng GPT-4 để giải bài tập trong lúc luyện tập, sau đó phải tự làm bài kiểm tra không có AI. |
| Stakeholder bị ảnh hưởng | Học sinh trực tiếp; giáo viên cần đánh giá học sinh đã nắm kiến thức hay chưa. |
| Failure mode | Over-reliance: học sinh có thể dựa vào đáp án AI thay vì tự suy luận. Đây là cách giải thích có khả năng phù hợp với kết quả, không phải kết luận rằng mọi học sinh đều phụ thuộc. |
| Layer bắt đầu lỗi | UX / Safety - suy luận từ việc giao diện GPT cơ bản đưa đáp án trực tiếp, trong khi GPT Tutor có guardrail hướng học sinh đến gợi ý. Bài báo không xác nhận đây là lỗi kỹ thuật nội bộ của mô hình. |
| Harm xảy ra là gì? | Trong điều kiện thử nghiệm, nhóm GPT cơ bản đạt điểm bài kiểm tra không có AI thấp hơn nhóm đối chứng. Tác động được đo là kết quả học tập trong bài kiểm tra; không suy rộng thành tổn hại lâu dài nếu nghiên cứu không đo điều đó. |
| Harm lens | Opportunity loss / learning loss: học sinh có thể mất cơ hội thể hiện kiến thức độc lập. |
| Severity | Medium. Giảm kết quả học tập là đáng kể, nhưng nghiên cứu này không báo cáo chấn thương thể chất hay hậu quả không thể đảo ngược. |
| Scale | Gần 1.000 học sinh trong thử nghiệm. Không suy ra quy mô tác động trong toàn bộ hệ thống giáo dục. |
| Probability | Có bằng chứng về kết quả bất lợi ở nhóm GPT cơ bản trong thử nghiệm; không có dữ liệu để gán xác suất cho từng học sinh hoặc mọi lớp học. |
| Frequency | Nghiên cứu đánh giá một chuỗi buổi luyện tập và bài kiểm tra; không cung cấp tần suất lỗi trên mỗi lần sử dụng. |
| Vì sao? | Căn cứ là so sánh giữa nhóm thử nghiệm và đối chứng trong bài báo. Các đánh giá Severity và Harm lens là phân tích của tôi; không đồng nhất điểm bài thi thấp hơn với chẩn đoán suy giảm học tập dài hạn. |

## 3. Case study 2 - Detector gắn nhầm bài viết của người học tiếng Anh không bản ngữ

### Brief Case - detector bài viết AI

- Tổ chức / sản phẩm AI: Nghiên cứu của Weixin Liang, Mert Yuksekgonul, Yining Mao, Eric Wu và James Zou đánh giá 7 công cụ phát hiện văn bản GPT.
- Thời gian, địa điểm / bối cảnh: Nghiên cứu công bố năm 2023; kiểm thử trên bài viết tiếng Anh do người viết bản ngữ và không bản ngữ tạo ra.
- AI được dùng để làm gì: Các detector phân loại bài viết là do AI tạo hay do con người viết; trường học có thể dùng kết quả này để điều tra bài tập.
- Vấn đề hoặc sự kiện đáng chú ý: Các công cụ có xu hướng gắn nhãn bài viết tiếng Anh của người không bản ngữ là văn bản do AI tạo, tạo nguy cơ bất công nếu nhãn này được dùng để nghi ngờ hoặc kỷ luật học sinh.
- Số liệu có nguồn: Nghiên cứu đánh giá 7 detector trên 91 bài luận TOEFL do người học tiếng Anh không bản ngữ viết. Bài báo báo cáo tỷ lệ dương tính giả trung bình 61,22%; 18/91 bài (19,78%) bị cả 7 detector gắn nhãn AI, và 89/91 bài (97,80%) bị ít nhất một detector gắn nhãn AI. Đây là kết quả trên bộ kiểm thử, không phải tỷ lệ học sinh trong trường bị kỷ luật.
- Nguồn: Weixin Liang và cộng sự, "GPT detectors are biased against non-native English writers," Patterns 4(7), 2023. [Bài báo trên arXiv](https://arxiv.org/abs/2304.02819). Phiên bản xuất bản: [Patterns, DOI 10.1016/j.patter.2023.100779](https://doi.org/10.1016/j.patter.2023.100779).
- Phân biệt bằng chứng và nhận định: Bằng chứng là detector đã phân loại nhầm bài viết trong bộ kiểm thử. Nghiên cứu không báo cáo rằng học sinh trong mẫu nghiên cứu đã bị một trường cụ thể kỷ luật. Hậu quả về điểm số, danh tiếng hoặc kỷ luật dưới đây là nguy cơ nếu trường dùng detector làm bằng chứng duy nhất.

### Harm Map Worksheet - detector bài viết AI

| Trường | Phân tích |
| --- | --- |
| High-risk moment | Giáo viên hoặc nhà trường dùng nhãn "AI-generated" của detector để kết luận học sinh gian lận, trước khi trao đổi với học sinh hoặc kiểm tra bản nháp/quá trình làm bài. |
| Stakeholder bị ảnh hưởng | Học sinh viết tiếng Anh không bản ngữ, đặc biệt người có vốn từ vựng và cách diễn đạt bị giới hạn; giáo viên và nhà trường cũng bị ảnh hưởng bởi kết luận sai. |
| Failure mode | Bias / fairness: lỗi dương tính giả không đồng đều theo nhóm người viết. |
| Layer bắt đầu lỗi | Model: đầu ra phân loại của các detector sai lệch trên mẫu bài viết này. Cách nhà trường dùng đầu ra để kỷ luật là một tầng quy trình riêng; nghiên cứu không đánh giá chính sách từng trường. |
| Harm xảy ra là gì? | Nghiên cứu ghi nhận lỗi phân loại, không ghi nhận một vụ kỷ luật cụ thể. Nguy cơ: học sinh có thể bị nghi oan, mất điểm/cơ hội học tập, hoặc bị áp dụng quy trình kỷ luật không công bằng nếu nhãn detector được xem là kết luận chắc chắn. |
| Harm lens | Opportunity loss và dignity loss: nguy cơ mất điểm/cơ hội và bị nghi ngờ không công bằng. |
| Severity | High nếu nhãn AI dẫn đến trượt môn, kỷ luật hoặc ảnh hưởng hồ sơ; Medium nếu chỉ dẫn đến việc phải giải trình và được sửa ngay. Mức độ phụ thuộc hậu quả thực tế, không được nghiên cứu đo trực tiếp. |
| Scale | Bộ kiểm thử gồm 91 bài TOEFL; trung bình 61,22% dương tính giả. Trong bộ này, 18 bài bị cả 7 detector gắn nhãn AI và 89 bài bị ít nhất một detector gắn nhãn AI. Không đủ thông tin để suy ra tỷ lệ trong các lớp học nói chung. |
| Probability | Khả năng detector nhận nhầm được quan sát trong bộ kiểm thử; xác suất một học sinh bị kỷ luật không được nghiên cứu này đo. |
| Frequency | Nghiên cứu không đo tần suất các trường sử dụng detector hoặc tần suất kỷ luật nhầm. Nếu trường chạy detector trên mỗi bài nộp, mỗi bài là một cơ hội phát sinh cần kiểm tra; đây là suy luận về quy trình. |
| Vì sao? | Số liệu 91 bài và 61,22% là kết quả của nghiên cứu Liang và cộng sự. Các hậu quả về kỷ luật là phân tích rủi ro nếu đầu ra bị dùng sai mục đích; không trình bày chúng như sự kiện đã xảy ra. |

## 4. Kết luận và biện pháp giảm thiểu

- Dùng AI như công cụ hỗ trợ, không thay giáo viên trong chấm điểm, kết luận gian lận hoặc quyết định quan trọng.
- Yêu cầu học sinh kiểm tra lời giải; ưu tiên tutor đưa gợi ý và câu hỏi hướng dẫn thay vì chỉ trả đáp án.
- Không xem detector AI là bằng chứng duy nhất. Giáo viên nên xem quá trình làm bài, trao đổi với học sinh và cho phép khiếu nại.
- Thông báo rõ dữ liệu học tập nào được thu thập, ai có thể xem và dữ liệu được lưu bao lâu.
- Các biện pháp trên là đề xuất của tôi dựa trên hai nghiên cứu, không phải kết quả thử nghiệm của chính các nghiên cứu này.

## 5. Tài liệu tham khảo

1. Bastani, H. và cộng sự (2025). [Generative AI without guardrails can harm learning: Evidence from high school mathematics. PNAS](https://doi.org/10.1073/pnas.2422633122).
2. Liang, W., Yuksekgonul, M., Mao, Y., Wu, E., & Zou, J. (2023). [GPT detectors are biased against non-native English writers. Patterns](https://doi.org/10.1016/j.patter.2023.100779). [Bản toàn văn arXiv](https://arxiv.org/abs/2304.02819).
