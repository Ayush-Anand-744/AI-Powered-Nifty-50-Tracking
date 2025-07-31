# **AI for Banking and Finance — Nifty 50 Index Tracking Using Machine Learning and Deep Learning**

---

## **Objective**
The principal aim of this project is to **Replicate The Performance of the Nifty 50 Index** by leveraging both machine learning and deep learning models. The focus lies in "Minimizing tracking error" between the benchmark index and a model-generated portfolio through:
- **Machine Learning Techniques:** Ridge Regression, Lasso, and ElasticNet.
- **Deep Learning Methodologies:** Autoencoder Neural Network.

---

## **Introduction**
**Index Tracking** has emerged as a fundamental investment strategy among passive investors and institutional portfolio managers. It involves constructing a portfolio that closely follows a reference index—in this case, the Nifty 50, which represents a benchmark of India’s top 50 blue-chip companies. The critical performance metric in this context is **Tracking Error**, which measures the divergence between the index returns and the model-driven portfolio returns.

This project explores the potential of **Artificial Intelligence (AI) and Machine Learning (ML)** in financial modeling by designing a replication portfolio that mimics the Nifty 50 index. The models developed include regularized regression techniques **(Ridge, Lasso, and ElasticNet)** and a **Deep learning-based Autoencoder** to handle non-linearities and feature compression.

Using the **yfinance API**, daily historical stock prices were fetched and transformed into log returns to ensure stationarity and suitability for predictive modeling.

---

## **Tools and Technologies:**
- **Programming Language: Python 3**

## **Libraries and Frameworks:**
- **yfinance – for financial data extraction**
- **pandas, numpy – for data handling**
- **scikit-learn – for ML modeling**
- **matplotlib, seaborn – for visualization**
- **TensorFlow, Keras – for deep learning implementation**

## **Dataset Overview**
- **Source: Yahoo Finance via yfinance**
- **Index: Nifty 50 (^NSEI)**
- **Constituents: Daily price data of all 50 component stocks**
- **Time Period: 1st January 2018 to 1st February 2025**

---

## **Methodology**
**1. Data Acquisition**
Historical daily closing prices for the Nifty 50 index and its constituent stocks were collected using yfinance.

**2. Feature Engineering**
Logarithmic returns were calculated for each asset to ensure mean reversion and stationarity. The feature matrix consisted of individual stock returns, while the target variable was the index return.

**3. Data Splitting**
Training Period: 2018–2021

Testing Period: 2022–2025

**4. Modeling Techniques**
Ridge, Lasso, ElasticNet Regression: Implemented using time-series aware cross-validation to identify optimal regularization hyperparameters.

- **Autoencoder Network:** 
Trained to reduce dimensionality of input returns while retaining core information, and followed by regression on encoded features.

**5. Evaluation Metrics**
Tracking Error (TE): Root mean square deviation between predicted and actual index returns.

- **R² Score:** 
Proportion of index variance captured by the model.

- **Mean Squared Error (MSE):** 
Average squared difference between predicted and actual values.

**Results:**
Ridge Regression achieved the lowest tracking error, making it the most accurate model in mimicking index behavior.

- **Lasso and ElasticNet** also performed well, although slightly less accurate due to their aggressive regularization effects.

- **The Autoencoder-based** approach efficiently compressed stock return signals, leading to competent performance with nonlinear modeling advantages.

- Rolling tracking error plots and cumulative return curves confirmed the reliability of the models across time.

---

**Conclusion**
This study underscores the viability of AI-based financial modeling for replicating benchmark indices like the Nifty 50. Through the application of regularized regression and deep learning, it is possible to construct passive portfolios that track the index with high precision, offering an effective foundation for ETF design and robo-advisory services.

**Future Work:**
Incorporating dynamic portfolio rebalancing to adapt to market fluctuations.

Exploring advanced architectures like **LSTM networks for sequential financial data**.

Integrating real-world constraints such as **Transaction Costs, Liquidity Filters, and Risk Metrics for Enhanced Robustness.**
