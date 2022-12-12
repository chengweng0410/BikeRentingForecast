# Bike Renting Forecast Analytic

## <p align="right">[Portfolio Main Page](https://github.com/WengWeng0410/Weng_Portfolio)</p>

This is a notebook on predicting total rentals of bike renting system. Bike renting system is a system for bicyles renting, including processes getting membership, rental and bike return through kiosk located throughout a city. Data generated (date, season, wind speed, temperature, humidity etc) from this system is used to predict the number of future rental. <br>

**Business Question**: What is the predicted number of bike rental given weather data? 

## Code and Resources Used

**Python Version:** 3.7 <br>
**Packages:** numpy, pandas, seaborn, matplotlib, sklearn <br>
**IDE:** Google Colab <br> 
**Dataset:** https://www.kaggle.com/c/bike-sharing-demand/overview <br>
**Python Script:** [Notebook](https://colab.research.google.com/drive/1C-tv2pzjv9cHketUwl0Ahc1W4GpBA-Ms?usp=sharing)

## Data Gathering

The dataset used in this project can be downloaded from Kaggle (link as shown above). It is hourly rental data spanning two years where test data file consists of the first 19 days of each month and the records of the rest of days until end of the month are in the test data file. This dataset consist of 1338 rows and 7 features. The information of the dataset includes: <br>
* datetime - hourly date + timestamp  
* season -  1 = spring, 2 = summer, 3 = fall, 4 = winter 
* holiday - whether the day is considered a holiday
* workingday - whether the day is neither a weekend nor holiday
* weather <br> 
1: Clear, Few clouds, Partly cloudy, Partly cloudy <br>
2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist <br> 
3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds <br> 
4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog  <br> 

* temp - temperature in Celsius
* atemp - "feels like" temperature in Celsius
* humidity - relative humidity
* windspeed - wind speed
* casual - number of non-registered user rentals initiated
* registered - number of registered user rentals initiated
* count - number of total rentals

## EDA

To understand the patterns and values of the data by using different types of visualizations. <br>

#### Heatmap
![](/images/1.BRF_heatmap.png)

#### Weather VS Count (Boxplot)
![](/images/2.Boxplot.png)

Based on the figures, the following inferences can be made
* It can be seen that, there are lot of outliers for the count feature.
* Spring season is with the lowest count as compared to Summer, Fall and Winter.
* Most of the outliers are contributed by working (non holiday). 

#### Weather VS Count (Barplot)
![](/images/3.BRF_Barplot.png)

Based on the figures, the following inferences can be made
* Fall season is with the highest number of count (bike rental). This may due to the weahter as the temperature in Fall season is not too hot as Summer and too cold as Winter. 
* More bicyle rental on working day as compared to non-working and holiday. 
* Two peak seasons with high bike rental are 7am - 8am and 5pm - 6pm. This may due to the working hour and school hour in the morning and after office hour and exercise time at the evening. 
* The count of bike rental is about the same from Saturday to Friday. 
* The number of bike rental is high when weather is 1 (Clear, Few clouds, Partly cloudy, Partly cloudy). This is followed by 2, 3 and the lowest when weather is 4. 

#### Distribution of Temperature, Humidity and Wind Speed VS Count
![](/images/4.BRF_Scatter.png)

#### Wind Speed VS Bike Rental Count
![](/images/5.BRF_windVSCount.png)

* It can be seen that both temperature and atemp are with low correlation with count. Hence, we may consider only temperature or aTemp in the machine learning model training. 
* For humidity, it did not show any correlation with count. 
* As for wind speed, gentle breeze of wind speed gives the highest number of bike rental. The higher the wind speed, the lower the bike rental (strong breeze - violet storm)

#### Hour VS Bike Rental Count
![](/images/6.BRF_hourVSCount_season.png)

![](/images/7.BRF_hourVSCount_dayofweek.png)

![](/images/8.BRF_hourVSCount_workingday.png)

![](/images/9.BRF_hourVSCount_holiday.png)

![](/images/10.BRF_hourVSCount_windgp.png)

* The trend for different seasons are about the same, where there are two peak seasons with high number of bike rental, i.e. in between 7am to 9am and 4pm to 8pm. 
* For working days/weekdays, there are two peak hours, i.e. in between 7am to 8am and 6pm to 8pm. The evening time is with higher bike count compared to morning session may due to the exercise time in the evening. 
* As for weekends, the peak hour is in between 12pm to 4pm. 
* As for holiday, it can be seen that the bike rental count is relatively low as compared to non holiday. This can conclude that most of the users are from working adult and school students. 



