---
title: Personal CV
layout: default
nav_order: 1
---


# Edoardo Camerinelli
BSc in Economics and Quantitative Methods at USI Università della Svizzera Italiana

### Summary
Hungry and passionate student highly interested in algorithmic 
trading and statistical arbitrage systems and strategies.

### Education
**USI Università della Svizzera italiana**

[Bachelor's degree, Economics and Quantitative Methods  · (2023 - 2026)](https://www.desk.usi.ch/it/piano-degli-studi-bachelor-in-scienze-economiche)

### Honors-Awards
Bachelor's Annual Scolarship at USI

### Languages
- English (Full Professional)
- Spanish (Elementary)
- Italian (Native)

### Certifications
**IELTS C1** Academic English

## Some of my projects on GitHub:

[Backtesting a mean reversion trading strategy on 100 thousand simulated price paths with Numba:](https://github.com/edoardoCame/PythonMiniTutorials/blob/a3920eb9b472f933a2b5bc6d721907deb9482c57/time%20series%20models/to%20practice/ts%20simulation%20ARIMA.ipynb)

This Jupyter notebook simulates time series data using a fitted ARIMA model. It imports necessary libraries, downloads EURGBP exchange rate data from a 
OneDrive link, and preprocesses it. Using sktime's AutoARIMA, the notebook fits an ARIMA model to the data and extracts the model's parameters. It then defines functions to simulate time series data based on the fitted ARIMA model, using the numba library for performance optimization. The notebook further extends simulations to thousands of time series and performs Monte Carlo optimization to backtest a Bollinger Bands strategy across these simulations, reporting satisfying results in terms of profits 

[Trading strategy live execution via asynchronous threading via interactive brokers:](https://github.com/edoardoCame/PythonMiniTutorials/blob/a3920eb9b472f933a2b5bc6d721907deb9482c57/trading%20strategies/MyOwnBacktester/IB%20api%20connection.ipynb)
This notebook demonstrates an asynchronous connection to the Interactive Brokers (IB) API for real-time trading. It includes the following key components: 

1. Asynchronous Connection Setup: The notebook sets up an asynchronous 
connection to the IB API, enabling real-time data streaming and trading operations. 
2. Data Handling and Processing: It processes incoming market data, including 
handling bar updates, to calculate trading signals and positions. 
3. Error Handling: The notebook includes error handling mechanisms for scenarios 
such as division by zero during position size calculations. 
4. Real-Time Updates: The code continuously prints out the current market position 
and price updates, ensuring the user is informed of the latest market conditions. 