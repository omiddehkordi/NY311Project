# NY911Projects
1. Understand the dataset:
1.1 Import the dataset
Dataset is imported with read_csv() method
1.2 Visualize the dataset
Visualize by looking at first 5 entries
1.3 Print the columns of the DataFrame 
First column is Created Date and the last one is Location
1.4 Identify the shape of the dataset
There are 364558 different entries with 52 variables (columns)
1.5 Identify the variables with null values
There are multiple values with almost all Null values such as Garage lot Name
2. Perform basic data exploratory analysis:
2.1 Draw a frequency plot to show the number of null values in each column of the DataFrame
This visualizes what was found out in the previous question
2.2 Missing value treatment
2.2.1 Remove the records whose Closed Date values are null
There were 2381 entries with Closed Date as null. After removing them with the dropna() method there were 0
2.3 Analyze the date column, and remove entries that have an incorrect timeline
2.3.1 Calculate the time elapsed in closed and creation date
The Time elapsed is calculated and added as a new column in the Data frame by subtracting Closed Date and Created Date after converting the dtype with pd.to_datetime()
2.3.2 Convert the calculated date to seconds to get a better representation
The time is converted with dt.seconds for each values in column Elapsed_Time
2.3.3 View the descriptive statistics for the newly created column
count    362177.000000
mean      13898.326843
std       13631.143892
min           1.000000
25%        4509.000000
50%        9539.000000
75%       18613.000000
2.3.4 Check the number of null values in the Complaint_Type and City columns
There are 0 null values for Complaint Type and 674 null values for City
2.3.5 Impute the NA value with Unknown City
The use of replace() method on the NA values results in 0 NAs in column City having been replaced by unknown City
2.3.6 Draw a frequency plot for the complaints in each city
Brooklyn, New York and Bronx have the highest frequencies
2.3.7 Create a scatter and hexbin plot of the concentration of complaints across Brooklyn
Most complaints fall within values 150000 and 210000 on y axis and 0.98 and 1.02 on x axis
3. Find major types of complaints:
3.1 Plot a bar graph to show the types of complaints
The top 3 complaint types for the whole dataset are Blocked Driveway, Illegal Parking, and Noise - Street/Sidewalk
3.2 Check the frequency of various types of complaints for New York City
Noise - Street/Sidewalk      22245
Noise - Commercial           18686
Illegal Parking              14549
Noise - Vehicle               6294
Homeless Encampment           3060
Blocked Driveway              2705
Vending                       2638
Animal Abuse                  1941
Traffic                       1769
Noise - Park                  1243
Derelict Vehicle               695
Drinking                       321
Urinating in Public            264
Bike/Roller/Skate Chronic      254
Noise - House of Worship       222
Panhandling                    206
Disorderly Youth                81
Posting Advertisement           49
Illegal Fireworks               38
Graffiti                        25
Squeegee                         4
3.3 Find the top 10 complaint types
The top 10 complaints are Noise street/Sidewalk, Noise Commercial, Illegal Parking, Noise Vehicle, Homeless Encampment, Blocked Driveway, Vending, Animal Abuse, Traffic, Noise Park
3.4 Display the various types of complaints in each city
Separate List of each complaint type for each city
3.5 Create a DataFrame, df_new, which contains cities as columns and complaint types in rows
Index Column is The Complaint Types and the df shows the number of complaint types for each city
4. Visualize the major types of complaints in each city
4.1 Draw another chart that shows the types of complaints in each city in a single chart, where different colors show the different types of complaints
Brooklyn, Bronx and New York are the outliers
4.2 Sort the complaint types based on the averageRequest_Closing_Time grouping them for different locations
All relatively similar
5. See whether the average response time across different complaint types is similar (overall)
	5.1 Visualize the average of Request_Closing_Time
Animal in the park closing time was the only significantly higher time
6.Identify the significant variables by performing statistical analysis using p-values


7.Perform a Kruskal-Wallis H test
reject the Null Hypothesis, because the pvalue is less than alpha 0.5
