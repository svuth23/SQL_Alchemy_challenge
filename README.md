# SQL_Alchemy_challenge
# Surfsup
![image](https://github.com/svuth23/SQL_Alchemy_challenge/assets/136966712/7b086514-8de9-4b0f-8deb-1491fae482b0)

For trip planning, we have  decided to do a climate analysis about the area. The following sections outline the steps that need to take to accomplish this task.

# Part 1:
# Analyse and Explore the Climate Data
In this section, used Python and SQLAlchemy to do a basic climate analysis and data exploration climate database. 
## Requirements:
1. SQLAlchemy ORM queries,
2.  Pandas,
3. Matplotlib.
To finish task ,we followed  the steps:

1. we used the provided files (climate_starter.ipynb and hawaii.sqlite) to complete climate analysis and data exploration.

2. Used the SQLAlchemy create_engine() function to connected to SQLite database.

3. Used the SQLAlchemy automap_base() function to reflect your tables into classes, and then save references to the classes named station and measurement.

3. Linked Python to the database by creating a SQLAlchemy session.

5. we closed session at the end of  notebook.

6. perform precipitation analysis and then a station analysis by completing the steps in the following two subsections.

# Precipitation Analysis
1.Find the most recent date in the dataset.i.e 
 2017-08-23

2. Using that date, get the previous 12 months of precipitation data by querying the previous 12 months of data.
seelected only  "date" and "prcp" values.
(used valuesmost recent date is: 2017-08-23
one year before recent date is:2016-08-23)
3. Load the query results into a Pandas DataFrame. Explicitly set the column names.

4 Sort the DataFrame values by "date".

5. Plot the results by using the DataFrame plot method, as the following image shows:
![image](https://github.com/svuth23/SQL_Alchemy_challenge/assets/136966712/2db9ce09-d267-47c0-87fb-82abdda8054c)

A screenshot depicts the plot.

6.Used Pandas to print the summary statistics for the precipitation data.

precipitation
count	2021.000000
mean	4.505888
std	11.713487
min	0.000000
25%	0.000000
50%	0.500000
75%	3.300000
max	170.200000

# Station Analysis
1.Design a query to calculate the total number of stations in the dataset.i.e (9)

2.Design a query to find the most-active stations (that is, the stations that have the most rows).
To do so, complete the following steps:
List the stations and observation counts in descending order.
### The  results is :
[('USC00519281', 2772),
 ('USC00519397', 2724),
 ('USC00513117', 2709),
 ('USC00519523', 2669),
 ('USC00516128', 2612),
 ('USC00514830', 2202),
 ('USC00511918', 1979),
 ('USC00517948', 1372),
 ('USC00518838', 511)]
find  which station id has the greatest number of observations? i.e  (USC00519281) 

Using the most-active station id, calculate the lowest, highest, and average temperatures.
The result is :
[(12.2, 29.4, 22.03582251082252)]

3.Design a query to get the previous 12 months of temperature observation (TOBS) data. To do so, 
Filter by the station that has the greatest number of observations.
Query the previous 12 months of TOBS data for that station.

 4.Plot the results as a histogram with bins=12, as the following image shows:
![image](https://github.com/svuth23/SQL_Alchemy_challenge/assets/136966712/278b1fa4-d295-42b6-aec2-ecde39385fb7)

A screenshot depicts the histogram.

5.Close your session.

# Part 2:
## Design Your Climate App
completed initial analysis,  design a Flask API based on the queries that  just developed. To do so, use Flask to create your routes as follows:

# 1./
Start at the homepage.
List all the available routes.

# 2. /api/v1.0/precipitation
Convert the query results to a dictionary by using date as the key and prcp as the value.

Return the JSON representation of your dictionary.

# 3. /api/v1.0/stations
Return a JSON list of stations from the dataset.
# 4. /api/v1.0/tobs
Query the dates and temperature observations of the most-active station for the previous year of data.

Return a JSON list of temperature observations for the previous year.

# 5. /api/v1.0/<start> and /api/v1.0/<start>/<end>
Return a JSON list of the minimum temperature, the average temperature, and the maximum temperature for a specified start or start-end range.
For a specified start, calculate TMIN, TAVG, and TMAX for all the dates greater than or equal to the start date.
For a specified start date and end date, calculate TMIN, TAVG, and TMAX for the dates from the start date to the end date, inclusive.
Joined the station and measurement tables for some of the queries.
Used the Flask jsonify function to convert your API data to a valid JSON response object.
