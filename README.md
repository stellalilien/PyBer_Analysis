# PyBer Analysis

## Overview
The purpose of this project was to analyze the ride sharing data provided and identify differences by city type (Urban, Suburban, and Rural).

## Results
In order to perform this analysis it was necessary to group the data and produce a DataFrame indexed by city type. This was done by first declaring three new variables as follows:

total_ride_count = pyber_data_df.groupby(["type"]).count()["ride_id"]

total_driver_count = city_data_df.groupby(["type"]).sum()["driver_count"]

total_fares = pyber_data_df.groupby(["type"]).sum()["fare"]


Using these new variables averages per ride and per driver were calculated:

average_fare_per_rider = total_fares / total_ride_count

average_fare_per_driver = total_fares / total_driver_count

All of this data was then organized into a pandas DataFrame. Viewing the data in this way we can clearly see that Total Rides, Total Drivers, and Total Fares in Urban cities far surpassed those in Suburban and Rural cities and conversely, Average Fare per Ride and Average Fare per Driver were highest in Rural cities and lowest in Urban cities. 

<img width="299" alt="image" src="https://user-images.githubusercontent.com/94754972/151723243-654dabbe-2493-45ce-989d-94931fa1c1d3.png">



### Total Fare by City Type
Using the DataFrame above a Pivot Table was created. Using the date as the index the fares were then organized into columns representing each city type. The dates were then resampled to show the sum of the fares by city types for each week of selected date range. 

<img width="127" alt="image" src="https://user-images.githubusercontent.com/94754972/151723472-3655458f-08c4-4fa0-90f1-d7b5ac12b076.png">


This data was then plotted to show the weekly fare totals for each of the three city types.

<img width="376" alt="image" src="https://user-images.githubusercontent.com/94754972/151723580-e276c9c1-7240-46ed-ad87-987f81146386.png">

## Summary
Based on the results of this analysis it is clear that Urban cities have the highest number of rides and drivers as well as the sum of fares while Rural cities have the lowest amount of the same three categories. Average fares per ride and per driver are both highest in Rural cities and lowest in Urban cities. Using this information several business strategies could be considered:

-- The higher average fares per ride in Rural cities indicates that while the total rides are less those riders are going longer distances. Adding a surcharge for rides over a certain distance could bring the total fares closer to those of the larger cities.

-- Higher average fares per ride in Rural cities could also lead to higher total fares if targeted marketing is used to increase usage.

-- In Urban cities the total rides being so much higher than the other types would lead to a much greater impact on the total fares with a minor price increase.
