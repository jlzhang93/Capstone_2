# Capstone_2 Great Energy Predictor

Use colab or ineractive brower to see plotly plots.

## Background

Significant investments have been made to improve building efficiencies to reduce costs and emissions, but assessing the value of energy efficiency improvements can be challenging as there's no way to truly know how much energy a building would have used without the improvements. Current methods of estimation are fragmented and do not scale well or are not generalizable to different specific meter types across various building types.
There are two key element to develop energy saving: first we need to be able to forecast future energy usage without improvement, and we also need to predict energy use after a specific set of improvement have been implemented. One issue hindering the growth of energy markets are the lack of cost-effective, accurate and scalable procedures for forecasting energy use.
The best we can do is to build counterfactual models. Once a building is overhauled the new (lower) energy consumption is compared against modeled values for the original building to calculate the savings from the retrofit. More accurate models could support better market incentives and enable lower cost financing.

## Potential Clients

With better estimates of these energy-saving investments, large scale investors and financial institutions will be more inclined to invest in this area to enable progress in building efficiencies.

## Data Source

https://www.kaggle.com/c/ashrae-energy-prediction/data
Data across four energy types based on historic usage rates and observed weather were collected. This dataset includes three years of hourly meter readings from over one thousand buildings at several different sites around the world.
`train.csv`
building_id - Foreign key for the building metadata.
meter - The meter id code. Read as {0: electricity, 1: chilledwater, 2: steam, 3: hotwater}. Not every building has all meter types.
timestamp - When the measurement was taken
meter_reading - The target variable. Energy consumption in kWh (or equivalent). Note that this is real data with measurement error, which we expect will impose a baseline level of modeling error. (UPDATE: the site 0 electric meter readings are in kBTU)
`building_meta.csv`
site_id - Foreign key for the weather files.
building_id - Foreign key for training.csv
primary_use - Indicator of the primary category of activities for the building 
square_feet - Gross floor area of the building
year_built - Year building was opened
floor_count - Number of floors of the building
`weather_train.csv`
Weather data from a meteorological station as close as possible to the site.
site_id
air_temperature - Degrees Celsius
cloud_coverage - Portion of the sky covered in clouds, in oktas
dew_temperature - Degrees Celsius
precip_depth_1_hr - Millimeters
sea_level_pressure - Millibar/hectopascals
wind_direction - Compass direction (0-360)
wind_speed - Meters per second

##  Project Approach

There are missing values and incorrect data in the .csv files, so data cleaning is a necessary step. Data exploratory analysis will be done, and useful features and DataFrame in proper formats will be generated through data wrangling. Regression models will be tried to predict energy use.

## Deliverables

Python scripts and summary report.

