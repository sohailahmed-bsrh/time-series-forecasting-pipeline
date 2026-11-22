# Time-Series Forecasting Pipeline - Classical, Prophet & Deep Learning

<p align="center">
  <a href="https://sohail.devsil.com"><strong>Portfolio</strong></a> | 
  <a href="https://github.com/sohailahmed-bsrh"><strong>GitHub Profile</strong></a> | 
  <a href="https://github.com/sohailahmed-bsrh/time-series-forecasting-pipeline"><strong>Source Repository</strong></a>
</p>

---

## Executive Summary & Problem Statement

Accurate temporal forecasting is fundamental to inventory planning, financial risk management, and energy grid load balancing. However, real-world temporal sequences exhibit complex dynamics: non-stationarity, shifting multi-period seasonalities, structural trend breaks, and stochastic noise. Relying on a single forecasting technique frequently leads to catastrophic projection errors.

This repository implements a rigorous comparative time-series forecasting framework. It benchmarks three foundational modeling paradigms: **Classical Econometric Models (ARIMA / SARIMAX)**, **Decomposable Additive Models (Facebook Prophet)**, and **Recurrent Deep Learning Architectures (LSTM / GRU)**, utilizing strict rolling-window backtesting.

<div align="center">
  <img src="https://raw.githubusercontent.com/sohailahmed-bsrh/myportfolio/main/assets/images/thumbnail/time-series-forecasting.jpeg" width="650" alt="Time-Series Forecasting Pipeline"/>
  <p><em>Multi-horizon forecasting benchmark across statistical, decomposable, and recurrent architectures.</em></p>
</div>

---

## Real-World Industry Applications

- **Supply Chain Demand Planning**: Projects retail product stock requirements to minimize stockouts and holding costs.
- **Energy Load Management**: Forecasts electrical grid consumption patterns across daily, weekly, and seasonal cycles.
- **Financial Market Volatility**: Models equity trends and risk metrics using moving average and autoregressive signals.
- **Server Capacity & Cloud Scaling**: Forecasts incoming API request traffic to automate cloud infrastructure scaling.

---

## Technical Architecture & Engineering Walkthrough

```
                      [Raw Temporal Sequence Data]
                                   │
                                   ▼
          [Stationarity Testing & Decomposition (ADF / KPSS)]
         (Trend, Seasonal, Residual Decomposition via STL)
                                   │
         ┌─────────────────────────┼─────────────────────────┐
         ▼                         ▼                         ▼
   [ARIMA / SARIMAX]      [Facebook Prophet]         [Recurrent LSTM / GRU]
(Autoregressive Orders) (Fourier Additive Terms)   (Sequential Tensor Sliding Window)
         │                         │                         │
         └─────────────────────────┼─────────────────────────┘
                                   │
                                   ▼
             [Rolling-Window Cross-Validation & Backtesting]
                                   │
                                   ▼
            [Comparative Evaluation Metrics (RMSE, MAE, MAPE)]
```

### Step 1: Temporal EDA & Stationarity Diagnostics
Executes Augmented Dickey-Fuller (ADF) and Kwiatkowski-Phillips-Schmidt-Shin (KPSS) statistical hypothesis tests to determine integration order. Applies first-order and seasonal differencing to achieve mean-variance stationarity.

### Step 2: Classical Statistical Modeling (SARIMAX)
Analyzes Autocorrelation Function (ACF) and Partial Autocorrelation Function (PACF) correlograms to determine optimal autoregressive $(p)$, integrated $(d)$, and moving average $(q)$ hyperparameters alongside seasonal $(P, D, Q)_s$ orders.

### Step 3: Decomposable Modeling with Facebook Prophet
Models non-linear trends with changepoint detection, yearly/weekly/daily seasonal Fourier series, and external holiday effects.

### Step 4: Deep Learning Sequential Modeling (LSTM)
Formats sequential data into three-dimensional sliding window tensors `(samples, time_steps, features)`. Trains stacked Long Short-Term Memory (LSTM) recurrent networks with Dropout regularization to prevent overfitting.

### Step 5: Rolling-Horizon Validation & Performance Benchmarking
Evaluates out-of-sample forecast accuracy using Root Mean Squared Error (RMSE), Mean Absolute Error (MAE), and Mean Absolute Percentage Error (MAPE).

---

## Technology Stack & Implementation Specifications

| Component | Technology | Version | Architectural Function |
| :--- | :--- | :--- | :--- |
| **Statistical Analysis** | Statsmodels | 0.14+ | ARIMA, SARIMAX, ACF/PACF analysis, ADF test |
| **Decomposition** | Facebook Prophet | 1.1+ | Additive trend and seasonal Fourier decomposition |
| **Deep Learning** | TensorFlow / Keras | 2.15+ | Recurrent LSTM / GRU neural network architectures |
| **Data Manipulation** | Pandas / NumPy | 2.x | Datetime index manipulation and rolling calculations |
| **Visualization** | Matplotlib / Seaborn | 3.8+ | Time series trajectory and residual diagnostic plotting |

---

## Installation & Execution Guide

```bash
git clone https://github.com/sohailahmed-bsrh/time-series-forecasting-pipeline.git
cd time-series-forecasting-pipeline
python -m venv venv
# Windows: venv\Scriptsctivate | Unix: source venv/bin/activate
pip install -r requirements.txt
jupyter notebook notebooks/time_series_forcasting.ipynb
```

---

## Author & Contact Information

<table width="100%">
  <tr>
    <td width="150" align="center" valign="middle">
      <img src="https://avatars.githubusercontent.com/u/231165170?v=4" width="120" style="border-radius: 50%;" alt="Sohail Ahmed"/>
    </td>
    <td>
      <h3>Sohail Ahmed</h3>
      <p><strong>Senior Software Engineer & AI Systems Architect</strong></p>
      <p>Specializing in Full-Stack AI Application Development, Computer Vision, Deep Learning Pipelines, and Scalable Automation Architectures.</p>
      <p>
        <a href="https://sohail.devsil.com"><strong>Portfolio Website</strong></a> | 
        <a href="https://github.com/sohailahmed-bsrh"><strong>GitHub Profile</strong></a> | 
        <a href="https://www.linkedin.com/in/sohail-ahmed-546314316/"><strong>LinkedIn</strong></a> | 
        <a href="mailto:se906403@gmail.com"><strong>Email Contact</strong></a>
      </p>
    </td>
  </tr>
</table>
