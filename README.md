# Crime in San Francisco
An exploratory data analysis and machine learning implementation for the [Kaggle San Francisco crime competition][1]

## EDA
The challenge of the competition is to predict the category of a crime from when and where it occurred. I explored both of those dimensions. Here are a few of the top level findings.

Although some of the categories of crime occur only in certain locations, most of the categories seem to spread across the map and overlap with each other, which will make classification difficult.

![Crime Density](https://raw.githubusercontent.com/ryankresse/sf_crime/master/imgs/crime_density.png)

The frequency of crime in general peaks around noon and 6pm, but certain categories like fraud, narcotics and missing persons have peaks at other times as well.

![Crime Density](https://raw.githubusercontent.com/ryankresse/sf_crime/master/imgs/crimes_by_hour.png)

As you can also see in the plot above, there are some outliers in the midnight hour when many crimes occurred. Specifically, these outliers occured on January 1 -- New Year's Eve.

Plotting the geographic distribution of crime versus time variables like year, month or day of the week didn't reveal any patterns. Though I didn't try it, another approach would be to create those plots per category of crime.

The most frequent location by far is the San Francisco Courthouse and sheriff's office. This could be due to some protocol for filling locations for crimes that don't otherwise have one. The distribution of crimes that 'occurred' at the courthouse differs 
slightly from that of all the other locations, so it may be marginally helpful when building a model.

![Crime Density](https://raw.githubusercontent.com/ryankresse/sf_crime/master/imgs/coords.png)


#### Modeling
In logistic_regression.ipynb, I trained a logistic regression model to predict the probability of each category for each crime. One feature engineering step I borrowed from other competitors was to create a categorical variable for location by combining lattitude and longitude into a string, then encoding those strings as different levels.




### Files
* EDA_TIME.ipynb: an exploration of how crime varies by year, month, day and hour
* EDA_LOCATION.ipynb: examining how crime varies geographically
* logistic_regression.ipynb: preparing the data and training a multinomial logistic regression classifier

[1]: https://www.kaggle.com/c/sf-crime

