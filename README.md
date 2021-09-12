# Project Oslo Bysykkel - How to optimize the bike fleet.

### Big Data - project by Mona Heggen

# Introduction

In this project our hypothesis is that a large part of the distribution problem Osly Bysykkel is experiencing can be solved or alleviated by introducing the concept of "Trekkfugler" / migratory birds. We will try to verify this hypothesis by analyzing public data from Oslo Bysykkel and the Norwegian Meteorological Institute.

# What is the problem?

Oslo Bysykkel are experiencing a number of problems, mainly related to how their service is perceived in media, paying customers and potential customers.

Some of the issues are:

* Empty stations
* Full stations
* Unpredictable availability of bikes
* "Full station anxiety" - where your planned activities are affected by not finding any open spots in stations nearby. Ref ["Aker Brygge-middagen ble ødelagt av bysykkel-kaos"](https://www.dagbladet.no/nyheter/aker-brygge-middagen-ble-odelagt-av-bysykkel-kaos/69981834)
* Bad PR might give paying and potential customers a worse picture of the distribution problem than it really are.

Unpredictable availability as the distribution of the bikes are not optimal based on the actual spread of customers througout the city. Based on observation it's a complex problem distributing bikes on trucks with a max capacity of about 22 during rush hour using the current method.

One of the goals Oslo Byykkel has is to increase the number of trips each bike does. Having a better and/or more optimized distribution of the bikes will probably increase this number.

Environment and pollution are increased by either 1) having a distribution that results in less trips than practically possible results in customers choosing options that pollute more. 2) optimizing distribution by using trucks will result in more pollution than a muscle based distribution model.

## Current measures by Oslo Bysykkel

* Unpredictable free spots in major traffic hubs feeding to other means of transportation. Countered with morgenfugler / "early birds" placed at the hub stations rapidly moving deliverd bikes out of the stations to ensure free spots for new ones arriving.
* Unpredictable free spots due to seasonal events like bathing at Sørenga and school vacations. Countered by "sommerfugler" / butterflies (literaly summer birds) rapidly moving delivered bikes out of the stations to ensure free spot for new ones arriving.

# Solution


## Trekkfugler / migratory birds

"Trekkfugler" or migratory birds, migrators from now on are a concept we propose to Oslo Bysykkel for an environment friendly way to redistribute bikes to where they are needed.

In practice migrators are a concept to enhance the existing redistribution strategy used by Oslo Bysykkel.

The theory is that:

- periods with the highest demand are the periods with the lowest number of bikes available for potential customers in some parts of the city.
- periods with the highest demand are the periods with lowest number of free spots in stations many of the customers would like to park the bikes in.

All in all Oslo Bysykkel are perceived as having to few and to many bikes at same time based on where the user are in the city. This creates bad press, frustrated subscribers and reduces the number of trips travelled.

"With an average of 9.8 trips per bike per day, Oslo City Bike is now one of the most efficiently operated bike sharing systems in the world. We have integrated data analinysis and prediction models into the product to fully optimize operations. This effect-based model is a more sustainable solution, as it minimizes unused resources while maximizing the overall results."
[http://urbansharing.com/projects/bike-sharing](http://urbansharing.com/projects/bike-sharing)

![](img/tweet-GinaLiabo-727851036560494592.png)

[https://twitter.com/GinaLiabo/status/727851036560494592](https://twitter.com/GinaLiabo/status/727851036560494592)

# Trekkfugler / migrators explained

Based on a model a separate app or extension in the existing app allow voluntary users (both paying and not) to help with the redistribution of bikes. Each of these trips rewards the migrator with something. What the reward are will be decided by Oslo Bysykkel.

Examples are:

- a token toward a free subscription (non-paying volunteers)
- a free bike ride at some point in the future (non-paying volunteers)
- free coffee
- free breakfast/lunch
- rebates on public transport

Most trips will not be valid as a migrator trip and the migrator has to commit to a specific route (station a to station b) before picking up a bike and completing the trip. There will also be a time limit based on expected travel time between stations. A partnership between Ruter and Oslo Bysykkel could be created so that migrators can travel without paying for bikes during rush hour.

The workflow for a particular migrator wanting to do a migration would be something like this:

- Decide where they would like to go
- Plot in the desired address OR pick the location on the map
- Pick a route from a list of potential routes based on where they are now and where they would like to go.
- This list could be empty.
- There could be alternatives where end station is far from desired destination, but close to public transport connecting the two places.
- There could be routes with extra bonuses based on:
- Time (deliver bike in 5 minutes for double reward).
- Tourist routes where for example a cruise ship arrives at 13.00 and all migrations to stations near that are extra valuable.
- Unexpected changes in the traffic that particular day.
- "Event" trips due to concerts, festivals and other social gatherings with large amount of participants.
- Commit to completing the migration by picking a bike from the start station
- If there for any reason aren't any free bikes left in the start station when they arrive there, the migration will not start. They can start from the top in case there are a valid start station nearby.
- Transport the bike from start to end station in the allotted time.
- Receive reward
- Tell friends about it

## Why not trucks?

Currently Osly Bysykkel use trucks for the redistribution of bikes. Based on articles in the media it seems like each truck can handle 22 bikes (there might be some with higher capacity). According to Oslo Bysykkel there are about 20.000 trips each day and if the trucks has to redistribute roughly 10% of the bikes during the day that would be approximately 90 trips in optimal conditions.

90 trips should be easy to do during the night when no one can use the bikes, but the need for redistribution is probably at its highest during rush-hour. The chance of being able to fill the truck at one station without emptying that station completely is not really possible at most of the stations around the city. This results in the trip taking extra time, driving from station to station filling up the truck and either place all 22 bikes at empty station or spreading them between two or more high traffic stations.

According to a Oslo Bysykkel tweet the stations are immediately emptied when filled in the period between 07-10 (was specifically referencing St. Hanshaugen, but it's probably safe to guess that this is the pattern around most of the high traffic parts of the city the trucks prioritize filling up).

In addition to all of this, there's the problem of rush-hour being rush-hour. The road traffic hinders the trucks from transporting the bikes where they need to be. Adding more trucks might even increase the time each truck use as they are part of creating more congestion and even worse, pollution.

# What is the data analytics solution you proposed

Our hypothesis was that there is a solution to the distribution problem using the users for distribution. This is "trekkfugler" / migratory birds / migrators.

1. Find the correct data and what should be analyzed. Does temperature correlate to number of trips and distribution of the bikes?
2. Can data be dropped/removed without changing the model?
3. Which, if any, data must be normalized to get a valid result? (There might be a higher number of some weekdays in a month, year or historically).
4. We also want to make the data easier to analyze by creating new columns based on other variables in our datasets. Categorizing the data is also an example of creating a dataset that's easier to analyze.

Which statistical methods do we want to use?

1. Our first thought was that the trips was correlated by a linear regression.
2. It's also interesting to see if there is ay clustering that could reveal patterns.

Obstacles in this project:

1. How reliable is the data? We do not know if the truck based distribution of bikes are represented in the trips dataset. Neither do we know if the mobile bike shops Osly Bysykkel use to fix problems with malfunctioning are counted as trips or not.
2. The distribution might be influeced by factors we don't have data for. One example for that are school vacations, wich might affect some of the distribution patterns.

# What types of data did we use?

We used semi-structured data like csv and json-files in this project. where each rows is a observation or case, and each columns are the variables.

We based our data on two sources, Oslo Bysykkel and weather observations from Meterologisk institutt Frost.

From Oslo Bysykkel we used trips data and a snapshot of the available stations. We did not do any data gathering over time from the stations endpoint they provide to get a "correct" overview for availability at a specific point in time. Instead we decided to use the historical trip data to estimate station availability and usage.

We focused on stations, time of day and travel time merged together from the stations and trips API endpoints.

From the Frost API we decided to start with temperature pr hour measured at Blindern, specifically the minimum temperature pr 1 hour (min(air_temperature PT1H)). Currently we are not using the height above sealevel as a parameter.

We wanted to use the available data to see if there could be a pattern correlating with temperature, time of day and weekday.

We also wanted to find a way to predict where trips would go at certain time from a specifict station, giving a base to work with to prototype the "trekkfugler" idea. This in combination with stations with extreme highs, followed by periods of none use (all bikes are taken as soon as they are available) would in theory reveal good candidates for trekkfugl routes.

To collect the unstructered data from text and multimedia we may need a Deep Learning (DL) detector.

In this project we use numerical(quantitative) data like temperature and number of trips. And categorical data – station ID. 
And we also used station longitude and lattitude coordinates data. We used Travel time in relation to filter out outliers and find the average travel time for a trip. 

The dependent variable in our project is number of trips per unit of time. We want to predict this by looking at weather metrics and hour and the day of the week.

The independent variables are temperature, position of the stations, number of working bikes, time of day and weekday/season.

In further analysis it would be interesting to look also at the height of the start and end stations. This can be found at YR and might be found in Google maps API. 

We have a lot of hypothesis that we want to look at. And it is a lot of conditions that can affect how many trips per hour. 
We start to look at the temperature data. It would also be interesting to use wind and rain and other more complex metrics related to weather down to specific location for each station. The categorical data that is used is m nomainal, the o

The relative variables/columns:

**Categorical:** 

1. id - Start or End title (nomainal) 
2. center.latitude, center.longitude 
3. weekday 
4. Start station, Start time, End station, End time
5. year month day hour

**Numeric:** 
1. Departing/date/hour, Arriving/date/hour, diff 
2. height(m) 
3. temperature(C) 
4. number_of_locks
5. Travel time in s

The trip data is collected by automatic sensors placed in the stations. Weather data is created from actual and estimated observations based on selected weather station. All in all this gives us a high quality data seemingly without human errors, misspelling, poor data entry, missing data and maybe also duplicate data. The sensors is not guarantied to create perfect data. there are some outliers in the trip dataset, that might be due to sensor errors or sampling errors.



## Preparing and Cleaning Data 

In this project we have focused on merging relevant data into the trip dataset, and removing data that is clearly wrong. Creating a new dataset this way might introduce errouneous data based on false assumptions and/or coding errors.

When we analyzed the june 2018 trips dataset we found out that the standard deviation is quite large and the mean and the middle are quite different and these variables is affected by extreme values, as we can see from the maximum and minimum values.

The minimum is not a possible time, it is megative. And the maximum is larger than possible to lend a bike.  

We started to clean data, but it was a little tricky to get all in place before we got an impression on the data. Therefore, we looked at the raw data as it was first. 

Next step was to clean out the trips that 

1.	Is lower than 15 secs
2.	Or over 1 hour.  Reason: 6 hours and 45 minutes is the limit for how long you can have the bike. You pay additional for this. 5kr/15 minutes, max 120 kroner. We decided to also delete the trips over 1 hour due to the fact that they only represent 1.4% of the trips in June. 

Further cleaning were to normalize and look for skewness in the data. We used built-in models from sklearn to this. 

And last check for covariances by tha variables. 


# What type of analysis did you use?

We started to look at the data in different methods:
* scatterplots
* histogram
* boxplot 
* barplot 

We have alot of data and we used supervised learning. Both Linear regression (to predict if there is a relation between the independent variables (X) and the dependent variable (y) and Logistic regression to predict classes. The classes we started to use was binary to simplyfy the model. Example of this is Long/short trip based on traveltime and many/few trips based number of trips pr unit of time. 

**Linear Regression** 
We was looking at these two cases: 
Case 1: X - temperature y - Traveltime
Case 2: X - temperature y - Number of trips 

**Logistic Regression** 
Here we focused to classifie two labels. 

Make two classes: 0 1 testes logistic regression. Where 0 are trips of less than 800 seconds. Predict the model and then evaluate the model by  feeding it into a confusion matrix.
Case 1: X - Temperature,  y - is it more trips/hour or is it fewer because of temperature? two classes. 
Case 2: X - Temperature y, - Long trip or short trip (binary) 


**Clustering**
We also want to look at the possibilities to predict the end station from the start station. It is a complex task to predict the end station from the start station, it is alot of stations that gives us alot of labels. This is too complex for a standard ML algorithm. We tried to use a clustering method to predict this, but the results was not so good. 

It might be a way to figure out how to predict end station for a trip by be making a model for each start station. 

One problem is that the station is not demographically numbered. It is not a logic system from a coordinate point of view. The stations seems to have ID based on when they were built/went online.

It might be possible to make a new index number with parameteres position coordinates longitude and lattitude. and then use a clustering method to find out if there is a pattern.


# What are the results?

We tested the machine learning methods, but it was difficult to get a good result. It was also hard working with more independent variables than one to predict the dependent variable. Therefore,  we only looked at models with one independent variable as part of this project. 

Most of the models gave a very inconsistent R_squared and value, this is going to be 1 if it is a good model. And the mean squared error should be approximately 0. 

The best results we got was approximately 70%. In this model

In one of the Logistic regression models we got a confusion matrix with zeros in the right column, that gave us among other a precision score of zero. The best results for a confusion matrix is when the diagonal spots are much higher than the remaining spots. This gives us higher percentage of true positives and true negatives.

![](img/predictclass-actualclass.png)


# What can be done better? or/and how to move forward?

Further work would be too get a better model that looks at more independent variables and see if there is a pattern. 

Predicting end station from the start station and all the other non correlated variables seems like a good fit for Deep Learning detector. 

Expanding the dataset to include all trips for 2018.

Create a more complex and complete model.

Prototype model for "trekkfugler" that are good enough to be presented to Oslo Bysykkel as a potential project.


# Tables

| Supervised Learning | | | | |
| --- | --- | --- | --- | --- |
| | Linear Regression | | X | y |
| | | Case 1 | temperature | Traveltime |
| | | Case 2 | temperature | Number of trips |
| | | Case 3 | | |
| | Logistic Regression | | | |
| | | Case 1 | Start station | End station |
| | | Case 2 | Temperature | Long trip or short trip (binary) |
| | | Case 3 | | |
| Unsupervised Learning | | | | |
| | Clustering | | | |
| | | Case 1 | Start station | End station |
| | | Case 2 | | |
| | | Case 3 | | |