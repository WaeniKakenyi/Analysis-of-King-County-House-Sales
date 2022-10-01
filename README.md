# King County Housing Sale Price Analysis
## Overview
An association of home owners are seeking to know what features in a house could be remodelled to increase the house prices and what features they should add as they list their houses in the market. I will be providing insights on  the best remodeling options for them and what features to highlight when selling their houses.
## Problem Statement
- The main goal of the project is to find the features that should be considered when building, renovating or selling a house.
## Data Understanding
The project used the King County House which can be found under [data](data/kc_house_data.csv) and the description of the columns is as below:
* `id` - Unique identifier for a house
* `date` - Date house was sold
* `price` - Sale price (prediction target)
* `bedrooms` - Number of bedrooms
* `bathrooms` - Number of bathrooms
* `sqft_living` - Square footage of living space in the home
* `sqft_lot` - Square footage of the lot
* `floors` - Number of floors (levels) in house
* `waterfront` - Whether the house is on a waterfront
  * Includes Duwamish, Elliott Bay, Puget Sound, Lake Union, Ship Canal, Lake Washington, Lake Sammamish, other lake, and river/slough waterfronts
* `view` - Quality of view from house
  * Includes views of Mt. Rainier, Olympics, Cascades, Territorial, Seattle Skyline, Puget Sound, Lake Washington, Lake Sammamish, small lake / river / creek, and other
* `condition` - How good the overall condition of the house is. Related to maintenance of house.
  * Rated 1-5 from poor to very good
* `grade` - Overall grade of the house. Related to the construction and design of the house.
  * Rated 1-13 from poor to excellent
* `sqft_above` - Square footage of house apart from basement
* `sqft_basement` - Square footage of the basement
* `yr_built` - Year when house was built
* `yr_renovated` - Year when house was renovated
* `zipcode` - ZIP Code used by the United States Postal Service
* `lat` - Latitude coordinate
* `long` - Longitude coordinate
* `sqft_living15` - The square footage of interior housing living space for the nearest 15 neighbors
* `sqft_lot15` - The square footage of the land lots of the nearest 15 neighbors

Conditions were rated as:
    "Poor": 0,
    "Fair": 1,
    "Average": 2,
    "Good": 3,
    "Very Good": 4
Views were rated as:
    "NONE": 0,
    "FAIR": 1,
    "AVERAGE": 2,
    "GOOD": 3,
    "EXCELLENT": 4
The method employed was as follows:
    - The datasets were imported and the dataset preparation was done.
    - Missing were handled by dropping affected columns or filling with the mode of the data depending on the scenario
    - Duplicated data were dropped and only the first instance of the duplicates was kept
    - The cleaned data was used to analyze and answer the problem statement
    - The models were used to answer the problem statement
    - A recommendation was made    
## Modelling
The price distribution was ![Price distribution](images/price%20density%20distribution.png)
It is seen that the price is skewed
The correlation between different features was ![correlation](images/price%20heatmap%20correlation.png)
The features highlighted are ![continuous variables](images/price%20vs%20sqft_living.png) 
The model distribution of variables was ![linear dist](images/model3%20partial%20regression%20plot.png) 
The homoscedasticity check was ![image](images/Model%20three%20Homoscedasticity%20check.png)
It was seen that as grade and view were seen to affect the prices greatly
## Regression Results
* The overall model explains about 65.4% of the variance in the prices. 
* The model is off by about $141,119 in price
* All coefficients are statistically significant
* Compared to grade 3, grades 4,5,6 and 7 have a price decrease
* Compared to grade 3, grades 9,11,12 and 13 have a price increase with grade 13 having the most increase
* Compared to view 0, views 1,3 and 4 have a price increase with view 4 having the most
## Conclusion
#### Recommendations:
* Houses with a waterfront are set to increase the price by $517,800
* The types of view, compared to having no views would be having a house having a view quality of 1 which is considered fair as it would increase the price by $122,500 and should one want the best view at wuality of 4, they would see an increase in price by $286,500
* When it comes to building materials, one should go with the rating that is more than average to increase the sale as excellent grade increases price by $1,923,000

## Limitations and Next Steps
The model fits about 65% of the data and additional tests to check for normality and scaling of features should be considered.
Also, for future research, deployment of other models besides the regression would be best and the data needs to be analysed while zoning in on specific zipcodes so as to get more accurate and fine tuned results

## For more information
See the full analysis in the [Jupyter Notebook](https://github.com/WaeniKakenyi/MAnalysis-of-King-County-House-Sales/blob/master/house_analysis.ipynb) or review this presentation.

For additional info, contact Medrine Waeni at [medrinewaeni@gmail.com](mailto:medrinewaeni@gmail.com)

## Repository structure
```
├── data                                        <- Both sourced externally
├── images                                      <- Both sourced externally and generated from code
├── README.md                                   <- The top-level README for reviewers of this project
├── King County Price Analysis.pdf              <- PDF version of the Tableau work up
├── house_analysis.ipynb                        <- Narrative documentation of analysis in Jupyter notebook
├── notebook.pdf                                <- PDF version of Jupyter notebook
├── presentation.pdf                            <- PDF version of project presentation
```





