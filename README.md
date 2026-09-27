# EduFold VN: Nền Tảng AI Khám Phá Sinh Học Cấu Trúc 3D

**Hạng mục tham gia (Track):** AI-Native Products & Operations
**Tài liệu đính kèm:** image_4db176.jpg

---

## 1. Tóm Tắt Dự Án (Executive Summary)

Việc hiểu rõ cấu trúc không gian của các đại phân tử sinh học, điển hình là protein và các đột biến gen, đóng vai trò then chốt trong việc hình thành tư duy trực quan về sinh học phân tử. Tuy nhiên, chương trình giáo dục phổ thông tại Việt Nam hiện nay hầu như chỉ phụ thuộc vào các sơ đồ 2D tĩnh trong sách giáo khoa. Sự hạn chế này làm giảm khả năng hình dung của học sinh về những thay đổi cấu hình không gian do đột biến gây ra, dẫn đến việc nắm bắt các khái niệm sinh học cấu trúc không thực sự vững chắc.

Mặc dù cộng đồng khoa học đã xây dựng những cơ sở dữ liệu 3D chi tiết như AlphaFold, cùng các tài liệu tham khảo quốc tế chuẩn mực (như Campbell Biology), học sinh Việt Nam vẫn không thể tận dụng trực tiếp các nguồn tài nguyên này. Nguyên nhân cốt lõi đến từ rào cản ngôn ngữ chuyên ngành, sự phức tạp của phần mềm và sự thiếu hụt các định hướng sư phạm.

EduFold VN được phát triển nhằm giải quyết triệt để các vấn đề trên. Chúng tôi xây dựng một nền tảng tương tác chạy hoàn toàn trên nền tảng web, sử dụng tiếng Việt làm ngôn ngữ giao tiếp chính. Hệ thống kết hợp giữa trình xem đồ họa 3D WebGL và một Trợ lý Trí tuệ Nhân tạo (LLM) được giới hạn chặt chẽ bởi kỹ thuật RAG (Retrieval-Augmented Generation). Kết quả đầu ra là một công cụ giảng dạy sinh học cấu trúc giúp loại bỏ khoảng cách từ mô hình 2D sang 3D, hỗ trợ học sinh xây dựng tư duy phân tử một cách trực quan, chính xác và an toàn về mặt thông tin khoa học.

---

## 2. Bối Cảnh Và Phân Tích Vấn Đề

Quá trình tiếp cận sinh học phân tử hiện đại của học sinh trung học phổ thông đang gặp phải ba rào cản thực tiễn:

*   **Rào Cản Ngôn Ngữ Học Thuật:** Các tài liệu cấu trúc 3D có độ chi tiết cao và các nền tảng quốc tế hầu hết đều sử dụng tiếng Anh. Học sinh và các nhà nghiên cứu gặp khó khăn khi phân tích các cấu trúc 3D của AlphaFold vì dữ liệu sử dụng nhiều thuật ngữ chuyên ngành khiến cho khả năng tiếp cận với công chúng không quá rộng rãi[cite: 1].
*   **Độ Phức Tạp Của Nền Tảng Công Nghệ:** Việc quan sát mô hình 3D thông thường yêu cầu tải xuống các tệp dữ liệu thô và cài đặt phần mềm chuyên dụng. Các phần mềm chuyên dụng hiện nay thường khá nặng hoặc khó cài đặt[cite: 1]. Điều này khiến người dùng không hiểu được cấu trúc đó có ý nghĩa gì[cite: 1], đồng thời quy trình này hoàn toàn không khả thi để triển khai đại trà trong điều kiện cơ sở vật chất của các trường phổ thông.
*   **Thiếu Tính Định Hướng Sư Phạm:** Các cơ sở dữ liệu lớn hiện nay chỉ cung cấp dữ liệu thô của mô hình phân tử mà không mang tính chất hướng dẫn hay giảng dạy. Không có tài liệu nào giải thích chi tiết ý nghĩa của một đột biến cụ thể theo ngôn ngữ dễ hiểu, khiến học sinh bị ngợp trước khối lượng thông tin không được cấu trúc hóa cho mục đích giáo dục.

---

## 3. Đối Tượng Mục Tiêu

Hệ thống được thiết kế tối ưu cho nhóm đối tượng: Học sinh phổ thông và người học sinh học phân tử và tế bào cần một cách dễ tiếp cận để khám phá sinh hóa và cấu trúc phân tử[cite: 1]. Bên cạnh đó, dự án cũng hướng tới việc trở thành công cụ hỗ trợ đắc lực cho giáo viên bộ môn Sinh học trong quá trình giảng dạy trực quan trên lớp.

---

## 4. Giải Pháp Của EduFold VN

Giải pháp nhóm em đưa ra là một nền tảng tích hợp mô hình 3D có thể tương tác, kết hợp với AI hỏi đáp thông minh và cho phép người dùng phân tích đột biến trên mô hình máy tính[cite: 1]. Các trụ cột của giải pháp bao gồm:

*   **Trình Xem Đồ Họa WebGL Trực Tiếp:** Giao diện người dùng được thiết kế để hiển thị mô hình 3D thông qua thư viện Three.js ngay trên trình duyệt web tiêu chuẩn. Yếu tố này giúp loại bỏ hoàn toàn yêu cầu cài đặt phần mềm, tương thích với mọi thiết bị tại trường học.
*   **Cơ Chế So Sánh Trình Tự Phân Tử:** Nền tảng cho phép tải và đặt cạnh nhau hai mô hình: dạng tự nhiên (wild-type) và dạng đột biến (mutant). Từ đó, trực quan hóa sự đứt gãy hoặc hình thành các liên kết hóa học mới do sự thay đổi của một axit amin duy nhất.
*   **AI Sinh Học Được Kiểm Soát (Controlled LLM with RAG):** Để ngăn chặn hiện tượng AI tự suy diễn kiến thức sai lệch (hallucination), hệ thống sử dụng phương pháp tạo prompt có hỗ trợ truy xuất (Retrieval-Based Prompting). AI chỉ được phép tổng hợp câu trả lời và giải thích các hiện tượng dựa trên một bộ dữ liệu đột biến đã được chọn lọc và kiểm chứng bởi các chuyên gia khoa học (như ClinVar, UniProt). Toàn bộ nội dung đầu ra được tự động chuyển ngữ sang tiếng Việt thân thiện, dễ hiểu.

---

## 5. Kiến Trúc Công Nghệ & Khai Thác Tiềm Năng AI (Hackathon Operations)

EduFold VN áp dụng kiến trúc Client-Server tách biệt, kết hợp luồng xử lý AI tối ưu cho tốc độ phản hồi thời gian thực:

*   **Frontend:** Xây dựng bằng HTML/JavaScript, tập trung vào khả năng xử lý đồ họa thông qua WebGL/Three.js.
*   **Backend:** Phát triển trên nền tảng Java Spring Boot, cung cấp hệ thống API RESTful và chịu trách nhiệm xử lý các thuật toán so sánh trình tự sinh học phức tạp.

**Ứng dụng thực tiễn của công cụ AI (Codex) trong quá trình thi đấu:**
Bám sát định hướng "AI-Native Products & Operations", đội ngũ phát triển đã đưa Codex vào sâu trong chuỗi quy trình sản xuất mã nguồn nhằm tối ưu hóa thời gian xây dựng sản phẩm. Team em sẽ sử dụng Codex để nhanh chóng sinh mã backend tích hợp API với cơ sở dữ liệu cấu trúc, viết các thành phần frontend cho trình xem 3D và tối ưu hóa các script phân tích hỗ trợ bởi AI[cite: 1]. Nhờ đó, nhóm giảm thiểu được rủi ro lỗi cú pháp và tập trung toàn lực vào việc tinh chỉnh logic nghiệp vụ cũng như trải nghiệm người dùng.

---

## 6. Phương Pháp Đánh Giá Hiệu Quả Nghiên Cứu

Để đảm bảo giá trị học thuật và tính ứng dụng thực tế, dự án đề xuất quy trình đánh giá hai giai đoạn:

1.  **Thử Nghiệm Khả Năng Sử Dụng (Pilot Testing):** Một nhóm học sinh trung học sẽ trải nghiệm phiên bản MVP với một tập hợp các đột biến đã được chọn lọc sẵn. Quá trình này được theo sau bởi một bài kiểm tra ngắn nhằm đo lường mức độ thông hiểu lý thuyết cũng như thu thập phản hồi về giao diện thao tác.
2.  **Đánh Giá Đối Chứng (A/B Testing):** Tổ chức đo lường hiệu quả học tập thông qua việc so sánh hai nhóm học sinh: một nhóm sử dụng EduFold VN và nhóm đối chứng sử dụng sách giáo khoa 2D truyền thống. Thang đo được xác định bằng hiệu suất trả lời các câu hỏi đòi hỏi tư duy về không gian cấu trúc và dự đoán tác động của biến thể.

---

## 7. Lộ Trình Phát Triển (Roadmap)

**Giai Đoạn 1: Ngắn Hạn**
*   Mở rộng bộ dữ liệu đột biến đã qua chọn lọc, tập trung trực tiếp vào các ví dụ đột biến có trong chương trình Sinh học phổ thông tại Việt Nam nhằm tăng cường tính gắn kết với thực tế giảng dạy.
*   Thay thế cơ chế căn chỉnh trình tự hiện tại bằng các thuật toán sinh tin học chuyên sâu (như thuật toán Needleman-Wunsch cho căn chỉnh toàn cục), giúp hỗ trợ đa dạng các loại đột biến bao gồm cả chèn đoạn (insertion) và mất đoạn (deletion).
*   Tích hợp hệ thống trích dẫn nguồn gốc tài liệu trực tiếp vào nội dung phản hồi của AI để đảm bảo tính minh bạch học thuật.

**Giai Đoạn 2: Trung Hạn**
*   Tiến hành hợp tác với các tổ chuyên môn Sinh học tại các trường THPT để đưa nền tảng vào thử nghiệm trong các giờ học thực tế.
*   Đo lường mức độ tương tác và cải thiện kỹ thuật thiết kế Prompt cho AI dựa trên cơ sở dữ liệu truy vấn thực tế của học sinh.

**Giai Đoạn 3: Dài Hạn**
*   Mở rộng năng lực xử lý dữ liệu của hệ thống, hướng tới việc tích hợp lượng dữ liệu cấu trúc khổng lồ tương đương quy mô của thư viện AlphaFold.
*   Phát triển các phân hệ dành riêng cho giáo viên, cho phép khởi tạo các bài kiểm tra thực hành (quiz) ngay trên giao diện quan sát 3D.
*   Nghiên cứu kiến trúc đa ngôn ngữ (Internationalization) nhằm triển khai dự án đến các khu vực quốc gia đang phát triển khác gặp chung rào cản về ngôn ngữ trong giáo dục khoa học tự nhiên.
