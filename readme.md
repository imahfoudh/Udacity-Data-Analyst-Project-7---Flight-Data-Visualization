# Analysis of US Flight Data for 2018-2019 from Bureau of Transportation statistics
## by Mohammed Almahfoudh


## Dataset

> The data was extracted from the Bureau of Transportation Statistics database from the following link:
- https://www.transtats.bts.gov/DL_SelectFields.asp?Table_ID=236

> Since the data size is big, it is not included in this repo. The prepared file can be downloaded from this MEGA link:
- https://mega.nz/file/EnBAFQ6Y#8_MDFv3geCUD6K7AV0KSaNHFxC3MVxCvMYMgSRc5AGs

> Due to the nature of the large database, the column selection was done to simulate the data used by Statistical Computing Statistical Graphics in Data Expo ‘09, as shown in the following link:
- http://stat-computing.org/dataexpo/2009/the-data.html

> The data had to be extracted on month by month basis, whoulc would need ot be merged into one CSV file for further analysis, the code for combining the CSV is based on FreeCodeCamp code as shown in the following link:
- https://www.freecodecamp.org/news/how-to-combine-multiple-csv-files-with-8-lines-of-code-265183e0854/

> The data is expected to require some wrangling, which would be conducted inside this notebook. The same wrangling steps will be repeated in the explanatory analysis notebook due to the large filesize (Approx 1.7GB)


## Summary of Findings

### Univariate Analysis Findings

**Flight Times Data**:
- Yearly Comparision: Seems like there were more flights in 2019 than 2018. Let's take a look at the number of flights per month (total for both years)
- Monthly Comparision: Some month appear to have fewer flights. This can be related to the number of days in the month (e.g. February is 28/29, while July and August are 31 days)
- Day of the week comparision: From a fist look Saturday appear to  have lower flight numbers, this could be due to the fact that Saturday is the first day of the weekend, folllowed by higher flight numebrs on Sunday.

**Flight Duration and Cancellation Data**:
- Duration: The flight duration is skewed to the right, with most if the flights being 150 minutes (2.5 hours) or shorter. This would be interesting to see who operates such flights.
- Cancellation: Most of the flight cancellations are due to "B" (Weather) reasons forllowed by "A" (Carrier) reasons. It would be interesting to see when do these cancellations occur.

**Flight Delays**:
- Departure Delay: The departure delays appear to be right skewed (which is reassuring), howerver there is a significant delays in some flights.
- Arrival Delay: Again, The arrival delay is skewed to the right, with a pattern that is almost identical to the Departure delay, which is expected. It would be interesting to see the relationship between the Departure and Arrival delays.

**Flight Operators**:
- The number of flights by WN (SouthWest Airlines) is significantly exceeding the other carriers in this database, followed by known big airlines such as American Airlines and DElata. It's interesting since SouthWest is a low-cost carrier with short flights in nature. It would be interesting to look at the relationship between the carrier and flight times.

### Bivariate Analysis Findings

- **Delay Correlations**: As assummed, there is a strong positive correlation between the two delay features. However the delay relationship does not apear to be a 1:1 relationship since the impact seems to be lower on longer flights rather than shorter ones. The clustering on the left is an indicator of the right skewed patteren identified earlier.
- **Flight Duration Monthly Distribution**: All months appear to have the similar flight durtion (Elapsed Time) distribution, with exception to one odd outlier in March. However,all have outliers outside the Quartile Range. This could be due to the overwhelming number of short flights by low cost airlines as shown in the Univariate analysis.

- **Flight Duration for top 5 airlines**: The flight duration of the top 5 airlines look interesting, since there are some airlines like WN (Southwest) and OO (Skywest) with a tight flight duration distribution in comparision to the other airlines (Delta, American Airlines, and United Airlines). It would be interesting to further examine the top five airlines in terms of other factors such as flight delay, and cancellation by month.

- **Correlation between physical distance and airtime**: The relationship is obviously strong and postitive. However, interestingly, the airtime in the sample seem to vary widely between flights with similar distances. There are also some observable gaps in some distance ranges between the 3000 and 5000 miles mark.

- **Flight Cancellation Across Months/Years**: The chart showed interesting pattern in cancellation for the two year sample we have. There is a high cancellation in both years in specific months such January (due to snow perhaps?), and June-August. Some months do vary between the years which is interesting, it may indicate special events during that specific year. It would be interesting to look at different plots for every cancellation type.


### Multivariate Analysis Findings

**Flight Cancellation Across Months/Years in Relation to Cancellation Type**: The faceted chart shows an interesting pattern, while Cancellation Code A (Carrier) does not appear to follow a multural distribution between the years, the Code B (Weather) ones are interestingly similar with small changes (maybe due to climate change?). Code C cancellations (National Air System) is also following a similar trend in both years.

**Flight Distance-Duration Plot Across the Years for Top 5 Airlines by Traffic**: Both years have almost identical pattern. The chart showed the way the airlines operate in the US. we could see how Southwest distance is limited to  approx 3000 miles, while SkyWest airlines is even shorter, approx 2000 miles. This could be related to the fleet type they operate with.


## Key Insights for Presentation

The presentation was driven based on the exploratory analysis done as a preparation. The graphs were cleaned (titles and labels) for better experience. Overall the slides focused on the flight patterns for the top five airlines in air traffic in terms of Cancellations, Delays, and Flight Durations/Distance.
