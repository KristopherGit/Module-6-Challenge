# <b> Module 6 Challenge </b>

## <b> Proptech - San Francisco Real-Estate </b>

## --------

## Overview

This application was written in order to develop a proptech software solution to analyze properties in the San Francisco housing market that
could potentially be viable investment opportunities for a third party customer(s). If the application and subsequent use alongside the
third party's one-click purchase/rental software proves viable, it could be expanded to other markets.
This application will take in pre-existing historical housing data and implement algorithms to develop charts and outputs
(including data aggregation, interactive visualizations, etc.) that will locate properties that may be viable investment opportunities in the San Fran area.

## Features

This project will take in the following data files and perform subsequent analysis on them, as outlined below:

First, an initial DataFrame that reads all San Francisco Data in is created called sfo_data_df that holds San Fran 'Neighbourhood' data, housing_units (total), prices_per_sqr_foot and gross_rent.

#### 1.) <u>Calculate and Plot the Housing Units Per Year:</u>

    a.) The groupby function will group the data by 'year'. The results will then be aggregated based on the mean of total housing units available.
    b.) The program will then use the hvplot function to plot the housing_units_by_year DataFrame as a bar chart. The x-axis represents the year while
    the y-axis represents the total housing_units.
    c.) A formatted and stylized plot is then displayed to the end user.

#### 2.) <u>Calculate and Plot the Average Sale Prices Per Square Foot (Mean) & Gross Rent (Mean)

    a.) Here, numerical and visual aggregation will be used to calculate the average prices per square foot - displayed as a line graph - superimposed alongside a line graph
    that displays the gross rental prices. Data is grouped by year, then the results averaged (prices_square_foot_by_year and gross_rent)
    b.) A new Dataframe called prices_square_foot_by_year_df is created and the 'housing_units' total is filtered out/not included in the final presented Dataframe.
    c.) Then, hvPlot is utilized to plot the prices_square_foot_by_year alongside gross_rent.

#### 3.) <u>Comparison of the Average Sale Price by Neighbourhood

    a.) This section of the program uses interactive visualizations alongside dropdown widgets to filter and isolate average sales price per square foot by neighbourhood. First,
    a Dataframe is created that groups the original DataFrame by 'year' and 'neighbourhood'. The results are aggregated by the mean of each group.
    b.) The 'housing_units' column is filtered out that distills the DataFrame down to only include data coluns 'sale_price_sqr_foot' and 'gross_rent'.
    c.) An interactive line plot is generated with hvPlot that visualizes both the 'sale_price_sqr_foot' and 'gross_rent'. The x-axis parameter is set to 'year' while
    the y-axis includes both mean price data from sale_price_sqr_foot (sale_price_sqr_foot_mean) and gross_rent (gross_rent_mean).

#### 4.) <u>The Build of an Interactive Neighbourhood Map

    a.) This section of the program allows geospatial organization and visualization of the data via an interactive hvPlot and GeoViews. The neighbourhood_coordinates.csv
    file is read in via the Resources file directory and a Dataframe called 'neighbourhood_locations_df' is generated (indexed by the Neighbourhood).
    b.) Using the original sfo_data_df, a DataFrame called all_neighbourhood_info_df is formed that groups the data by Neighbourhood and aggregated by mean values.
    c.) Next, both the neighbourhood_locations_df and all_neighbourhood_info_df are concat together to form the final all_neighbourhoods_df DataFrame.
    d.) Finally, using hvPlots and GeoViews, a points plot based on the all_neighbourhood_df DataFrame is generated whereby the size parameter uses the "sale_price_sqr_foot",
    and the color parameter indicates "gross_rent".

#### Running the Project

Running the project can be accomplished by accessing the https://github.com/KristopherGit/Module-6-Challenge.git Git Repository and running each section sequentially.

#### Dependencies

No other outside resources are required to run the project except a python engine / python program and the following imported libraries and modules:

i.)
import pandas as pd
import hvplot.pandas
from pathlib import Path

And the following .csv data files located in the parallel hierarchal included 'Resources' folder:

/Starter_Code/Resources/

housing_per_year.csv
neighbourhoods_coordinates.csv
sfo_neighbourhoods_census_data.csv

#### Contributors

C Ringwood
