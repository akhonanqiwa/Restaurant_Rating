# Restaurant Rating Analysis

## About the project 

This project is about analyzing the ratings of Mexico restaurants. 
The dataset contains customer surveys that were carried out in Mexico in the year 2012 to collate information about each restaurant, 
their cuisines, information about the consumers and the preferences of the consumers.

### Data Sources

The dataset consist of 5 tables:
- Restaurant data : restaurant.csv
- Restaurant Cuisines data : restaurant_cuisines.csv
- Consumers data : consumers.csv
- Consumers Preferences data : consumers_preferences.csv
- Consumers Ratings data : ratings.csv

### Tools

- Excel - Data Cleaning
- Power Query - ETL(data sorting, data transformation)
- Power Pivot - ERD diagram (table joins/relationships for data modeling)
- PowerBI - Data Visualization (dashboard)
- DAX - Data aggregation

### Data Preparation

After examining and extracting the data from the 'Restaurant_Ratings.zip' file, which contains five CSV files 
- I uploaded the data into Power Query Editor for cleaning and transformation.
- In this process, I replaced null values with 0 and utilized the first row as headers for certain datasets. 
- Following data cleaning, I observed that some datasets share one or two connections, notably the consumer_id 
  and restaurant_id, which serves as the basis for merging all the datasets. 
- After I have done analyzing the data, I then created relationships in Power Pivot to connect and sync the data.

### Exploratory Data Analysis

1. What can you learn from the highest rated restaurants? Do consumer preferences have an effect on
   ratings?
2. What are the consumer demographics? Does this indicate a bias in the data sample?
3. Are there any demand & supply gaps that you can exploit in the market?
4. If you were to invest in a restaurant, which characteristics would you be looking for?

### Data Analysis

- Performing data aggregation using DAX functions by creating measures.
  - The below function calculates the total number of consumers participated in the ratings.
    ``` Total consumers = COUNTROWS('consumers') ```
  - The below function calculates the ratings by restaurant names using the unique value (Consumer_ID).                        
    ``` Total conPerName = CALCULATE(DISTINCTCOUNT(ratings[Consumer_ID]),FILTER('ratings',RELATED(restaurant[Name]))) ```
  - The below functions shows the demographics of the consumers:
      1. Average age of consumers
      ```AVR_Age = AVERAGE(consumers[Age])```
      2. Marital Status of the consumers
      ``` Married = CALCULATE([Total consumers],'consumers'[Marital_Status]="married") ```                      
      ``` Single = CALCULATE([Total consumers],'consumers'[Marital_Status]="Single") ```

### Results/Findings

1. Overall Ratings by Restaurant: The highest rated restaurant is "Tortas Locas Hipocampo" with a rating of 48, 
   followed by "Puesto De Tacos" with 41, and "Cafeteria Y Restaurante El Pacifico" with 33. 
   This suggests that "Tortas Locas Hipocampo" is performing exceptionally well in terms of customer satisfaction. 
   Consumer by Preferred Cuisine: The most preferred cuisine is Mexican, with 97 consumers preferring it. 
   Followed by American (11 consumers), and then Cafeteria and Pizzeria (9 each). 
   This indicates a strong preference for local cuisine among the consumers, which might be influencing the high ratings for restaurants 
   that offer Mexican food, like "Tortas Locas Hipocampo."

2. Restaurant Food Ratings by Age, Occupation & Marital Status: The table shows a variety of consumers, 
   mostly younger (average ages 21-25), students, and single. 
   This might indicate a bias towards younger, single individuals in the data sample, 
   which could affect the generalizability of the results to other demographic groups of restaurant goers in Mexico. 
   Service Rating by Smoking Allowed: Most of the service ratings are from places 
   where smoking is not allowed (73.46%), which might skew insights about consumer preferences related to smoking areas. 
   Average Overall Rating by Alcohol Service: 
   The majority of ratings come from restaurants that offer “Full Bar" (34.29%) followed by those with 
   “Wine and Beer”(33.8%). Restaurants with No alcohol service have the least ratings (31.9%).

3. Service Rating by Alcohol Service: A significant majority (63.19%) of restaurants offer full bar services, which receive a higher service rating. 
   This suggests a strong market preference for restaurants with extensive alcohol service options.
   Service Rating by Smoking Allowed: Most restaurants (74.16%) do not allow smoking, aligning with a general trend towards non-smoking environments. 
   This could indicate a preference or regulatory environment favoring non-smoking establishments. 
   Preferred Cuisine by Budget: Mexican cuisine shows a high preference across all budget categories, especially in the medium budget range. 
   This indicates a robust demand for Mexican cuisine. Other cuisines like American, Cafeteria, and Pizzeria also show some demand particularly in the medium budget range.

### Characteristics I would consider if I were to invest in a restaurant in Mexico.

- Alcohol Service: Opt for a full bar setup to attract a larger clients, as indicated by the high service ratings for such establishments. 
- Smoking Policy: Invest in a non-smoking restaurant to align with the majority preference and possibly regulatory trends.
- Cuisine Type: Mexican cuisine is a safe bet given its widespread popularity. However, offering a unique twist 
  on traditional dishes or high-quality ingredients could differentiate the restaurant. 
- Price Point: Targeting the medium price range could be optimal, as it appears to cater to the largest segment 
  of the market while still allowing for profitability. 
- Location: Choose locations in cities with higher overall ratings to capitalize on existing positive perceptions
  of dining experiences in those areas.

By focusing on these characteristics, an investment in a restaurant is more likely to succeed, 
tapping into established market preferences while offering distinctive qualities that can set the restaurant apart from competitors.

### Conclusion

The analysis suggests that consumer preferences particularly towards Mexican cuisine and nonsmoking environments significantly influence restaurant ratings. 
The demographic data indicates a potential bias towards younger, single individuals which should be addressed in future surveys for more balanced insights. 
Additionally, the type of alcohol service provided appears to correlate with the frequency and possibly the quality of ratings with "Wine & Beer" being 
the most favorable option.











