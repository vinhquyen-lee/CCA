# CCA
### 1. Giới thiệu
  Phân tích Tương quan Chính tắc (Canonical Correlation Analysis - CCA) là một kỹ
thuật thống kê đa biến được sử dụng để nhận diện và đo lường mối liên hệ/tương quan
giữa hai tập hợp các biến. Nó giúp hiểu rõ mối quan hệ này bằng cách tối đa hóa tương
quan giữa các tổ hợp tuyến tính của các biến trong hai tập hợp đó. Trong xử lý ảnh/video,
CCA có thể được áp dụng để tìm mối liên hệ giữa các tập hợp đặc trưng (feature sets)
trích xuất từ các khía cạnh khác nhau của dữ liệu (ví dụ: đặc trưng hình ảnh và đặc trưng
âm thanh của video, hoặc đặc trưng từ hai góc nhìn khác nhau của cùng một vật thể).
### 2. Thực hiện CCA
- Triển khai thuật toán CCA: Xây dựng hoặc sử dụng cài đặt thuật toán CCA
để tìm ra các biến chính tắc (canonical variates).
- Phân tích tương quan chính tắc và hệ số tải (loadings): Nghiên cứu giá trị
của các tương quan chính tắc và các hệ số tải của biến gốc trên các biến chính
tắc để hiểu bản chất mối quan hệ giữa hai tập hợp biến ban đầu.
- Trực quan hóa kết quả: Sử dụng các phương pháp như biểu đồ phân tán
(scatter plots) hoặc biểu đồ tọa độ song song (parallel coordinates) để hiển thị
mối quan hệ giữa các biến gốc và các biến chính tắc.
### 3. Các Khái niệm Chính
- Biến Chính tắc (Canonical Variables): Là các tổ hợp tuyến tính của các biến
gốc trong mỗi tập hợp. Các tổ hợp này được tạo ra sao cho tương quan giữa hai
tập hợp biến chính tắc (từ hai tập hợp gốc) là lớn nhất có thể.
- Tương quan Chính tắc (Canonical Correlation): Là giá trị tương quan giữa
hai biến chính tắc tương ứng (một từ mỗi tập hợp). Giá trị này định lượng độ
mạnh và chiều hướng của mối quan hệ giữa hai tập hợp biến gốc. Có tối đa
min(số biến tập 1, số biến tập 2) cặp biến chính tắc và tương quan chính tắc.
- Diễn giải (Interpretation): CCA cho phép diễn giải ý nghĩa của mối quan hệ
giữa hai tập hợp biến (ví dụ: các đặc trưng hình ảnh liên quan đến đặc trưng
### 4. Tập dữ liệu
- Nguồn: tập dữ liệu Iris từ thư viện scikit-learn
- Mô tả: tập dữ liệu này bao gồm chiều dài và chiều rộng của cánh hoa (petal) và
đài hoa (sepal) của 3 loại hoa diên vĩ (iris) khác nhau: Setosa, Versicolour, và
Virginica.
- Mục tiêu: tập trung vào các đặc trưng mô tả hoa. (Trong bối cảnh thị giác máy
tính, ta hình dung đây là việc trích xuất các đặc trưng hình dạng/kích thước từ
ảnh của hoa).
### 5. Note
  Cho hai ma trận X (với n đặc trưng) và Y (với m đặc trưng). (Trong ngữ cảnh xử lý
ảnh/video, mỗi hàng của ma trận có thể là một mẫu dữ liệu/đối tượng, và các cột là
giá trị của các đặc trưng được trích xuất).

  CCA trước tiên sẽ tìm một tổ hợp tuyến tính của các biến trong X (gọi là U1) và một
tổ hợp tuyến tính của các biến trong Y (gọi là V1) sao cho U1 và V1 có tương quan
cao nhất với nhau.

  Các tổ hợp tuyến tính này được gọi là biến chính tắc (canonical variates).
  
  CCA sẽ tiếp tục tìm cặp biến chính tắc tiếp theo (U2 và V2) có tương quan cao nhất
với nhau, NHƯNG không tương quan với cặp biến chính tắc đầu tiên (U1 và V1).

  Quá trình này lặp lại để tìm các cặp biến chính tắc tiếp theo cho đến khi hết các chiều
tương quan có ý nghĩa.

