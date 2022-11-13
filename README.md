# COMP2200/COMP6200-S2-2020 Data Science Portfolio @ Macquarie University

## Portfolio projects   
**Student Name:** Chi Thanh Liu   
**StudentID:** 45728046

## Portfolio 1:
In Portfolio 1, I have been required to analyse Cycling Data. Before answering all the requirements, I joined 'Strava' data frame and 'Cheetah' data frame together. There are five requirements in Portfolio 1.
 1. In the first requirement, I cleaned the data by removing all 'False' values in 'device_watts' column in the joined data frame.
 
 
 
 2. In the second requirement, I created histograms to look at the distributions of some key variables: time, distance, average speed, average power, TSS.   
    
    * Time: I used two variables 'Moving_time' and 'Elapsed_time'. The histograms of both these variables are skewed right.
    * Distance: The histogram is skewed right.
    * Average speed: The histogram looks like a normal distribution. Although there are some outliners, these values could not influence too much.
    * Average power: This histogram is the same as the histogram of average speed. Although there are some outliers, it is not important.
    * TSS: The histogram is skewed right, and it also has some outliers.  

3. In the third requirement, I explained the relationships between variables:
    * When moving_time increases, the distance and TSS also increase. It is a positive correlation.
    * The longer distance is, the higher TSS is. It is a positive correlation.
    * The Average Speed increases, the average_hearthrate, the average_watts, and NP would rise. It is a positive correlation.
        * The Average Speed increases, the moving_time would decrease. It is a negative correlation.
    * The Hearth Rate grows, the average_watts and the NP would increase. It is a positive correlation.
        * The Hearth Rate increases, the moving_time would decrease because you run fastly, the moving_time will decrease. It is a negative correlation.
    * The higher average_watts is, the more increased of NP is. It is a positive correlation.
    * The NP rises, the TSS and the distance also increase. It is a positive correlation.
    

        
4. In the fourth requirement, I created scatter plots and histograms of three categories: *Race*, *Workout*, *Ride*.

    * In this fourth requirement, I have chosen the moving_time and distance which belong to each workout_type, and display these data on scatter plot with different categories (Ride, Race, Workout). We can see that the number of Rides is the highest. Race and Workout do not have too much the quantity as same as Ride. However, the moving_timeand distance of three categories has the same tendency. It means that when the moving_time increases, the distance also grows. Although these three categories also have some outliers, these outliers do not impact significantly on the whole result.

    * I also present the moving_time of three categories on three different histograms to see the different distributions of the moving_time for each type. The first histogram displays the moving_time of Race. It is normally distributed. As I said before, even though it has some outliners, it does not influence significantly. The second histogram and third histograms are Ride and Workout categories, respectively. They are not normally distributed. The Ride histogram is skewed right, and the other one is skewed left. While the moving_time of Workout and Race seems to be the same, the moving_time of Ride is different. The highest moving_time of Ride is approximately 250, while the lowest is nearly 0.


5. In the final requirement, I have been asked to join the temperature data frame with the cycling data and find the relationship between *distance*, *Average speed* and *temperature*:
    * The relationship between distance and temperature is positive. However, the value is 0.015; it is tiny. It means that when the distance increases, the temperature also increases.
    * The relationship between Average Speed and the temperature is a negative relationship. The values are -0.063. It means that when the temperature is increased, the average speed will be decreased.
        
## Portfolio 2:
In Portfolio 2, I will work on the training and testing data about the energy of the house, and try to predict whether temperature and humidity impact on energy consumption. Moreover, I also need to reproduce some plots by using the given datasets. To reproduce, I need to combine training and testing data to get the complete dataset. 

### Reproduced Plots:
1. **Line Graphs (Time-series Plots):**
    * In the first line graph, it showed the energy consumption of Appliances in from January to May in 2016. As we can see from the graph, in January, the energy was consumed more than other months. In January, there were days that people used electricity more than 1000Wh while the highest amount of consumed electricity was 900 Wh in other months
    * In the second line graph, I have only selected one week from January to see how the consumed energy in a week of Appliances. As we can see from the graph, the graph shows the amount of consumed electricity in a week from 2016-01-11 to 2016-01-18. The highest amount of consumed electricity was more than 900 Wh.
    

2. **Distribution of Appliances:**
    * The first plot is the histogram of Appliances. As can be seen from the histogram, the data distribution has a long tail. Perhaps, there are some outliers. The common amount of consumed energy was in a range from 0 to 200 Wh, and the highest is probably about 60 Wh.
    * The second one is the boxplot. In the boxplot, the median has a value of 60 Wh. While the lower whisker has a value of 10 Wh, the upper whisker has a value of 170 Wh. There are several outliers in the boxplot.
    
    
3. **Pairsplot:**

    Pairsplot showing the relationships between all the variables with the energy consumption of appliances.
    I displayed pairs plot with three different formats. The diagonal shows the histograms, the upper displays Pearson's correlation coefficient, and the lower is the regression plot. 

    * *The first pairs plot:* As can be seen from the first pairs plot. There is a positive correlation between the energy consumption of appliances and lights (0.20). The second largest is between appliances and T2. There still has a negative correlation between appliances and RH_3.
    * *The second pairs plot:* shows the relationship between the energy consumption of appliances with T4, RH_4, T5, RH_5, T6, RH_6. The largest correlation is that a positive correlation between appliances and T6 is 0.12. There is a negative correlation between Appliances and RH_6 (-0.08).
    * *The third pairs plot:* The third pairs plot demonstrates the relationship between the consumed electricity of appliances with T7, RH_7, T8, RH_8, T9, RH_9. The correlation in this Paris plot is quite low. The largest is 0.04 between Appliances and T8. There are many negative correlations in the third pairs plot.
    * *The last pairs plot:* represents the relationship between the energy consumption of Appliances with T_out, Press, RH_out, Windspeed, Visibility, Tdewpoint, NSM, and T6. There is a positive correlation between Appliances and NSM (0.22). In this pairs plot, we can easily to see that there is no relationship between Appliances and Visibility.
    
    
4. **Heatmap:**

    The heatmap shows the hourly energy consumption of appliances in a week (2016-01-11 - 2016-01-18). As can be clearly seen, there is a strong time component in the energy consumption pattern. The energy consumption starts to rise around 6 in the morning. Then around noon, there are energy load surges. The energy demand also increases around 6 pm. The energy demand starts to decrease from 10 pm. There is no clear pattern regarding the day of the week.


5. **Residual Plot:**
    
    The relationship between the variables and the energy consumption of appliances is not well represented by the linear model since the residuals are not normally distributed around the horizontal axis.
    
### Models Performance:

* After dropping 4 columns which are not essential, I used 35 predictors to predict Appliances. In this case, I used Linear Regression to fit model and tested the model in training data and testing data to calculate RMSE, r2_score, MAE, MAPE. When I tried to test the data based on testing data, r2_score decreased from 0.18 to 0.16. Although r2_score did not decrease significantly, it was quite small to evaluate this model fit the data.
    
### Feature selection using RFECV:

* In this case, to test how many variables are optimal to minimize the RMSE the recursive feature elimination and cross-validated (RFECV) is used to select the optimal inputs. Follow to the textbook, and I also trained model with 10 cross Fold Cross-Validation. In the textbook, they used the random forest regression method to train the model. However, in my portfolio, I used linear regression method. Therefore, my result could be different. I found that there is 22 optimal number of features instead of 34 optimal number of features in the textbook.

### Answer some questions from Portfolio 2 tasks pdf file:

* In my opinion, the weather data obtained from a nearby weather station representative is enough to improve the appliance's energy consumption prediction.
* The temperature and humidity measurements from a wireless network can help in the energy prediction. From the pairs plots, there are relationships between Appliances and temperature and humidity. Moreover, temperature and humidity are parameters are the most important in energy prediction after implementing feature selection.
* From all the data used in prediction models, parameters are the most important in energy prediction such as 'lights', 'T1', 'RH_1', 'T2', 'RH_2', 'T3', 'RH_3', 'T6', 'T8', 'RH_8','T9', 'T_out', 'Windspeed', 'WeekStatus_Weekday', 'WeekStatus_Weekend','Day_of_week_Friday', 'Day_of_week_Monday', 'Day_of_week_Saturday','Day_of_week_Sunday', 'Day_of_week_Thursday', 'Day_of_week_Tuesday','Day_of_week_Wednesday'

## Portfolio 3:
In the portfolio 3, the goal is to predict the genre of books by looking at its summaries. The dataset contains a large number of books, but the requirement needs to classify the books into five target genres such as Children's literature, Science Fiction, Novel, Fantasy, and Mystery. In this portfolio, I have a chance to deal with categorical values. I have built three predictive models to classify the books. I used train_test_split function to split the data into training data(80%) and testing data(20%). I fitted the model with training data and predicted it with testing data.
* LogisticRegression model: The accuracy score when using LogisticRegression to classify genres of the books is 0.615. The number of books which are classified correctly is 1102.
* RandomForestClassifier model: The accuracy score when using RandomForestClassifier to classify genres of the books is 0.6.  The total of precisely predicted books decreases from 1102 to 1081. 
* GaussianNB model: The accuracy score when using GaussianNB to classify genres of the books is 0.539. That number is lowest compared to the two above models. In the confusion matrix, the total of the correctly classified books is 965, which is about 200 lower than for using Logistic Regression and about 100 lower than the Random Forest Classifier methods.

**From the result, I conclude that in three predicted model which are used in this Portfolio, LogisticRegression model is most suitable for classifying the genre of books from summaries.**  