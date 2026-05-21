**Tổng quan dự án khai phá dữ liệu**

Dự án này tập trung vào việc áp dụng các kỹ thuật khai phá dữ liệu và học máy để giải quyết các bài toán thực tế trong quản trị nhân sự và thương mại điện tử. Dưới đây là mô tả chi tiết về hai bài toán chính cùng các kết quả rút ra từ các mô hình.

**1. Dự án quản trị nhân sự IBM HR Analytics**
Tập tin liên quan: Data_mining1_6.ipynb

* Mô tả bài toán
Dự án phân tích hành vi và dự đoán nguy cơ nghỉ việc của nhân viên nhằm giúp bộ phận nhân sự chủ động xây dựng chính sách giữ chân nhân tài. Dữ liệu gốc gồm 1470 dòng và 35 thuộc tính được làm sạch còn 31 thuộc tính. Bài toán được giải quyết qua hai phương pháp là phân loại nhị phân và phân cụm dữ liệu.

* Mô hình phân loại và kết quả đạt được
Mô hình sử dụng gồm có Decision Tree, Random Forest và XGBoost. Kết quả thực nghiệm cho thấy thuật toán XGBoost đạt hiệu năng tốt nhất với chỉ số AUC là 0.807, tiếp sau là Random Forest đạt AUC là 0.797, và Decision Tree đạt AUC là 0.700.
Các đặc trưng quan trọng nhất dẫn đến nghỉ việc là làm thêm giờ OverTime, mức thu nhập tháng MonthlyIncome và độ tuổi Age. Nhóm nhân sự trẻ tuổi dưới 30 tuổi có thâm niên thấp dưới 5 năm và phải làm thêm giờ liên tục là nhóm có nguy cơ nghỉ việc cao nhất.

* Phân cụm nhân viên và kết quả
Sử dụng thuật toán K Prototypes và DBSCAN để phân nhóm nhân sự. K Prototypes chia nhân viên thành các cụm đặc trưng dựa trên sự cân bằng giữa thâm niên và thu nhập. DBSCAN giúp phát hiện các nhóm nhân sự cá biệt có giá trị cao như các quản lý cấp cao có thu nhập vượt trội để doanh nghiệp lập kế hoạch chuyển giao kiến thức.


**2. Dự án thương mại điện tử Olist E Commerce**
Tập tin liên quan: Data_mining2_fixed_v2.ipynb

* Mô tả bài toán
Dự án giải quyết hai bài toán kinh doanh cốt lõi của sàn thương mại điện tử Olist là dự đoán phản hồi tiêu cực của khách hàng từ 1 đến 2 sao và dự đoán nguy cơ đơn hàng giao trễ ngay tại thời điểm đặt hàng.

* Bài toán dự đoán phản hồi tiêu cực
Mô hình sử dụng gồm có Logistic Regression Baseline và XGBoost Advance. Kết quả cho thấy XGBoost cải thiện rõ rệt chỉ số F1 Score lên 0.42 và đạt AUC là 0.72 so với Baseline. Đặc trưng quyết định đến việc đánh giá thấp của khách hàng là số ngày giao hàng trễ delivery_delay_days, theo sau là giá trị đơn hàng và chi phí vận chuyển.

* Bài toán dự đoán đơn hàng giao trễ
Mô hình sử dụng gồm có Decision Tree Tuned, Random Forest Tuned và Ensemble Voting Classifier Tuned. Mô hình Random Forest đã qua tối ưu đạt AUC cao nhất ở mức 0.5900, và Ensemble Voting đạt AUC là 0.5874. Các đặc trưng quan trọng nhất dẫn đến giao trễ là cước phí vận chuyển total_freight, chỉ số cùng bang hay khác bang same_state và giá trị đơn hàng.

* Khuyến nghị nghiệp vụ cốt lõi
Doanh nghiệp cần tích hợp mô hình dự báo vào hệ thống quản lý kho WMS để gắn nhãn ưu tiên đóng gói cho các đơn hàng có xác suất trễ trên 50 phần trăm. Đồng thời cần tối ưu hóa logistics liên bang bằng cách tự động điều hướng sang các dịch vụ chuyển phát nhanh và ưu tiên mở rộng mạng lưới người bán tại các bang trọng điểm như SP, RJ, MG để rút ngắn khoảng cách giao nhận.