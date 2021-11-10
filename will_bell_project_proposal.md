#Linear Regression Project Proposal

##Question

- How well is it possible to predict the price of a used 'Porsche 911' listed on autotrader.co.uk given other attributes of the car?

## Data Description

 - Data to be scraped from autotrader.co.uk
 - There are circa 1700 used Porsche 911's listed here
 - With listing price as the target variable, I anticipate using the following attributes of each car as features:
   - year of registration
   - mileage
   - body type (e.g. coupe, convertible)
   - gearbox (e.g. manual, automatic)
   - engine size in litres
   - fuel_type (e.g. petrol)
   - number of doors
   - 0-60mph in secs
   - top speed in mph
   - number of cylinders
   - engine brake horsepower

 - Much of the data is available on initial render of a product details page, but the data relating to car's performance requires an API call
 - The product listings pages which contain the urls of the products details pages can be accessed via predictable urls (page number is a parameter)
 
##Tools

- Selenium
- BeautifulSoup
- Pandas
- Numpy
- Scikitlearn
- Statsmodels
- Matplotlib
- Seaborn

## MVP Goal
- An initial linear regression model using only features with numerical values
