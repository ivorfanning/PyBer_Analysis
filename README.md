# PyBer Analysis Project Overview
  As we have done the previous analysis of ride-sharing data, the new project step is to summarize the data by city type in order to anaylize how the data differs by city type, and give some recommendations from the analysis results.

# Resources:

-Data Source: city_data.csv, ride_data.csv

-Software: Python 3.7.6, Jupyter notebook, 6.4.8

# Analysis and Results:

  Firstly, I merged two dataset together and then summarize the totoal rides, total drivers, and total fares by city type, and secondly, I calculated the average fare per ride and and per driver. After all the above steps, the ride-sharing data statistics table is created by using pandas dataframe.

```
#  1. Get the total rides for each city type
total_ride_per_cityType = pyber_data_df.groupby(['type']).count()['ride_id']

# 2. Get the total drivers for each city type
total_drivers_per_cityType = city_data_df.groupby(['type']).sum()['driver_count']

#  3. Get the total amount of fares for each city type
total_fares_per_cityType = pyber_data_df.groupby(['type']).sum()['fare']

#  4. Get the average fare per ride for each city type. 
mean_fares_per_ride = total_fares_per_cityType / total_ride_per_cityType

# 5. Get the average fare per driver for each city type. 
mean_fares_per_driver = total_fares_per_cityType / total_drivers_per_cityType

```

  As we can see from the table, the total riders, total drivers and total fares from urban city are much higher than the total numbers in suburban and rural types. however the average fare per ride and per driver are the lowest which we can speculate that the ride-share in urban city type is short, fast and frequent.

![summary stats](https://github.com/ivorfanning/PyBer_Analysis/blob/main/analysis/Summary%20Stats%20per%20city%20type.png)

  Then I create a multi-line chart of total weekly of fares for each city type from Jan to April. From the chart it is obviously the weekly fares in urban city type are higher than suburban and rural, and also we can tell from the chart the total weekly fares are relatively gentle for each city type, the busiest time for all city type is at the end of February.
  
![multi-line chart](https://github.com/ivorfanning/PyBer_Analysis/blob/main/analysis/PyBer_fare_summary.png)

# Recommendations

  1. From the data summary table, we can clearly conclude that the total fares in urban city type is almost twice the suburban and 10 times of rural, so it is taking a high proportion in total fares of all city type, which means in urban city type, the demand of ride-sharing is huge and we should add more drivers in urban to satisfy the high ride-sharing demand. 

  2. Even though the average fare per ride and per drive in rural area are the highest number in all three city types, I still recommend adequately increasing the number of drivers to meet the ride-sharing demand in rural area, because the reason of higher average fare is that ride-sharing in rural area is long disance driving and due to the lack of drivers, the people have not experienced the advantage of ride-sharing. 

  3. From the multi-line chart we can see the lowest fares in urban city type happened in the end of Dec and the begining of Jan due to holiday season. we could add some incentive reward in the lower fare period to give the driver more prositivity.
