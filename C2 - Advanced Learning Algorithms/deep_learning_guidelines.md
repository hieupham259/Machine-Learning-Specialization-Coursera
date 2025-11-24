# Hướng dẫn chọn Activation, Optimizer, Loss, Metrics trong Deep Learning

## 1. Activation Functions

### 1.1 Bài toán phân loại nhị phân

-   **Output activation:** `sigmoid`
-   **Hidden layers:** `ReLU`, `LeakyReLU`
-   **Lý do:** Sigmoid cho output dạng xác suất (0--1).

### 1.2 Phân loại đa lớp (multi-class)

-   **Output activation:** `softmax`
-   **Hidden layers:** `ReLU`, `GELU`
-   **Lý do:** Softmax chuẩn hóa các lớp thành phân phối xác suất.

### 1.3 Hồi quy (regression)

-   **Output activation:** không dùng activation (linear)
-   **Hidden layers:** ReLU/GELU
-   **Lý do:** Giá trị đầu ra là số thực liên tục.

------------------------------------------------------------------------

## 2. Optimizer

### 2.1 Adam

-   Dùng cho hầu hết mọi bài toán.
-   Tốt khi dữ liệu vừa/phức tạp.

### 2.2 SGD + Momentum

-   Tốt cho mô hình lớn (CNN, Vision)
-   Tối ưu chậm nhưng ổn định và tổng quát hóa tốt hơn.

### 2.3 RMSProp

-   Tốt cho sequence (RNN, LSTM)
-   Thường dùng trong reinforcement learning.

------------------------------------------------------------------------

## 3. Loss Functions

### 3.1 Binary classification

-   **BinaryCrossentropy**

### 3.2 Multi-class classification

-   **SparseCategoricalCrossentropy** (nhãn dạng số)
-   **CategoricalCrossentropy** (one-hot)

### 3.3 Regression

-   **MSE** (Mean Squared Error)
-   **MAE** (Mean Absolute Error)
-   **Huber Loss** (chống outlier)

------------------------------------------------------------------------

## 4. Metrics

### 4.1 Binary classification

-   `accuracy`
-   `precision`, `recall`, `F1`

### 4.2 Multi-class classification

-   `accuracy`
-   Macro/micro precision, recall

### 4.3 Regression

-   `MAE`
-   `MSE`
-   `RMSE`
-   `R²`

------------------------------------------------------------------------

## 5. Tổng hợp theo từng bài toán

  Bài toán   Activation output   Loss                 Optimizer   Metrics
  ---------- ------------------- -------------------- ----------- --------------
  Nhị phân   Sigmoid             BinaryCrossentropy   Adam        Accuracy, F1
  Đa lớp     Softmax             CCE/ Sparse CCE      Adam/SGD    Accuracy
  Hồi quy    Linear              MSE/MAE              Adam        MSE/MAE/R²
