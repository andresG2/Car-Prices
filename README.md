# Car-Prices


What drives the price of a car?

OVERVIEW

In this application, you will explore a dataset from kaggle that contains information on 3 million used cars. Your goal is to understand what factors make a car more or less expensive. As a result of your analysis, you should provide clear recommendations to your client -- a used car dealership -- as to what consumers value in a used car.

CRISP-DM Framework
To frame the task, throughout our practical applications we will refer back to a standard process in industry for data projects called CRISP-DM. This process provides a framework for working through a data problem. Your first step in this application will be to read through a brief overview of CRISP-DM here. After reading the overview, answer the questions below.
Business Understanding

From a business perspective, we are tasked with identifying key drivers for used car prices. In the CRISP-DM overview, we are asked to convert this business framing to a data problem definition. Using a few sentences, reframe the task as a data task with the appropriate technical vocabulary.

The mileage of the car may influence the buying decision.

The condition of the car over different owners and driven in different locations might be another factor.

The accident history over the years may influence whether the car is in great, medium, or poor condition.

The color of the car may be a small factor, but still plays a role in the decision buying power.
Data Understanding

After considering the business understanding, we want to get familiar with our data. Write down some steps that you would take to get to know the dataset and identify any quality issues within. Take time to get to know the dataset and explore what information it contains and how this could be used to inform your business understanding.

The categories involve the various regions: Sedona, Flagstaff, Mohave county, Phoenix, Little Rock, Yuma, Bakersfield, etc.

The state and zipcode are used for the location.

The catgories involve the car characteristics: The Year, Manufacturer, Cylinders, Model, Type, Size, Fuel are used as major decision categories.

The condition of the car involves:

1. Condition: Excellent, Good, like New.
2. Odometer
3. Title: Clean, Rebuilt, Salvage

VIN: Shown but might not be used.
Data Preparation

After our initial exploration and fine tuning of the business understanding, it is time to construct our final dataset prior to modeling. Here, we want to make sure to handle any integrity issues and cleaning, the engineering of new features, any transformations that we believe should happen (scaling, logarithms, normalization, etc.), and general preparation for modeling with sklearn.

There are many missing values in the dataset, so these will need to be fixed.

df.info()

<class 'pandas.core.frame.DataFrame'>
RangeIndex: 426880 entries, 0 to 426879
Data columns (total 18 columns):
 #   Column        Non-Null Count   Dtype  
---  ------        --------------   -----  
 0   id            426880 non-null  int64  
 1   region        426880 non-null  object 
 2   price         426880 non-null  int64  
 3   year          425675 non-null  float64
 4   manufacturer  409234 non-null  object 
 5   model         421603 non-null  object 
 6   condition     252776 non-null  object 
 7   cylinders     249202 non-null  object 
 8   fuel          423867 non-null  object 
 9   odometer      422480 non-null  float64
 10  title_status  418638 non-null  object 
 11  transmission  424324 non-null  object 
 12  VIN           265838 non-null  object 
 13  drive         296313 non-null  object 
 14  size          120519 non-null  object 
 15  type          334022 non-null  object 
 16  paint_color   296677 non-null  object 
 17  state         426880 non-null  object 
dtypes: float64(2), int64(2), object(14)
memory usage: 58.6+ MB

df.nunique(axis=0)

id              426880
region             404
price            15655
year               114
manufacturer        42
model            29649
condition            6
cylinders            8
fuel                 5
odometer        104870
title_status         6
transmission         3
VIN             118246
drive                3
size                 4
type                13
paint_color         12
state               51

Index(['id', 'region', 'price', 'year', 'manufacturer', 'model', 'condition',
       'cylinders', 'fuel', 'odometer', 'title_status', 'transmission', 'vin',
       'drive', 'size', 'type', 'paint_color', 'state'],
      dtype='object')



Evaluation

With some modeling accomplished, we aim to reflect on what we identify as a high quality model and what we are able to learn from this. We should review our business objective and explore how well we can provide meaningful insight on drivers of used car prices. Your goal now is to distill your findings and determine whether the earlier phases need revisitation and adjustment or if you have information of value to bring back to your client.

The categorical features which influenced the behavior were the following: 'transmission','model','odometer', 'condition', and 'manufacturer'.

The price, odometer, and year with numeric values had a large influnce in the model.

The r square was above 90% with the simple linear regression which means the feature given can be used to check further for the price prediction.

More analysis can be made using the model created, but with caution.

The year, odometer, and type of fuel are major drivers for car prices.

These features still need to compare to other machine learning models, and see whether we get the same results. 

In conclusion, we can use the Ridge Regression or Linear Regression for our optimum modeling analysis. But, Random Forest performed much better with MSE.



Deployment

Now that we've settled on our models and findings, it is time to deliver the information to the client. You should organize your work as a basic report that details your primary findings. Keep in mind that your audience is a group of used car dealers interested in fine tuning their inventory.

The report will show the graphs without the code. Plot explanations will be given that will describe what we are trying

to achive. The model training will be used continuosly, but also new data will be needed to improve the prediction analysis,

and the prediction error of what was expected.

      


