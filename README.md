
# Bitcoin Price Prediction Using Deep Learning Models 📈💻

This project implements and compares three deep learning models — **LSTM**, **GRU**, and **CNN-LSTM** — for predicting daily Bitcoin closing prices using historical data. The goal is to determine which architecture is most effective in capturing Bitcoin's highly volatile and nonlinear price behavior.

---

## 📊 Dataset

- **Source**: Historical Bitcoin daily closing prices (2014–2024) from Kaggle.
- **Features Used**: Only the `Close` price is used.
- **Preprocessing**:
  - Min-Max normalization to [0,1]
  - Sliding window of 15 days to predict the next day
  - 80% training and 20% testing split

---

## 🧠 Models

### 1. LSTM (Long Short-Term Memory)
- Two stacked LSTM layers (50 units each)
- Dense output layer
- Dropout: 0.2
- Optimizer: Adam (lr = 0.001)
- Loss: Mean Squared Error

### 2. GRU (Gated Recurrent Unit)
- Two GRU layers (50 units each)
- Dense output layer
- Dropout: 0.2
- Optimizer: Adam (lr = 0.001)
- Loss: Mean Squared Error

### 3. CNN-LSTM (Hybrid Model)
- 1D Convolutional layer (64 filters, kernel size = 3)
- Followed by LSTM layer (50 units)
- Dense output layer
- Optimizer: Adam (lr = 0.001)
- Loss: Mean Squared Error

---

## 📈 Evaluation Metrics

- **RMSE**: Root Mean Squared Error
- **MAPE**: Mean Absolute Percentage Error
- **Loss Curves**: Tracked during training

---

## ✅ Results

| Model       | Train RMSE | Test RMSE | Train Accuracy (MAPE) | Test Accuracy (MAPE) |
|-------------|------------|-----------|------------------------|-----------------------|
| LSTM        | 732.17     | 2893.88   | 85.15%                 | 92.18%                |
| **GRU**     | **446.56** | **2168.36** | **91.69%**              | **97.28%**             |
| CNN-LSTM    | 761.96     | 3272.46   | 87.45%                 | 93.53%                |

---

## 🏆 Best Model

Based on the results above, the **GRU model** achieved:
- The **lowest RMSE** on both train and test sets
- The **highest accuracy (97.28%)** on test data
- The most **stable and realistic future predictions**

Thus, GRU is the **recommended model** for Bitcoin price forecasting using deep learning.

---

## 📉 Known Issues

- **NaN Validation Loss**: Caused by inconsistent normalization during validation split. Ensure validation/test data uses the same scaler fitted on training data.

---

## 🚀 Future Work

- Incorporate external features: trading volume, news sentiment, macroeconomic indices
- Use Transformer-based architectures (e.g., BERT, TST)
- Try ensemble or attention-based models

---

## 📝 Citation

If you use this repository or its findings in your work, please cite:

> Prince Goti (2025). *Bitcoin Price Prediction Using Deep Learning Models: A Comprehensive Comparative Study*. PDEU School of Technology.

---

