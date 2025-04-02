# Flight Fare Prediction
The purpose of the analysis is to understand various factors influencing flight fares and to develop a predictive model.

## Data Analysis Report

### Dataset Overview
- Number of rows: 10683
- Number of columns: 11
- Target Variable: Price (Flight Fare)
- Features: Airline, Source, Destination, Total_Stops, Duration, Date_of_Journey, Dep_Time, Arrival_Time, Route, Additional_Info.
### Data Preprocessing and feature engineering
- Handling Missing Values: As there were only 2 missing values, we directly dropped them, as they are very less.
- Outlier Treatment: We chose not to handle outliers in the price column because flight fares can naturally vary widely, reflecting legitimate high or low prices. Removing these outliers could distort the model's ability to predict future fares accurately.Outliers were observed in the Price column, with a few extremely high fares, likely corresponding to business-class or premium economic flights.
- Handling Categorical data: In this dataset features Duration, Date_of_Journey, Dep_Time, Arrival_Time are in object, so have formatted them to date and time by splitting and converting Date_of_Journey into Day and Month, Dep_Time, Arrival_Time into Hour and Minutes and Duration into Hour and minutes. And categorical features Airline, Source, Destination, Total_Stops, Additional_Info was encoded to numerical features.
### Exploratory Data Analysis (EDA)
- Airline vs Price: There are slight differences between each companies on this graph, AirAsia seems to have the cheapest flights when Jet Airways, Multiple camers and Air India are more expensive. However it looks like Jet Airways Business Class are a little more expensive than the Jet Airways Economic Class.
- Total_stops vs Price: The majority of flights are 1 stop and followed by 2 stops and non-stop. Non-stop flights tend to be cheaper, prices are highest for 1-stop flights, followed by 2-stop flights, with non-stop flights generally being the most affordable.
- Source vs Price: Flights departing from Bangalore tend to have the highest prices, followed by other cities, while Chennai appears to offer more affordable options. Among the sources, Delhi has the highest frequency, followed by Kolkata and Bangalore.
- Destination vs Price: New Delhi has the highest flight prices, followed by Cochin, while flights to Delhi are more affordable. In terms of destination frequency, Cochin has the most flights, followed by Bangalore and Delhi.

## Performance Report for Flight Price Prediction Models
### Overview of Models Evaluated

#### Linear Regression
Performance Metrics:
- R² Score: 0.6235227041515081
- Adjusted R² Score: 0.6163308657869327
- Mean Absolute Error (MAE): 1924.3512465326605
- Mean Squared Error (MSE): 7222040.889838384
- Root Mean Squared Error (RMSE): 2687.3855119499294

#### Decision Tree Regressor
Performance Metrics:
- R² Score: 0.7724088369351185
- Adjusted R² Score: 0.7677792082394592
- Mean Absolute Error (MAE): 853.5510941151475
- Mean Squared Error (MSE): 4365927.783549324
- Root Mean Squared Error (RMSE): 2089.480266369923

#### Bagging Regressor
Performance Metrics:
- R² Score: 0.8670944853556191
- Adjusted R² Score: 0.868744769874477
- Mean Absolute Error (MAE): 743.6650573613767
- Mean Squared Error (MSE): 2549553.6432906473
- Root Mean Squared Error (RMSE): 1596.7321764437038

#### Gradient Boosting Regressor:
Performance Metrics:
- R² Score: 0.8091062864831604
- Adjusted R² Score: 0.7677792082394592
- Mean Absolute Error (MAE): 1271.7271587588857
- Mean Squared Error (MSE): 3661953.1106771575
- Root Mean Squared Error (RMSE): 1913.6230325425008

#### Random Forest Regressor:
Performance Metrics:
- R² Score: 0.8823998882757239
- Adjusted R² Score: 0.8788413260379788
- Mean Absolute Error (MAE): 717.0869156309751
- Mean Squared Error (MSE): 2322088.557425377
- Root Mean Squared Error (RMSE): 1523.8400695038101

### Model Performance Comparison
#### Best Model: Random Forest Regressor
The Random Forest Regressor exhibited the highest accuracy and lowest error metrics compared to other models. It achieved the highest R² score - 0.8823998882757239, indicating that it explains the most variance in the target variable, and had the lowest MAE - 717.0869156309751, MSE - 2322088.557425377, and RMSE - 1523.8400695038101, suggesting it provides the most reliable predictions.

### Conclusion
Before tuning, the model achieved an R² score of 0.8823. After tuning, the R² score remained at 0.8756, indicating that the model had already reached optimal performance with the initial hyperparameters. Despite hyperparameter tuning, the Random Forest regression model maintained a strong performance with an R² score of 0.8756. The current model appears to be well-tuned with an R² score of 0.8823. The Random Forest Regressor has demonstrated the best performance among the evaluated models and is recommended for use in production to predict future flight prices. Its accuracy and robustness make it well-suited for helping customers plan their journeys and make informed decisions.

### Technologies Used
- Python
- Jupyter Notebook: Interactive environment
- Pandas, Numpy: Data manipulation and analysis
- Scikit-Learn: Machine learning modeling
- Matplotlib, Seaborn: Data visualization
