#  Stock Price Prediction Using LSTM

This project demonstrates how deep learning—specifically **Long Short-Term Memory (LSTM)** networks—can be used to predict the **closing prices of stocks** using past historical data.  
From exploring the raw stock data to building a sequence-based model and comparing it against traditional indicators, this notebook captures a complete ML workflow for time series forecasting.

---

##  Objective

To build a deep learning model that can:
- Learn from 4 years of historical stock prices
- Predict the **next day’s closing price**
- Compare its performance with simple and exponential moving averages

---

##  Dataset

The dataset used includes:
- Open, High, Low, Close prices
- Date range: **4+ years**
- Frequency: **Daily**

 Stored in: [`stock_data.csv`](./stock_data.csv)

---

##  Exploratory Data Analysis (EDA)

Visualized important patterns and relationships like:

| High & Low Prices | Open & Close Prices |
|-------------------|----------------------|
| ![High Low](./plot%20images/stock%20high%20and%20low%20prices.png) | ![Open Close](./plot%20images/stock%20open%20and%20close%20prices.png) |

---

##  Preprocessing

1. Scaled features using `StandardScaler`
2. Used a sliding window approach (`n_steps = 1`) to create sequences for LSTM
3. Splitted the dataset into train and test sets (80:20)

---

##  Model: Long Short-Term Memory (LSTM)

Initially, a basic 1-layer LSTM model was trained:

| Training Loss Plot (Initial Model) |
|------------------------------------|
| ![Initial Loss](./plot%20images/initial%20mode%20training%20loss%20plot.png) |

| Predictions vs Actual (Initial) |
|----------------------------------|
| ![Initial Pred](./plot%20images/initial%20model%20LSTM%20values%20vs%20true%20values.png) |

---

###  Second Experiment: Added Another LSTM Layer

| Training Loss (2nd Model) | Predictions vs Actual |
|---------------------------|------------------------|
| ![Loss 2](./plot%20images/2nd%20model%20adding%20another%20layer%20training%20loss%20plot.png) | ![Pred 2](./plot%20images/2nd%20model%20LSTM%20values%20vs%20true.png) |

---

###  Final Experiment: Deeper LSTM + Tuning

| Training Loss (3rd Model) | Predictions vs Actual |
|---------------------------|------------------------|
| ![Loss 3](./plot%20images/3rd%20model%20training%20loss%20plot.png) | ![Pred 3](./plot%20images/3rd%20model%20LSTM%20vs%20true%20values.png) |

>  The predictions aligned closely with true values and captured overall trends well.

---

##  Baseline Comparison

To validate the model's performance, it was compared with:

| Simple Moving Average | Exponential Moving Average |
|------------------------|----------------------------|
| ![SMA](./plot%20images/LSTM%20vs%20simple%20%20moving%20average.png) | ![EMA](./plot%20images/LSTM%20vs%20exponential%20moving%20average.png) |

LSTM clearly outperformed both moving averages in capturing momentum and direction changes.

---

##  Evaluation Metrics

- **Loss Function**: Mean Squared Error (MSE)
- **Performance Observations**:
  - Fast convergence within 20 epochs
  - Captures both upward/downward trends well
  - Slight lag during volatile movements

---

##  Files in this Repo

| File | Description |
|------|-------------|
| `stock_price_prediction.ipynb` | Complete notebook |
| `stock_data.csv` | Raw dataset |
| `plot images/` | All charts and visualizations |
| `README.md` | This file |

---

##  Conclusion

This project demonstrates the potential of LSTMs in time series forecasting. Although it uses only the previous day's data (1-step window), it performs reasonably well. Future improvements can include:

- Using larger time windows (e.g., 10 or 30 days)
- Including technical indicators (RSI, MACD)
- Hyperparameter tuning or using GRU / Transformer models

---

##  Author

GitHub: [@clawnic](https://github.com/clawnic)

---

##  Try It Yourself

Want to test on a different stock?  
Simply replace the CSV and rerun the notebook in [Google Colab](https://colab.research.google.com/github/clawnic/stock-prediction-lstm/blob/main/stock_price_prediction.ipynb).
