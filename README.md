 # Time Series Analysis of Stock Data
 
 This project conducts a time series analysis on stock price data for the ticker 'AABA'. The primary goal is to analyze the properties of the stock's 'High' price, test for stationarity, and apply transformations to make the series stationary, which is a prerequisite for many time series forecasting models.
 
 ## Dataset
 
 The analysis uses the `stock_data.csv` dataset, which contains daily stock price information. The key columns include:
 - **Date**: The trading date.
 - **Open**, **High**, **Low**, **Close**: Daily stock prices.
 - **Volume**: The number of shares traded.
 - **Name**: The stock ticker ('AABA').
 
 ## Analysis and Visualizations
 
 The analysis follows several key steps, from initial data exploration to stationarity testing and transformation.
 
 <img width="1006" height="556" alt="image" src="https://github.com/user-attachments/assets/34293747-2a60-41c3-9715-be0480813b78" />
 <img width="1006" height="556" alt="image" src="https://github.com/user-attachments/assets/2c59b199-ef37-4de7-9d3d-645b013ffc37" />
 <img width="599" height="463" alt="image" src="https://github.com/user-attachments/assets/1ba7b5f8-80ca-463f-934a-46b600095abc" />
 <img width="995" height="532" alt="image" src="https://github.com/user-attachments/assets/40e80cb5-1330-4691-825b-270af4287497" />


 <img width="1006" height="556" alt="image" src="https://github.com/user-attachments/assets/f9076cd5-350d-43d9-9596-e274c8a52d29" />

 
 
 ### 1. Data Exploration and Resampling
 
 An initial plot of the 'High' stock price over time reveals a clear trend, suggesting that the time series is not stationary.
 
 !High Stock Price Over Time
 
 To get a clearer view of the long-term trend, the data was resampled to a monthly frequency by averaging the daily values.
 
 !Monthly Resampled High Price
 
 ### 2. Autocorrelation and Stationarity Testing
 
 The Autocorrelation Function (ACF) plot was generated to check for seasonality and non-stationarity. The slow decay in the ACF plot is a strong indicator of a non-stationary series.
 
 !ACF Plot
 
 To formally test for stationarity, the **Augmented Dickey-Fuller (ADF)** test was performed on the original 'High' price series.
 
 **ADF Test on Original Data:**
 - **ADF Statistic:** `0.767`
 - **p-value:** `0.991`
 
 With a p-value significantly greater than 0.05, we fail to reject the null hypothesis, confirming that the series is non-stationary.
 
 ### 3. Differencing for Stationarity
 
 To address the non-stationarity, first-order differencing was applied to the 'High' price series. The plot below contrasts the original data with the transformed, differenced data, which now appears to hover around a mean of zero.
 
 !Original vs Differenced Data
 
 ### 4. Verifying Stationarity
 
 The ADF test was performed again on the differenced data to confirm that the transformation was successful.
 
 **ADF Test on Differenced Data:**
 - **ADF Statistic:** `-12.148`
 - **p-value:** `1.59e-22`
 
 The extremely low p-value allows us to confidently reject the null hypothesis, indicating that the differenced series is now stationary and suitable for time series modeling.
 
 ## Dependencies
 
 This project requires the following Python libraries:
 - `pandas`
 - `numpy`
 - `seaborn`
 - `matplotlib`
 - `statsmodels`
 
