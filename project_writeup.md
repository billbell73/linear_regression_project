## Regression Module Project - Predicting prices of used Porsche 911 sports cars listed on autotrader.co.uk

### Abstract

This project was in two parts. The first part was to obtain a viable dataset containing prices and features of listed used Porsche 911's as a result of scraping the autotrader.co.uk website. The next part of the project was to investigate predicting the listing prices of the cars via regression models, using the features obtained.

### Design

The motivation behind this project was that I thought it would be an interesting challenge to try to model the wildly varying prices of listed used Porsche 911's (i.e. from £8,950 to £495,990). I also thought that autotrader.co.uk - as a well-engineered, high traffic site - would be a good target for web-scraping. 

### Data
* When I performed the scraping on autotrader.co.uk on 10/26/21, there were 1742 Porsche 911 cars listed on autotrader.co.uk
* The listings vary in terms of how much data they contain. Some listings have a lot of potential features but a significant number have only the following basic information: 
  * Mileage, Engine size, Number of doors, Number of cylinders, Top speed, 0-6Xmph in seconds, Engine power in bhp, registration year, gearbox (e.g. ‘Manual’), fuel type (e.g. ‘Petrol’), body type (e.g. ‘Coupe’)
* There were 1560 cars that had scrapable data for all of the above eleven features.

### Algorithms
#### Feature Engineering and Target Transformation
1. Converting categorical features to binary dummy variables
2. Eliminating strongly collinear features
3. Eliminating features with no significance
4. Creating ratio features to avoid losing data in attempts to reduce collinearity
5. Use of sklearn preprocessing tools for polynomial and interaction term creation.
6. Target transformations using logarithmic, Box Cox and Quantile methods.

#### Models, data splitting and model selection
* Types of regression performed: OLS, Lasso, Ridge, ElasticNet 
* The dataset of 1560 full records was split into 80/20 train vs. hold out. Most regressions used cross-validation on the training portion. Predictions on the 20% holdout were limited to the very end.
* In total I performed 27 different regressions. Details are reported in a spreadsheet which is included in the appendix of the project presentation.
* Generally the best predictive models used numerous auto-generated polynomial and interaction features and a power transformation of the target variable.
* As a result there was a significant trade-off between accuracy and interpretability when it came to model selection: i.e. the most accurate models were not very interpretable. For the purposes of this project, accuracy was strongly preferred (understanding which features influence price seems very secondary to the overall goal of trying to predict prices accurately).

#### Most accurate predictive model and future work
* The most accurate model was one with 45 features and a Box Cox transformation of the target variable. On the held-out data this produced a mean absolute error of predictions of £7813.63 and r-squared value of 0.853.
* Given a mean listing price of £79,177, it is suggested that the accuracy level of this best model is still relatively poor.
* Further helpful data (for example on the condition of the car) and better modelling may well lead to better predictions, but it is also possible that data science can only get so far in this problem space. There may be a significant element of fundamental unpredictability in the way people come up with listing prices for these ultra-luxury goods.


### Tools

* Web-scraping: Selenium and Beautiful Soup
* Data storage: Python Pickle
* EDA and data-readying: Python Pandas
* Modelling: Statsmodels and sklearn
* Visualizations: matplotlib and Seaborn


### Communication
The methodology and results of this project have been communicated via this document, and via a recorded presentation and its slide-deck.