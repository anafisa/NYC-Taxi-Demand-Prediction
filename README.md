# NYC-Taxi-Demand-Prediction

The primary objective of this project is to build a Real-Time Taxi Demand Prediction Model for every district and zone of NYC.

<img width="602" alt="Снимок экрана 2021-12-29 в 14 54 14" src="https://user-images.githubusercontent.com/30799388/147659748-da22f728-3dfe-4ace-9c50-22fe6af041c0.png">


Data: [nyc.gov](https://www1.nyc.gov/site/tlc/about/tlc-trip-record-data.page). The yellow taxi trip records include fields capturing pick-up and drop-off dates/times, pick-up and drop-off locations, trip distances, itemized fares, rate types, payment types, and driver-reported passenger counts. 

The data used in the attached datasets were collected and provided to the NYC Taxi and Limousine Commission (TLC) by technology providers authorized under the Taxicab & Livery Passenger Enhancement Programs (TPEP/LPEP). The whole dataset consists of approximately 30 million observations. 


__Project Structure:__
1. [Data exploration and processing](https://github.com/anafisa/NYC-Taxi-Demand-Prediction/blob/main/01_data_processing.ipynb)
2. [Geo data visualization](https://github.com/anafisa/NYC-Taxi-Demand-Prediction/blob/main/02_geodata_processing.ipynb)
3. [Complex seasonal forecasting](https://github.com/anafisa/NYC-Taxi-Demand-Prediction/blob/main/03_complex_seasonal_forecasting.ipynb)
4. [Model evaluation](https://github.com/anafisa/NYC-Taxi-Demand-Prediction/blob/main/04_all_regions_forecasting.ipynb)
5. [Model implementation](https://github.com/anafisa/NYC-Taxi-Demand-Prediction/blob/main/05_regression_for_forecasting.ipynb)
6. [Model enhancement](https://github.com/anafisa/NYC-Taxi-Demand-Prediction/blob/main/06_new_features_forming.ipynb)


The main difficulty of the project is the fact that every district of NYC has its own structure, that's why we need to cluster districts with the same dynamic in groups. Then for each group buid unique model with optimal parameters and forecast the demand.

<img width="800" alt="Снимок экрана 2021-07-09 в 00 34 18" src="https://user-images.githubusercontent.com/30799388/124993803-8b5a8100-e04d-11eb-8c82-87ff549e7203.png">

<img width="800" alt="Снимок экрана 2021-07-09 в 00 34 34" src="https://user-images.githubusercontent.com/30799388/124993832-957c7f80-e04d-11eb-9e43-331123466657.png">


We should remember that the time series have complex seasonability 24 and 168 lags, so we need extra features to model seasonality correctly. In this case we may use fourier series or dummy variables.

As for the model, it can be a linear regression or SARIMAX with exog features. The results of models are [here](https://github.com/anafisa/NYC-Taxi-Demand-Prediction/blob/main/03_complex_seasonal_forecasting.ipynb).

<img width="800" alt="Снимок экрана 2021-07-09 в 00 39 15" src="https://user-images.githubusercontent.com/30799388/124994202-29e6e200-e04e-11eb-8ed8-502e0187ac80.png">

As we work with geo data, we need visualize forecasts on the map. It can be static or dynamic visualization.

Static visualization of NYC districts:

<img width="800" alt="Снимок экрана 2021-07-08 в 22 18 37" src="https://user-images.githubusercontent.com/30799388/124978472-80e2bc00-e03a-11eb-8f98-28df1d1e6d86.png">

<img width="800" alt="Снимок экрана 2021-07-08 в 22 18 07" src="https://user-images.githubusercontent.com/30799388/124978827-efc01500-e03a-11eb-9de9-a940379ccfe9.png">


Dynamic visualization of forecasts in every NYC district in selected date and time:

![sss](https://user-images.githubusercontent.com/30799388/124981964-dcaf4400-e03e-11eb-858c-cbe145341cf8.gif)
