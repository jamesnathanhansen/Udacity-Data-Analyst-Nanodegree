# Ford GoBike System Dataset Exploration
## by James Hansen

## Dataset

### Ford GoBike System Data (38 MB, CSV File)

This data set includes information about individual bike rides made in a bike-sharing system covering the greater San Francisco Bay area. The dataset file can be found in this folder as `fordgobike.csv`.

The data consists of information regarding 183,412 bike trips, including information on trip duration, start/end times and locations, as well as member gender, birth year and customer type.

## Preliminary Wrangling

After preliminary wrangling, the final dataset had 174952 entries with 19 features. During wrangling, all null values were dropped from the data and the outliers found in the member_birth_year column were replaced with the median value. Additionally, data types were converted to the appropriate type. 

Three new features were created as well member_age (derived from member birth year) and duration_min and duration_hr (derived from duration_sec) which hold rounded values for trip duration.

## Summary of Findings

In exploration, I intended to understand different customer demographics and their effect on the each other as well as how bike usage vary per hour, day and week in the dataset.

To do so, I divided my features into numeric, (nominal) categorical, spatial and time-series types and then explore then individually and together.

Frequency plots of categorical features revealed that males members compose about 3 times as much of the trip data as female members. The distribution of the member's age indicated a right-skewed distribution with most common user age of 31 years old. Further investigations with the box plot showed that regardless of categorical differences, at least 50% of the member users were under 35 years old.

Distribution plots of bike trip duration unveiled a extremely right-skewed distribution. However, due to the range of the values, the plot appeared small so I replotted and zoomed in by limiting the x-axis. This help indicate that the most common bike trip duration was 6 to 8 minutes. After applying the log transformation, the distribution appeared approximately Gaussian shaped. Grouping the data by gender, indicated that females have slightly higher average trip duration and larger variance.

Exploration of the time-series data showed interesting cycles on bike usage. The average number of trips per day of the week indicated that weekend usage was lower than week dy usage. Plotting the total of bike trip per day over the month confirm this pattern - a incline on Monday and Tuesday, a peak around Wednesday ans Thursday with a sharp drop off on the weekends. Oddly, the 13th of February had similar usage to the weekends - perhaps its the day before Valentine's Day is why. Finally, an analysis by dividing the data over a 24 hour cycle and then faceting by day of the week showed two patterns. During the work week, bike usage spiked twice. Once on the morning and one in the afternoon. On the weekend, there was a single spike with a smaller gradient and maximum height during midday.

The spatial data simply indicate that there are three large clusters of start and end destinations.

## Key Insights for Presentation

> Select one or two main threads from your exploration to polish up for your presentation. Note any changes in design from your exploration step here.

For the presentation, I focus on just the bike usage patterns over the course of a day, week and month. I start by introducing the bike trip duration variable, followed by the usage patterns by plotting the average number of trips per day in a week, the total number of trips per day in a month and the hourly trips faceted by day of week.

Afterwards, I go on to highlight findings about member age and gender through box plots and bar plots respectively.