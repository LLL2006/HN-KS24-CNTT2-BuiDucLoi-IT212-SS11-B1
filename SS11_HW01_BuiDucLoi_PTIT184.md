# Bài 1: Phân Tích & Lựa Chọn Phương Án Tạo Mã Nguồn (Lesson 01)

- Đáp án chọn: Phương án B.

- Lý do chọn phương án B:
  - Phương án B là phương án tối ưu nhất vì nó có cấu trúc prompt đầy đủ, rõ ràng và có tính hướng dẫn cao. Đây là kiểu prompt phù hợp nhất khi muốn sử dụng AI để sinh mã nguồn trong môi trường dự án thực tế, nơi yêu cầu không chỉ là “viết code” mà còn phải đúng chuẩn kỹ thuật, đúng ngữ cảnh nghiệp vụ và đúng định dạng đầu ra.
  - Nếu xét theo cấu trúc 5 thành phần của prompt thì phương án B thể hiện đầy đủ cả năm phần một cách rất tự nhiên:
    - Vai trò (Role): câu prompt đã yêu cầu AI đóng vai “Senior Java Developer”, nghĩa là AI sẽ phản hồi theo tư duy của một lập trình viên có kinh nghiệm, thay vì chỉ đưa ra câu trả lời chung chung.
    - Nhiệm vụ (Task): prompt nêu rõ mục tiêu là viết class PaymentValidator để kiểm tra tính hợp lệ của số thẻ tín dụng bằng thuật toán Luhn.
    - Ngữ cảnh (Context): prompt cho biết đây là hệ thống E-commerce và việc validate cần diễn ra trước khi gửi API thanh toán. Nhờ đó, AI hiểu được mục đích sử dụng của class trong hệ thống chứ không chỉ hiểu nó như một bài tập lập trình đơn thuần.
    - Ràng buộc (Constraints): prompt đưa ra các giới hạn rất cụ thể như dùng Java 17, triển khai thuật toán Luhn, và ném IllegalArgumentException khi thẻ rỗng hoặc chứa chữ cái. Đây là phần rất quan trọng vì nó giúp giới hạn phạm vi sáng tạo của AI và làm cho kết quả gần với yêu cầu thực tế của dự án hơn.
    - Định dạng đầu ra (Output format): prompt yêu cầu chỉ trả về mã nguồn Java trong một code block và không giải thích. Điều này giúp loại bỏ phần thừa, giảm nhiễu và làm cho đầu ra dễ dùng ngay trong quá trình phát triển.
  - Chính vì có đủ các yếu tố trên, phương án B giúp AI hiểu đúng yêu cầu từ đầu, tránh việc sinh ra code thiếu sót, sai logic hoặc không phù hợp với quy chuẩn kỹ thuật của dự án. Nó vừa tập trung vào yêu cầu chính, vừa giảm tối đa khả năng AI tự suy đoán quá mức.

- Phân tích phương án A:
  - Phương án A là một prompt khá ngắn và thiếu chi tiết. Nó chỉ nói chung chung rằng cần viết một class Java tên PaymentValidator để kiểm tra số thẻ tín dụng bằng thuật toán Luhn, rồi thêm câu “code ngắn gọn thôi nhé”.
  - Điểm yếu lớn nhất của phương án này là nó bỏ qua nhiều thông tin cốt lõi. Không có vai trò rõ ràng, không có ngữ cảnh nghiệp vụ, không có ràng buộc kỹ thuật cụ thể, và cũng không nêu rõ định dạng đầu ra cần nhận được.
  - Vì vậy, AI có thể sinh ra một đoạn code đúng về ý tưởng cơ bản nhưng không chắc đã đúng với chuẩn dự án. Ví dụ, code có thể không xử lý trường hợp thẻ rỗng hoặc chứa ký tự chữ cái, hoặc không có cách xử lý ngoại lệ như mong muốn. Ngoài ra, kết quả cũng có thể khác nhau giữa các lần gọi AI vì prompt quá mơ hồ.
  - Đây là kiểu prompt dễ dẫn tới sai lệch ngữ cảnh và rủi ro hallucination, vì AI phải tự “đoán” nhiều thứ mà người dùng chưa nói rõ.

- Phân tích phương án C:
  - Phương án C là phương án kém hiệu quả nhất vì nó sai lệch hoàn toàn khỏi mục tiêu chính. Prompt không chỉ yêu cầu viết code Java cho PaymentValidator mà còn yêu cầu AI sinh thêm database SQL, hướng dẫn cài đặt database và kết nối JDBC.
  - Khi một prompt yêu cầu quá nhiều nhiệm vụ khác nhau cùng lúc, AI thường sẽ bị phân tán và khó tập trung vào phần quan trọng nhất. Kết quả có thể là code Java bị làm quá dài, thiếu tập trung, hoặc có thêm các thành phần không cần thiết.
  - Điều này làm tăng nguy cơ trả về nội dung thừa, không đúng trọng tâm và thậm chí có thể tạo ra các phần không liên quan đến bài toán đang giải quyết. Trong thực tế, đây là một dạng prompt dễ gây lãng phí thời gian và làm giảm chất lượng đầu ra.
  - Ngoài ra, phương án C còn làm tăng nguy cơ hallucination vì AI phải tự đưa ra nhiều thông tin bên ngoài phạm vi cần thiết, trong khi người dùng chỉ thực sự cần một lớp validate thẻ tín dụng đơn lẻ.

- Kết luận:
  - Nhìn chung, phương án B là lựa chọn tối ưu nhất vì nó vừa đủ chi tiết, vừa tập trung đúng trọng tâm, đồng thời có cấu trúc prompt rõ ràng, logic và phù hợp với mục tiêu sử dụng AI trong phát triển phần mềm. So với phương án A, nó cho đầu ra chính xác và có ràng buộc hơn; so với phương án C, nó không bị lan man và không làm sai lệch yêu cầu ban đầu.
