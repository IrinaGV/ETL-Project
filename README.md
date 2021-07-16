# ETL-Project
Taxi Revenue and the weather
In my project I tried to find a relationship between the cab fare and the weather as well as the relationship between the cab mileage and the weather.
I used two datasets that I found on Kaggle.com:the historical hourly weather data for Chicago, 2016 and Chicago taxi trips for 2016.
I started working with the hourly weather data first. Since the file had temperature in Kelvin I converted it to Farenheit by using a formula. I renamed the columns and applied aggregation on "Temperature" column to find the average daily temperature.
My taxi trips file consisted of 12 different csv files, one for each month. After opening each file I had to extract the columns that I needed:trip_start_timestamp,trip_miles,fare. I combined all 12 dataframes by using the append method. To calculate the daily total revenue and mileage I used a groupby function for the date and then applied aggregation on "Trip Miles and "Fare". I merged 2 dataframes by using a merge function. My dataframe had an  hierarchical index  after the aggrgation. I used to_flat_index methond to flatten the index and then I was able to use lookup to rename the columns in my dataframe.
I sorted the dataframe in ascending and descending order to find 5 days with the highest/lowest revenue and highest/lowest mileage. My dataframe didn't show a strong correlation between the revenue and the weather or between the mileage and the temperature.
I plotted my dataframes and calculated the correlation. It showed that the correlation  is very weak, below 0.2.
I loaded the dateframe to MongoDB.
