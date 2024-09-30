
# README: Hybrid Attention-Based EMD-LSTM Model for Financial Time Series Prediction

## Overview

This repository contains two Python notebooks implementing models for financial time series prediction:
1. **model-without-emd.ipynb**: Implements a standard LSTM model with an attention mechanism.
2. **model-with-emd.ipynb**: Implements a hybrid model that integrates Empirical Mode Decomposition (EMD) with an LSTM model and attention mechanism.

These models are based on the hybrid approach described in the paper *"A Hybrid Attention-Based EMD-LSTM Model for Financial Time Series Prediction"*. The approach combines EMD and LSTM with attention mechanisms to improve the accuracy of time series forecasting, particularly in financial data.

## Model Descriptions

### 1. **LSTM with Attention (model-without-emd.ipynb)**
   - **Model Structure**: This model employs a standard Long Short-Term Memory (LSTM) network enhanced with an attention mechanism. The LSTM component captures the sequential dependencies in the data, while the attention mechanism helps the model focus on the most relevant parts of the input sequence.
   - **Architecture**:
     - **LSTM**: A recurrent neural network (RNN) variant, designed to handle long-term dependencies in time series data.
     - **Attention Mechanism**: Enhances the LSTM's ability to focus on important time steps by assigning weights to each hidden state and computing a context vector based on these weights.
   - **Use Case**: Useful for financial time series prediction where capturing the most relevant past data points is crucial.

### 2. **EMD-LSTM with Attention (model-with-emd.ipynb)**
   - **Model Structure**: This hybrid model integrates Empirical Mode Decomposition (EMD) with LSTM and attention mechanisms.
     - **EMD**: Decomposes the time series data into Intrinsic Mode Functions (IMFs), each representing different frequency components of the original data. This preprocessing step allows the model to capture both high and low-frequency patterns.
     - **LSTM**: Processes the decomposed IMFs to learn temporal dependencies.
     - **Attention Mechanism**: Applied to the LSTM outputs to focus on the most significant IMFs and time steps.
   - **Architecture**:
     - **EMD**: Separates the original time series into a set of IMFs.
     - **LSTM + Attention**: Processes each IMF through the LSTM and applies attention to the sequence for enhanced forecasting accuracy.
   - **Use Case**: Particularly effective for financial time series that exhibit both long-term trends and short-term fluctuations.

## Results Summary

Both models have been evaluated based on common time series forecasting metrics, such as:
- **MAE (Mean Absolute Error)**: Measures the average magnitude of the errors.
- **RMSE (Root Mean Square Error)**: Penalizes larger errors more severely than MAE.
- **MAPE (Mean Absolute Percentage Error)**: Expresses errors as a percentage of the true values.

In general, the **EMD-LSTM with Attention** model shows better performance compared to the **LSTM with Attention** model, particularly in capturing complex financial time series patterns. Here’s a summary of key results:
- **LSTM with Attention**: MAE = 39.08, RMSE = 63.56, MAPE = 0.0114.
- **EMD-LSTM with Attention**: MAE = 26.63, RMSE = 39.13, MAPE = 0.00777.

## Data

The models are trained and tested on financial time series data. The dataset is preprocessed and normalized before feeding it into the models. Further details on data preparation and processing steps can be found in the respective notebooks.

