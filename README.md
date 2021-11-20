# Module_5_Challenge


## Ride-Sharing Data Analysis

## Overview of the Analysis

		The purpose of the analysis of this data was to see how different city types use ride-sharing.  In
	the analysis, there were different factors which were analyzed to see the usefulness of ride-sharing.  Those 
	factors were the city types, fares and average fare per ride, drivers and average fare per driver.

## Results

		After analyzing the data, it was noticed that the urban areas were using ride-sharing more than the suburban and rural
	areas.  From the data that was collected, the urban areas had more usage of ride-sharing than the suburban and rural areas 
	combined.  This is true because there is higher population in the urban areas versus the suburban and rural areas.  Also, much 
	more money was being made in the urban areas because of the amount of usage.  This statistic agrees with the data becaus of the
	same reason as the amount of usage; the higher population means higer usage which equals to more money being made. On the 
	other hand, the average amount per ride and average amount per driver was higher for the rural areas. This makes sense because 
	there was less usage and ride-sharing probably had to charge more to make up for the low amount of usage.  The .count, .sum 
	and .mean functions were used to calculate the results.


	total_rides = pyber_data_df.groupby(["type"]).count()["ride_id"]
	total_rides.head()

	total_drivers = city_data_df.groupby(["type"]).sum()["driver_count"]
	total_drivers.head()

	total_fares = pyber_data_df.groupby(["type"]).sum()["fare"]
	total_fares.head()

	average_fare_per_ride = pyber_data_df.groupby(["type"]).mean()["fare"]
	average_fare_per_ride.head()
	
	This function was used to format the final DataFrame

	pyber_summary_df["Total Rides"] = pyber_summary_df["Total Rides"].map('{:,}'.format)
	pyber_summary_df["Total Drivers"] = pyber_summary_df["Total Drivers"].map('{:,}'.format)
	pyber_summary_df["Total Fares"] = pyber_summary_df["Total Fares"].map('${:,}'.format)
	pyber_summary_df["Average Fare per Ride"] = pyber_summary_df["Average Fare per Ride"].map('${:,.2f}'.format)
	pyber_summary_df["Average Fare per Driver"] = pyber_summary_df["Average Fare per Driver"].map('${:,.2f}'.format)
	pyber_summary_df.head()

	This code was used to show the fare by city type from January to the end of April.

	style.use('fivethirtyeight')

	sum_week_df.plot(figsize=(18,5),)
	plt.xlabel("")
	plt.ylabel("Fare($USD)")
	plt.title("Total Fare by City Type")
	plt.savefig('analysis/Pyber_fare_summary.png')


## Summary
	
		In summary of the analysis, it was found that there was a higher usage of ride-sharing in the urban areas because of 
	the higher population in them.  Also, it was found there was a higher amount of money being generated in the urban areas because
	of the same reason.  I would suggest to the CEO in order to make more money in the suburban and rural areas, I would add more
	drivers in those areas.  On the other hand, if she wanted to increase the amount of money being generated in the urban areas,
	I might consider reducing the amount if costs for one ride to encourage more people to use the service.  Another suggestion
	would be to increase the the number of drivers in all 3 areas to give the population more options to use the service.
