# HAVELSAN-INTERNSHIP

In this project, which I worked on during my internship at Havelsan, I examine a time series data set created with the second data of hundreds of sensors on ships. The dataset includes gas emission data for three different gases, apart from the sensors. These are: NOx, SOx and Smoke Content. During the voyage (RunId), the mentioned gases are emitted on ships that go on 89 voyage.

### About Data

There are different initial conditions throughout cruises:

-Load Type: FAL, FAU

-Sea Temperture: SW20, SW25, SW28

-Wind Speed: WC0, WC3, WC6

The 18 initial conditions create different scenarios for each cruise and affect gas emissions differently. Considering the data density, since the majority of the data were sea temperature SW20 and wind speed WC0, these two values were taken as constant and the results of the Load Type variable were examined.

Additionally, it was determined that 3 different errors occurred during the journey. Due to these error situations, separate regression models were studied for 1 normal case and 3 fault cases (4 fault classes in total) for gas emission prediction. These situations are defined as follows:

-M0000 : Normal Status

-M2503, M2506, M2508: Error Conditions

## Regression

The first aim of the project is to create regression models to predict gas emissions from various gases. In the project, model improvements were made mostly for 'Smoke Content' gas.

To solve the regression problem, GPR (Gaussian Process Regression) was used in the project. Various kernel types were tried and Grid Search was used for the most optimal hyperparameter selection.


## Classification

The second phase of the project is to create a classification model for the 4 error classes mentioned above. Since the sensor data is time series, the LSTM approach was focused on. Windowing was done for each run and Stratified K-Fold was worked on to balance the data distribution in the classes.

