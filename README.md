# King-County-House-Price-Prediction
<img width="614" alt="Screenshot 2023-07-08 at 18 47 41" src="https://github.com/CandiceDataAnalyst/King-County-House-Price-Prediction/assets/127648422/81dfaa75-c317-4179-a8f4-b3489d80db3b">

## PROJECT OVERVIEW
As a data scientist at FlyHomes, I am tasked with analyzing house sales data in the King County area to build predictive models for sale prices and identify the significant factors influencing these prices.</p>
**Business Question**:</p>
**Location**: Which areas in King County have the highest average house prices?</p>
**Inner Factors**: What specific house features (e.g., square footage, number of bedrooms) have the most substantial impact on the sale price?</p>
**External Factors**: How do external elements such as crime rates, school ratings, and demographic data affect house prices in King County?</p>
**Goal**: </p>
My goal is to support potential investors and homebuyers in making well-informed decisions by offering them data and insights gathered through the comprehensive analysis of the King County real estate market. Moreover, we aim to cultivate a more confident home-buying experience, assisting them in navigating the market with certainty and success..</p>

## DATA USED FOR THIS PROJECT
<img width="524" alt="Screenshot 2023-09-15 at 23 33 18" src="https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/80e45a9b-f518-49b8-9b74-205eb25274a5"></p>
The 'House Sales in King County, USA' dataset from Kaggle was selected to analyze house sales data. This dataset encompasses sales from May 2014 to May 2015 and includes 21 variables, with over 21,000 rows of data, each representing a single house sale. I downloaded it in CSV format and removed unnecessary columns, retaining only essential columns such as price, bedrooms, bathrooms, square footage of living space, square footage of the lot, floors, view, condition, grade, year built, and zip code.</p>

To enhance our analysis, I incorporated location-based data by sourcing tables from federal and state databases. This additional data brought in crucial factors such as property tax rate, the number of crimes, school ratings, unemployment rate, average commute time, median household income, total population, and median age. I then merged five different datasets based on zip codes to construct a comprehensive dataset for predicting house prices. To review the process of merging the datasets, you can check my GitHub under the 'data merging' folder.</p>

## DATA PROCESSING
<img width="1083" alt="Screenshot 2023-09-16 at 19 47 30" src="https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/cd924ff8-bd83-4a1b-b3ca-1d49543626ea"></p>
The data tool that I used for data cleaning and modeling is Python. To clean the dataset, I identified missing values and duplicates, handled incorrect data types and values, and applied log transformation to the 'price', 'sqft_living', and 'sqft_lot' variables. I chose this transformation method for these three variables because their distributions tended to be more normally distributed after the transformation, compared to removing outliers. The variables that I will use for my models are 'price_log', 'condition', 'grade', 'floors', 'bedrooms', 'bathrooms', 'sqft_living_log', 'sqft_lot_log', 'house_age', 'school_rate', 'unemployment_rate', 'travel_time_to_work', 'total_population', 'typical_levy_rate', 'median_age', 'median_household_income', and 'area_crime'. To review the details of the data cleaning process, you can check my GitHub under the “Data Cleaning” folder.</P>

## METHODOLOGIES
<img width="1106" alt="Screenshot 2023-09-15 at 23 40 18" src="https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/85cc1e93-43cc-477d-ae25-92f9978312f9">
In the effort to analyze the King County real estate market meticulously and aid potential investors and homebuyers in making informed decisions, selecting appropriate analytical methods is important.

Firstly, Exploratory Data Analysis (EDA) is chosen as a foundational step in the analytical process. EDA will facilitate the initial understanding of the dataset, helping to identify the primary trends, patterns, and potential factors that influence house prices in King County. By rectifying data errors and selecting crucial features early on, EDA ensures a robust groundwork for the subsequent analytical stages, aligning perfectly with the goal to offer well-grounded insights to the stakeholders.</p>

Following EDA, the Multiple Linear Regression (MLR) method is employed to build predictive models for house sale prices. MLR stands out for its ability to create clear and understandable models, which is essential in conveying insights to potential investors and homebuyers who may not have a background in data science. Moreover, it enables the identification of impactful variables, directly answering the business questions regarding the inner and external factors affecting house prices.</p>

Lastly, the XGBoost algorithm is incorporated to enhance the predictive accuracy of the models further. This method is known for its high predictive accuracy, automatically handling missing data, and highlighting important features in the dataset, thus providing a more rounded and reliable analysis. It aligns with the project's goal by ensuring the insights derived are based on a thorough analysis, fostering confidence in the homebuyers and investors regarding the decisions they make based on the insights provided.</p>

## EXPLORATION
### City VS Price
<img width="1087" alt="Screenshot 2023-09-15 at 23 41 39" src="https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/ce078374-8bfa-42b1-b48d-06ce25902d5d"></p>
**Insights**:
- The top five cities with the highest average house prices are Medina, Mercer Island, Bellevue, Sammamish, and Redmond.</p>
- A significant portion of the houses are located in Seattle.</p>

### Bedrooms VS Price
![bed](https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/79373b08-9e3b-4e38-81ea-55b9f51ad830)
**Insights**:
- A large number of houses in the dataset feature three bedrooms.
- Generally, more bedrooms result in a higher house price. However, houses with 0, 11, and 33 bedrooms are exceptions. During deep exploration, I identified that these houses have impractical layouts, which affects the dataset accuracy
- To maintain data integrity, it is recommended to remove entries with 0, 11, or 33 bedrooms.

### Bathrooms VS Price
![bathrooms](https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/a7748a79-12f8-49de-b012-60d155f49ef7)
**Insights**:
- The prevalent bathroom configuration is 2.5 bathrooms per house..
* Similar to the bedrooms, a higher number of bathrooms tends to increase the house price. However, houses with 0 and 7.5 bathrooms are exceptions. During deep exploration, I identified that these houses have impractical layouts, which affects their pricing
* To maintain data integrity, it is recommended to remove entries with 0 or 7.5  bathrooms.

### Floors VS Price
![floors](https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/fdd65c74-29d7-44d3-8827-1f044d8f9b3e)
**Insights**:
* Most houses are designed with one or two floors.
* Houses boasting 2.5 floors fetch the highest average prices in the market.

### Condition VS Price
![condition](https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/2bfb2f6b-f5ae-4e72-845a-098762045a37)
**Insights**:
* A large swath of houses has been awarded a condition score of 3.
* The average house prices don't vary much for homes with condition scores between 3 and 5.

### Grade VS Price
![grade](https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/29a803cd-44bc-4ce8-b219-5be472c1b287)
**Insights**:
* The majority of houses receive a grade score of 7.
* A direct correlation exists between the grade score and the house price, with a higher grade denoting a higher price.
## MODEL COMPARISON
<img width="1002" alt="Screenshot 2023-09-16 at 00 01 41" src="https://github.com/WuCandice/King-County-House-Price-Prediction/assets/127648422/91549de3-7896-4b89-9af8-ac0ab483b0e5"></P>
I leveraged MLR and XGBoost algorithms to develop predictive models for inner factors, external factors, and overall factors. Above are the best performances from each method for different independent variables.</p>
**Insights**:</P>
- **Inner Factors**:</P>
Both models emphasized that the variables sqft_living_log, sqft_lot_log, grade, and bathrooms consistently exert a significant impact on house prices. However, they displayed low R-squared values, hinting at a potentially limited relationship between the inner factors and the predicted outcomes. Before deploying the MLR model, I noticed that each variable had a high Variance Inflation Factor (VIF), which signals potential inaccuracies in the MLR results due to multicollinearity. In this case, where variables are highly correlated, this can skew the results and underrepresent the importance of some variables. Despite my attempts to remove the high VIF variables one at a time, I was left with no variables to analyze. Conversely, an article on Medium highlighted the XGBoost model's adeptness at managing multicollinearity issues effectively, suggesting it might furnish more reliable predictions compared to the MLR model in this context.</p>

- **External Factors**:</P>
Both models showed that the unemployment rate, travel time to work, and median age have a substantial impact on house prices. Yet, they encountered the same issue as in the inner factors analysis, presenting lower R-squared values, each variable having a high Variance Inflation Factor (VIF), and no variables were left for modeling after removing the variables with high VIF one by one.</p>

- **Overall Factors**:</P>
Both models exhibited high explanatory power when considering the overall factors, with XGBoost slightly outperforming MRL. The sqft_living_log and grade variables were significant in both models, highlighting their importance in the prediction.</P>

## Findings
- **Location Insights**</P>
**Top Cities for Investment**: Medina, Mercer Island, Bellevue.</P>
**Seattle**: Major hub with dense housing landscape.</P>
- **House Features**</P>
**Optimal Features**: Homes with 3 bedrooms, 2.5 bathrooms, and 2.5 floors tend to fetch the highest prices.</P>
**Grade**: A higher grade generally correlates with a higher price; the condition score is less influential.</P>
- **Model**</P>
**Inner Factors**: The sqft_living_log, sqft_lot_log, grade, and the number of bathrooms significantly impact house prices.</P>
**External Factors**: The unemployment rate, travel time to work, and median age are significant factors.</P>
**Overall**: The sqft_living_log and grade being pivotal factors.</P>
- **Challenges**</P>
**Multicollinearity**: Present in both inner and external factors, yet better managed by the XGBoost model compared to MLR

## Recommendation
- **Data-Driven Marketing**:</p>
 Utilize the insights derived from the analysis to create data-driven marketing strategies. For example, highlighting the optimal house features (like the number of floors and grade score) in marketing.</P>
- **Advisory Services**: </p>
Offer advisory services to clients, helping them make informed decisions based on the significant factors influencing house prices in King County.</P>
- **Collaborative Efforts**:</p>
Collaborate with local authorities to gather more comprehensive data on external factors such as crime rates and school ratings to further enhance the predictive models.</P>
- **Leveraging XGBoost**: </p>
Recommend leveraging the XGBoost model for predictive analyses given its slightly superior performance compared to the MLR model, especially in handling multicollinearity issues effectively.</P>

## Further Work
- **More sales data**:</p>
The dataset covers the period from May 2014 to May 2015. To reach a more accurate conclusion, it is essential to obtain data that is both more recent and spans a longer period</P>
- **Temporal Analysis**:</p>
Conduct a temporal analysis to understand how house prices have evolved over time and identify any seasonal trends or patterns.</P>
- **Interactive Dashboard**: </p>
Develop an interactive dashboard that allows users to explore the data and insights visually and to generate custom reports based on their preferences.</P>
