# Currency_Exchange_Rate
Analyzing and predicting US Dollar, Japanese Yen and Euro exchange rate values 

## Motivation 
Currency Exchange rates are one of the most dynamic and volatile financial indexes that drives a country's Balance of Payments. Effective analysis and its accurate prediction can help government in taking proactive steps towards reducing current account deficit and thereby maintain financial stability.

## Objective
- This project aims at analysing floating exchange rates of US Dollar (USD), Japanese Yen (JPY) and Euro (EUR)
- Create a predictive model which captures the movement and predict the exchange rate value

## Key Observations
- We observe that closing value shares a linear relationship with opening, high and low value for EURJPY, EURUSD as well as USDJPY
- This hints at using Linear Regression for our model
![image](https://user-images.githubusercontent.com/86396532/126045886-1758bd91-0dc1-4066-b2d5-132431451768.png)


![image](https://user-images.githubusercontent.com/86396532/126043893-3e7f27dc-83a7-4799-8080-4d48b18b97e8.png) ![image](https://user-images.githubusercontent.com/86396532/126043897-26ddf0a8-f68b-4503-a1b1-d6ef9e38505e.png) ![image](https://user-images.githubusercontent.com/86396532/126043909-9d7b4514-6176-4512-9dc9-77aaa3db4893.png)

## Analysis of Closing Value
- **Mean**
  - EURJPY = 130.885623
  - EURUSD = 1.183646
  - USDJPY = 110.577013

- **Peaks and Troughs**
  - Time at which Closing value peaked
    - EURJPY = 07/05/2021 00:30
    - EURUSD = 07/06/2021 06:00
    - USDJPY = 07/05/2021 00:15
  - Time at which Closing value reached lowest
    - EURJPY = 07/08/2021 08:30
    - EURUSD = 07/07/2021 14:15
    - USDJPY = 07/08/2021 14:30

- **Most frequent Closing Value**
  - EURJPY = 131.635
  - USDJPY = 110.7734
  - EURUSD = 1.184605
![image](https://user-images.githubusercontent.com/86396532/126044046-0f4fed9a-24c9-4480-8475-9c85853c8e20.png)

- **Correlation amongst closing values**
  - As evident from the heatmap, USDJPY and EURJPY share the highest correlation factor (0.89)
  - Correlation of EURJPY and EURUSD is also strong (0.66)
  - Weak correlation exists between USDJPY and EURUSD (0.24)
  - Reason
    - This trend might be due to USD and EUR being hard currency as compared to JPY
    - So when institutions would be selling JPY, they would buy either EUR or USD, hence both EURJPY and USDJPY increases

![image](https://user-images.githubusercontent.com/86396532/126044087-b88ead84-bce9-40cc-972e-b91bdd50e2e0.png)

- **Trend**
  - We observe that the closing value of USDJPY and EURJPY show a steady rise across the given time frame
  - But EURUSD has shown more of a volatile / unpredictable nature (probably due to competitive market value of Euro and US Dollar)
  - This same pattern can also be observed in Change(%) graph
    - Number of sharp rise/fall - EURUSD > USDJPY > EURJPY

![image](https://user-images.githubusercontent.com/86396532/126044121-95c35d41-5d31-4f01-83e5-eb28e090c56a.png)

![image](https://user-images.githubusercontent.com/86396532/126044188-1d4a9929-be76-4c0f-9422-8aa4c2acb85a.png)

![image](https://user-images.githubusercontent.com/86396532/126044151-3dffabea-6794-4403-91bd-1a63ee75ebac.png)

## Model Creation
- We use Linear Regression in our model since we saw an almost linear relationship between Closing value and other parameters
- Linear Regression increases speed with low computational cost
- Feature Selection
  - We drop features EURJPY_Change(Pips), EURJPY_Change(%) from our model since these won't be available while predicting the closing value
  - EURJPY_Change represents the difference between Opening and closing value
  - The only inputs available would be Opening Value, High and Low
- Train and test dataset
  - Dataset has been split in the ratio of 75:25 (Train:test)
  - Threshold date was used to divide the dataset instead of going with train_test_split
  - This ensures that older data is used to train model whereas testing is done on recent dataset
  - It helps in truly gauging the bias and variance present in our model

## Performance
- EURJPY
  - R_square =  0.956
  - MSE =  0.0003
- EURUSD
  - R_square =  0.994
  - MSE =  0.0003
- USDJPY
  - R_square =  0.9954148713941781
  - MSE =  0.00018560988336948305




