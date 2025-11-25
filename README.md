🚦 Metro Interstate Traffic Volume — Time Series Forecasting Project
Dự án này xây dựng một End-to-End Time Series Forecasting Pipeline dựa trên bộ dữ liệu Metro Interstate Traffic Volume.
Mục tiêu chính là phân tích, tiền xử lý, khám phá dữ liệu (EDA) và huấn luyện mô hình dự báo lưu lượng giao thông theo từng giờ (Hourly Volume).

📌 1. Giới thiệu dự án
* Dự báo lưu lượng giao thông là một bài toán quan trọng trong:
* Quy hoạch đô thị
* Giảm ùn tắc giao thông
* Tối ưu hạ tầng đường bộ
* Hỗ trợ các hệ thống thông minh ITS (Intelligent Transportation Systems)
* Trong dự án này, chúng tôi xây dựng các bước từ EDA → mô hình hóa → đánh giá → trực quan hóa dự báo so với dữ liệu thực.

📂 2. Cấu trúc thư mục
'''bash
project/
│-- data/
│   └── Metro_Interstate_Traffic_Volume.csv
│
│-- notebooks/
│   └── traffic_volume_forecasting.ipynb
│
│-- models/
│   └── saved_models/ (tuỳ chọn)
│
│-- README.md
│-- requirements.txt

🧹 3. Các bước xử lý dữ liệu
Notebook gồm các bước chính:

✔ 3.1. Load & Clean Data
* Chuyển đổi date_time → DatetimeIndex
* Sắp xếp theo thời gian
* Kiểm tra missing values
* Loại bỏ outliers (nếu cần)

✔ 3.2. Feature Engineering
* Tách các đặc trưng thời gian: hour, dayofweek, month, year
* Encode các biến categorical như: weather_main, weather_description
* Chuẩn hóa dữ liệu (nếu mô hình yêu cầu)

📊 4. Exploratory Data Analysis (EDA)

Notebook đã thực hiện nhiều phân tích quan trọng:
Biểu đồ xu hướng theo thời gian (long-term trend)
* Seasonal patterns: theo giờ, theo ngày trong tuần, theo tháng
* Ảnh hưởng của thời tiết đến lưu lượng xe
* Kiểm tra phân phối traffic volume

Một số insight nổi bật:
Giờ cao điểm rõ ràng khoảng 7–9 AM và 4–6 PM
Lượng xe thấp vào cuối đêm và rạng sáng
Một số điều kiện thời tiết như “Rain”, “Snow” kéo giảm traffic volume

🤖 5. Các mô hình được xây dựng

Notebook huấn luyện và so sánh hiệu năng của nhiều mô hình:

🔹 5.1. ARIMA/SARIMA (tuỳ chọn)

Mô hình thống kê cổ điển cho dữ liệu time series

🔹 5.2. LSTM

Mạng nơ-ron hồi quy truyền thống cho dữ liệu chuỗi thời gian

🔹 5.3. GRU

Biến thể nhẹ hơn của LSTM nhưng tốc độ nhanh hơn

🔹 5.4. Stacked LSTM

Kiến trúc nhiều tầng LSTM để học phụ thuộc dài hạn tốt hơn

Tất cả mô hình đều được đánh giá bằng:

RMSE

MAE

MAPE

R2

📈 6. Biểu đồ trực quan (Graphs Included)

Notebook có đầy đủ biểu đồ:

Actual vs Predicted Plot

Residual Plot

Train vs Test Visualization

Learning Curves (nếu có)

Ví dụ biểu đồ chính:

Actual vs Predicted
Residual Errors
Train-Test Split Visualization

🧪 7. Các thí nghiệm & kết quả
Model	MAE	RMSE	Notes
LSTM	...	...	baseline RNN
GRU	...	...	cải thiện độ chính xác
Stacked LSTM	...	...	tốt nhất nhưng tốn thời gian

(Bạn có thể điền số liệu thực tế khi chạy notebook.)

🚀 8. Cách chạy dự án
8.1. Clone repository
git clone https://github.com/<your_username>/<repo_name>.git
cd <repo_name>

8.2. Tạo môi trường & cài dependencies
pip install -r requirements.txt

8.3. Mở notebook
jupyter notebook


Chạy file:

notebooks/traffic_volume_forecasting.ipynb

📦 9. File requirements.txt (tham khảo)
pandas
numpy
matplotlib
seaborn
scikit-learn
tensorflow
statsmodels
jupyter

🎯 10. Mục tiêu hướng tới (Future Work)

Áp dụng mô hình Transformer cho Time Series (Informer / TFT / LongNet / PatchTST)

Hyperparameter tuning với Optuna

Triển khai API dự báo bằng FastAPI

Deploy mô hình lên Streamlit / Gradio
