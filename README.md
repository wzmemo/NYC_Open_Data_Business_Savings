# Does Being Green = Saved Ultility Costs for Businesses?
This a tool using data from the [2018 NYC Business Savings Data](https://data.cityofnewyork.us/City-Government/Value-of-Energy-Cost-Savings-Program-Savings-for-B/ukdt-xm28) and the [2015 Tree Census](https://data.cityofnewyork.us/Environment/2015-Street-Tree-Census-Tree-Data/pi5s-9p35) to build a simple predictive model to estimate how much a business might <b> save </b> in ulitity costs  if it invested in <b> green initatives </b> like tree planting or enrolling in a business association.

This project is a part of the 2019 NYC Open Data Competition. 

## Step 1 - Load the Data
First, given the size of the NYC Business data, we were directly able to load it using the following code for our analysis:

<img src="https://github.com/wzmemo/Predicting_Business_Savings/blob/master/images/etl_Business2.png" width="1000">

Next, we attempted to load the NYC Tree Census, but given that there are over 680,000 rows, this was not feasible, and we used an optimized function instead. This function downloaded the large CSV in smaller 100,000 row increments that could be more quickly processed by laptops with lower processing power and memory.

## Step 2 - ETL, Clean the data 

The next step was to simply clean the data of any null values, any unimportant values, for instance like "tree stumps" in the tree dataset, and to remove any unused categories.

Importantly, Savings was given in aggregate over the entire existence of the business so, we needed to standardize the savings by address. We created a normalized calucated category that gave the savings of a particular business for one month only ("Periodic Savings Over Months"). <b> We would predict for this normalized monthly savings </b>

Lastly, we created two more categories (1) monthly savings of addresses in a 0.5 miles radius and (2) tree count in a half-mile radius from the address. Our prepared data consisted of both categorical and continuous data.

<img src="https://github.com/wzmemo/Predicting_Business_Savings/blob/master/images/prepared_data.png" width="800">

## Step 3 - Training the Model
There are two ways to take this analysis.
- I experimented with doing regression on continuous and coded categorical variables but that turned out to be a little unwiedly and out of scope of this project. 
- I instead opted to do regression on our three coninuous variables
Our training data consisted of 

<img src="https://github.com/wzmemo/Predicting_Business_Savings/blob/master/images/training_data.png" width="800">

## Further Steps
- If we had more time, we would like to have optimized the model further because we suspect that there is a model that drastically reduces variance and bias.
- I originally worked on coding the different categorical variables into our model and is an interesting way to make our tool more powerful and relevant

## Team Atlas Members
- William Zeng
- Paloma (Haige) Cui
- Paige (Zipei) Wang

## Special Thanks to
- Roy Hyujin Han of Cross Compute
- Ying Zhou of QC Tech Incubator
