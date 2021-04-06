# Data Visualization: Ford Go Bike
**by Zakariya Boutayeb

*Introduction<br>
*I. Data Wrangling<br>
*II. Univariate Exploration<br>
*III. Bivariate Exploration<br>
*IV. Multivariate Exploration<br>
*Conclusion<br>

#Introduction:

Implemented in August 2013, Ford GoBike is the first bike-sharing system introduced in the San Francisco Bay Area, California. 
Ford GoBike system had over 7,000 bicycles in 540 stations across across San Francisco, East Bay and San Jose. 
On June 28, 2017, the system officially launched as Ford GoBike in a partnership with Ford Motor Company. Lyft acquired and rebranded the service in 2019.

Ford GoBike, like other bike share systems, consists of a fleet of specially designed, sturdy and durable bikes that are locked into a network of docking stations 
throughout the city. The bikes can be unlocked from one station and returned to any other station in the system, making them ideal for one-way trips. 
The bikes are available for use 24 hours/day, 7 days/week, 365 days/year and riders have access to all bikes in the network when they become a member or 
purchase an access pass.

## What is the structure of your dataset?
Ford GoBike System Data includes information about individual rides made in a bike-sharing system covering the greater San Francisco Bay area. 
The dataset explores the Ford GoBike's trip data for public containing approximately 183,412 bike rides on february, 2019.
The data includes: Trip Duration (seconds) , Start Time and Date , End Time and Date , Start Station ID , Start Station Name , Start Station Latitude , 
Start Station Longitude , End Station ID , End Station Name, End Station Latitude , End Station Longitude , Bike ID , 
User Type (Subscriber or Customer – “Subscriber” = Member or “Customer” = Casual) , Member Year of Birth, Member Gender.

## What is/are the main feature(s) of interest in your dataset?
Our data analysis process for this project will provide a step by step guidance, starting by asking a series of questions, then wrangling and exploring the dataset, 
and finally drawing some conclusions as well as communicating the findings.

- Where do Ford GoBike Bikers ride?<br>
- How long does the average trip take?<br>
- Which stations are most popular?<br>
- What time of day and days of the week are most rides taken on?<br>
- Does the above depend on if a user is a subscriber or customer?<br>

## What features in the dataset do you think will help support your investigation into your feature(s) of interest?

I would say that the duration, day of the week, time, and location information will help me the most.

We are going to use Python visualization libraries, including matplotlib and seaborn, to systematically explore Ford GoBike System Data dataset, 
starting from plots of single variables and building up to plots of multiple variables. Then, we are going to produce a presentation that illustrates 
interesting properties, trends, and relationships that will be discovered in the dataset.

# Data Wrangling:

Data Wrangling includes data gathering of Ford GoBike sharing system dataset, then assessing the dataset both visually and programmatically, 
indentifying the presence of any quality or tidiness issues and finally cleaning the dataset to improve its quality which will help us further on to analyze
our data and draw conclusions.

## Quality issues:

- Q 1: Missing values in columns: start_station_id, start_station_name, end_station_id, end_station_name and also member_birth_year and member_gender.
- Q 2: Drop columns: start_station_latitude, start_station_longitude, end_station_latitude, end_station_longitude, and bike_share_for_all_trip
- Q 3: start_time and end_time should be datetime64 dtype instead of objects
- Q 4: There are two variables in one column which violates the "each variable forms a column" requirement.
- Q 5: user_type, member_gender and bike_share_for_all_trip can be set to category instead of objects
- Q 6: bike id can be set to object instead of dtype int64
- Q 7: member_birth_year should be set to int64 instead of dtype float64
- Q 8: For further analysis, a new column of age group should be created as well as another one for duration in minutes

## Data cleaning :

Data cleaning is the third step in data wrangling process. This entails formatting the columns into appropriate data types and extracting essential data. 
First, I will isolate the hour and day of the week from start_time for visualizing bike usage over time. 
In addition, I will convert member_birth_year into member_age and group_age. Moreover, I will convert duration_sec into duration_min. 
Finally, I will reorder the column placement for better readability and analysis. The cleaned data frame contains 17 descriptors for around 175 thousand rides.

# Exploration of Data:

After having trimmed and cleaned the dataset, we are ready to move on to data exploration. So, we are going to compute statistics and create visualizations 
with the aim to anwer the research questions that we have posed in the introductory section. 

- Univariate analysis will refer to a descriptive statistical technique that is applied to the dataset containing a single variable.
- Bivariate visualizations simultaneously analyzes two variables in order to explore the possibilities of an empirical relationship between them.
- Multivariate analysis is based on the multivariate statistics which help to observe and analyzes multiple two or more independent variables simultaneously.

# Conclusions:

To summarize our findings:

- Most of the rides are short distance, within a range of 5mn to 15mn (300 sec to 900sec), with a median of 8.5 and mean of 11.73 minutes. 
This means that GoBike share system offers an affordable short-term mode of transport. The distribution is slightly skewed to the right, 
reinforcing the idea that the bikes are generally used for short trips.

- Customers trips are usually longer than the ones of subscribers, most probably due to the fact that most Customers are tourists and then have plenty of time 
to explore the Bay Area and enjoy cycling. However, Subscribers prefer quick rides and then use bikes sharing system only for their commute to and from work/school.

- GoBike users are mostly subscribers with 90.5% of all bikers while customers represent only 9.5%. This means that commuters prefer subscribing to 
the monthly memberships or annual pass while customers who are tourists in most cases, prefer holding a single-ride or day pass.

- We have found that male users outnumber the female users. The majority of the rides are made by men with more than 130,000 rides during February 2029 
while only 40,000 come from women. This means that GoBike sharing is predominately operated by males.

- The ages of the majority of users range from mid-twenties to mid-thirties, with a median of 32 and mean of 34.19

- There is a consistent use of bike sharing system mostly during business or school days compared to weekend, which means that even in February 
supposed to be very cold commuters prefer using bike rides for their daily commute to workplaces and schools etc.

- The most active stations are San Francisco Caltrain Station 2 (Townsend St at 4th St), Market St at 10th St, Montgomery St BART Station (Market St at 2nd St), and also San Francisco Ferry Building (Harry Bridges Plaza) which are connceted to mass public transportation (Train, Bart and Ferry). Commuters have many options to get to the city either by using the train, bus service and also by using the ferry that connects Oakland, Alameda, and Vallejo to the city. While, many subscribers are commuting to the city for work and, therefore, bike rentals will concentrate near major transit stations during the rush hours of 8 AM and 5 PM. Customers might be tourists who like to ride a bike during the weekend. The reason why, the number of trips increases during weekends in the tourist attractions like Ferry building and Embarcadero (close to piers).

- More rides are made on the weekdays than weekends. This means that subscribers (90.5% of the bikers) use bike rides mostly on business days for their commute to work 
or to home while occasional customers (9.5%) use bike rides every day but with a greater usage than subscribers on weekends for their recreational activities.

- Customers might be tourists who like to ride a bike during the weekend. Also, the number of trips increases in the tourist attractions like Ferry building and 
Embarcadero (close to piers). On the other hand, subscribers might be commuters. The trips in subscribers increase during the weekdays, the number of trips gradually 
increases on weekends. We noticed also that there are many outliers because customers forgot to log off from the system after using the bike.

One of the limitations to draw perfect conclusion is that the dataset contains only data from February 2019 and also there are some outliers due to the miss-use of 
the Ford GoBike System. In addition, the database have some quality issues that have been cleaned which leads that many data were excluded from our analysis. 
Finally, the dataset needs to be updated with more data of other months of the year in order to investigate it deeper with new features and draws new findings.


