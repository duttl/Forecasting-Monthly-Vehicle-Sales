
# Forecasting-Monthly-Vehicle-Sales

## Preface:

- The project is built for Forecasting the future monthly Vehicle Sales in the United States based on the historic data from 1976 to 2019.
- The project begins with exploring the trends in the data. 
- Based on the findings, ARIMA algorithm has been used for Forecasting.

Data is gathered from : https://fred.stlouisfed.org/


## Packages:
`numpy`, `pandas`, `seaborn`, `statmodels`, `sklearn`, `scipy` `matplotlib`
## Overview

### EDA

![fig1](https://user-images.githubusercontent.com/72896396/221480647-3f115137-ecb5-4e36-87bd-e36a86e86474.png)

![fig2](https://user-images.githubusercontent.com/72896396/221483056-56c3a770-fad0-4ef2-a85b-aea09df91ae9.png)

- Based on the graphs, there is a clear indication of **Seasonality** in the data.
- The average sales in the time period of 43 years has been **~1,240**.
- The data doesn't have any missing value, and has only one atbrite, which the Total Sales in a given month; hence **Feature Engineering** or **Feature Importance** are not necessary for this poject.

### Differencing:

- Seasonal Differencing has been applied to make the data stationary.
- **Dickey Fuller** test is conducted to confirm with the results after one seasonal Differencing and one regular Differencing.

![fig3](https://user-images.githubusercontent.com/72896396/221484805-aab8f3ba-c1aa-41ec-8bdb-3484439a6680.png)

### Model Creation:

- **Autocorrelation** and **Partial Autocorrelation** graphs are used for creating the ARIMA Model. 
- In **PACF**, the spikes at lag 1,2,3 and 4 implies **non-seasonal p** *(AR lags)* value of **4** and the spike at lag 12 implies seasonality, and the **seasonal p = 1**.
- In **ACF** the spike at lag 1 implies **non-seasonal q** *(MA)* value of **1** and a significant spike at 12 implies a **seasonal q** value of **1**.
- The seasonal difference has been applied once , so the **d** value would be **1**.

*p - Auto Regressive Lags, q - Moving Averag Lags, d - Differencing*

![fig4](https://user-images.githubusercontent.com/72896396/221486801-52cab2d1-dbbb-4051-b10b-739833c3c392.png)


### Test Results:

![fig5](https://user-images.githubusercontent.com/72896396/221487010-313c0d56-ec24-4e5a-829b-519c811e384e.png)

- The model performance has been evaluted by calculating the Mean Absolute Percentage Error, which is 4.3%. Hence can infer the model is performing well. 


### Future Prediction

![fig6](https://user-images.githubusercontent.com/72896396/221487968-1abe2934-d62b-4710-916c-9e56794ace15.png)
