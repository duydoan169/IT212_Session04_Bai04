Đáp án: Phương án B

Phân Tích Phương Án B (Tối ưu nhất)
Phương án B thể hiện đúng tư duy Iterative Prompting vì đáp ứng đủ 3 yếu tố then chốt:

Chỉ ra vấn đề bằng thông số cụ thể: Không nói chung chung "chạy chậm" mà nêu rõ

độ phức tạp hiện tại là O(2^N) và trường hợp thực tế gây sập là n = 50 -

AI có đủ cơ sở kỹ thuật để hiểu đúng mức độ nghiêm trọng của vấn đề.
Chỉ định kỹ thuật thay thế rõ ràng: Yêu cầu đích danh Dynamic Programming

với 2 phương án cụ thể là Tabulation hoặc Memoization,

không để AI tự chọn hướng giải quyết theo ý muốn.
Ràng buộc kỹ thuật đầy đủ: Xác định rõ mục tiêu cần đạt là O(N) về thời gian,

O(1) hoặc O(N) về không gian, và giữ nguyên kiểu trả về long -

3 ràng buộc này ngăn AI tự ý thay đổi interface hoặc đề xuất giải pháp đúng ý tưởng nhưng sai chi tiết kỹ thuật.

Đây là cách Iterative Prompting hoạt động đúng: giữ nguyên phiên chat,

đánh giá kết quả cũ, nhận diện đúng điểm yếu, và tinh chỉnh với thông tin đủ cụ thể

để AI không phải đoán mò.

Phân Tích Phương Án A (Chưa đạt)
Phương án A mắc đúng lỗi mà prompt thô thường gặp - phản hồi quá mơ hồ.

Không chỉ ra nguyên nhân cụ thể: "Chạy chậm quá" không cung cấp thông tin gì

về độ phức tạp thuật toán - AI không biết chậm ở mức O(N²) hay O(2^N),

dẫn đến có thể đề xuất giải pháp chỉ cải thiện một phần như dùng vòng lặp thay đệ quy

nhưng vẫn không tối ưu về không gian.
Không ràng buộc kỹ thuật: "Thuật toán khác tối ưu hơn" là yêu cầu hoàn toàn mở -

AI có thể đề xuất ma trận nhân (Matrix Exponentiation) với O(log N),

công thức Binet với dấu phẩy động gây sai số với N lớn,

hoặc bất kỳ hướng nào AI cho là "tối ưu hơn" mà không phù hợp với yêu cầu thực tế.
Không giữ ràng buộc interface: Không nhắc giữ nguyên kiểu trả về long,

AI có thể đổi sang int hoặc BigInteger làm ảnh hưởng đến code đang dùng hàm này.


Phân Tích Phương Án C (Chưa đạt)
Phương án C mắc lỗi nghiêm trọng hơn A vì chỉ định sai hoàn toàn kỹ thuật cần áp dụng.

Stream API không giải quyết được vấn đề gốc rễ: Vấn đề cốt lõi là thuật toán đệ quy

tính lại các giá trị đã tính hàng triệu lần - đây là lỗi thuật toán,

không phải lỗi thiếu tính song song. Chạy song song một thuật toán O(2^N)

không làm giảm độ phức tạp, chỉ phân tán tải sang nhiều luồng nhưng vẫn treo hệ thống với N lớn.
Parallel Stream không phù hợp với bài toán phụ thuộc tuần tự:

Fibonacci có tính chất mỗi giá trị phụ thuộc vào 2 giá trị trước đó -

đây là bài toán có phụ thuộc tuần tự (sequential dependency),

không thể song song hóa hiệu quả bằng Stream API.
Nguy cơ kết quả sai: Xử lý song song trên bài toán có phụ thuộc thứ tự

có thể dẫn đến race condition nếu AI sinh code không xử lý đồng bộ hóa đúng cách.