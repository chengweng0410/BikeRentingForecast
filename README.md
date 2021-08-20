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
1: Clear, Few clouds, Partly cloudy, Partly cloudy 
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





