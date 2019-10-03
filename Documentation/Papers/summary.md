## <p align="center">**SUMMARY**</p>
### <u>*Document 1*</u>: " A Novel Approach for Anomaly Detection in Power Consumption Data"
<pre>
<b>*)Problematic</b>: Anomaly Detection has been widely used within diverse research areas. In this document, especially, it used to detect anomalies in power consumption data in household in order to improve energy efficiency. Several models are used and each one had its functionality.
<b>*)Data:</b> the data used is a time series data which is collected from Pecan Street's dataport that works on smart meters to provide real data for researchers.The total database contains data from 67 devices in 820 households.In this document,they use the total usage of the user of one year period with 1 hour resolution.
"We randomly chose one user (ID 59) during the period January 2017 to December 2017"
<b>*)Target Function:</b>The input is the power consumption of users of the last 24 hours and the output is a predection of power consumption of the next hour. 
"The predicted value using LSTM is going to be used to form a vector representing the power consumption of the last 24 hours"(page 3/8)
"We begin by building a LSTM with three hidden layers and we trained it to predict the power consumption of the next hour using the data of the last 24 hours using Adam optimizer"(page 3/8)
<b>*)Models:</b>  
This research proposes a combination of recurrent neural networks and clustering methods in order to detect and predict anomalies in power consumption data . they present a hybrid model combining LSTM and K-means algorithm in order to detect outliers in time series data. Auto-Encoders detects abnormal days.      
Auto Encoders: identify normal days.
K-means: was used to categorize daily consumption patterns in a week.The analysis of K-means algorithm results suggested that electricity consumption patterns differ each day except on weekends.
LSTM: is used to predict the power consumption of the next hour.


</pre>

### <u>*Document 2*</u>: " Anomaly detection in electricity consumption data of buildings using predictive models"
<pre>
<b>*)Problematic</b>: This document showed that is not an easy task to detect anomalies automatically in big buildings such as govermant institutions and universities beacause they don't have detailed information of about the consumption of the individual parts.So the energy consumption data that will be analyzed is the total electricity consumption of the building in a constant interval.A seperate model for each bulding (5 buildings) because anomalies can occur in different time scales.Then they compare anomalies between buildings to get more insight in the nature of them.
<b>*)Data:</b> time series data collected from Unive of Amesterdam and Hogeschool von Amesterdam. There are 2 kinds of data that are used: Building Data and Local weather data. 
"Another way to get deeper insight in the anomalies is to look at a smaller time scale. By analyzing consumption on a 15 minute frequency, the structure of the anomaly could provide extra information"
"every building must have enough data to train the model and the training can take a long time"
<b>*)Target Function:</b> The input is the power consumption of n previous values of Electricity consumption and the output is a predection of Electricity consumption  in the time t.
"a model has been made for each building that accurately predicts the electricity consumption. This model can be now be used the find anomalies in the data. The idea is to let the model predict the consumption on time t"
"Forecasting tries to predict the value at time t using the n previous observations, as shown in equation y(t)= s(yt-1; yt-2;...; yt-n)"
-Bulding Data: consists of the electricity consumption at a constant time interval. It’s an hourly frequency data(24 mes/day) because anomalies less then 1 hour duration have a little influence in the total electricity consumption and add noise to the data which makes predection more complicated.
-Local weather Data: The data is measured on an hourly granularity (which matches the building data) and the most important variables are temperature(Celcuis), wind speed(m/s), global radiation(J/cm²).
-Time features: * Hour 0-23
                      * weekday 1-5
                      *coshour cos(hour*2pi/24)
                      *sinhour sin(hour*2pi/24)
                      *cosweekday cos(weekday*2pi/5)
                      *sinweekday sin(weekday*2pi/5)

During holidays and weekends the energy consumption is different from regular usage. Because this can cause problems for the machine learning algorithms, the data is split in 3 parts:    *Weekdays
                     *Weekends
                     *Holidays

                                   | Training data set      | Test data set          |
                                   | -----------------------| ---------------------- |
                                   | 01/01/2008->31/12/2012 | 01/01/2014->28/04/2014 |
                                   | 24384                  | 1826                   |
<b>*)Models:</b>                   
     k Nearest Neighbors
     ANN
     SVM

"Jasper [16] tried to use unsupervised learning on a detailed dataset, which did not yield good results."
"Several papers suggest that artificial neural networks are the best method for prediciting such data"
"The error is measured by using a large train set (2008-2013) and a smaller test set (2014). It is clear the neural network is the best model."

                                   | Model     | MAPE   | MASE  |
                                   | ----------| -------|------ |
                                   | KNN       |   69%  |  1.83 |       
                                   | ANN       |   83%  |  0.91 |
                                   | SVM       |   69%  |  1.14 |

</pre>

### <u>*Document 3*</u>: " A New Anomaly Detection System for School Electricity Consumption Data 
<pre>
<b>*)Problematic</b>: In this paper, they focus on remote facilities management that identifies anomalous events in buildings by detecting anomalies in building electricity consumption data.They investigated five models within electricity consumption data from different schools to detect anomalies in the data. Furthermore, they proposed a hybrid model that combines polynomial regression and Gaussian distribution, which detects anomalies in the data with 0 false negative and an average precision higher than 91%.
<b>*)Data:</b> *time series data.
        *Collected from 40 different schools.
        *half hourly frequnce.Power(kwh)
"Furthermore, since the model is trained by one year of data, long-term effects of the data have not been explored comprehensively. Therefore, optimizing the model with a larger dataset (e.g., data of 10 years), for example, investigating season and holiday effect on the model, is another research emphasis."
<b>*)Target Function:</b>The input is a previous values of Electricity consumption and the output is a predicted value of EC.   
"For predicting one week’s electricity consumption, an ARMA(45, 45) model is trained by its previous three week’s data."(page 5/18)
<b>*)Models:</b>     
in order to detect anomalies in weekly data with a low false negative and a high precision, a hybrid model that combines polynomial regression and Gaussian distribution
is proposed.               
   AR
   ARMA
   POLYNOMIAL REGRESSION
   Gaussian Kernel Distribution
   Gaussian Distribution
</pre>                                     

### <u>*Document 4*</u>: " Real-time detection of anomalous power consumption 
<pre>
<b>*)Problematic</b>: In this paper, they tried an hybrid model neural net ARIMA to predict data consumption in buildings in order to detect anomalies there.
<b>*)Data:</b> collected from a smart meter and registred in a database.
        per minute(kwh) 
"The data used to build the forecasting model for each of the considered weeks included electricity consumption for each minute of the 8 weeks and 4 weeks previous to the first day of the week whose consumption are to be predicted"
<b>*)Target Function:</b>The input is a previous values of Electricity consumption and the output is a predicted value of EC.   
"For predicting one week’s electricity consumption, an ARMA(45, 45) model is trained by its previous three week’s data."(page 5/18)
Predictions of electricity consumption during the following week were based on 8 or 4weeks of rolling training data. For example,data for weeks1–8 were used to predict electricity consumption for week 9 while datafor weeks 2–9 were used to predict consumption for week 10.The same procedure was used for 4 weeks of rolling data, i.e., data for weeks 5–8 were used to predict consumption for 9,and so on."
<b>*)Models:</b>      
Daily real-time consumption is predicted by using a hybrid neural net ARIMA(auto-regressive integrated moving average) model of daily consumption.               
  K-means algorithm
  Artificial neural networks
  Auto-regressive integrated moving average
  Neural network auto regressive
</pre>
## Conclusion:    

### After examining The 4 papers, I can say that 3 of them are making the same thing with diffrent tools and models.They all try to predict Energy consumption from previous Data (Regression: the input is a previous data of energy consumption and the output is a predicted value of energy.).Then They categorize this values into to categories which are anomalies days and normal days with different methods (Classification).
