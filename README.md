# NYC Realty Estate Analysis


💻 **Programming Language:** R, Advanced Excel, SQL <br>
📚 **Libraries:** tidyverse, lubridate, dplyr, DBI, odbc, Excel Solver <br>
📌 **Professional Ability:** Connect db, JOIN TABLE, Data Cleaning, Exploratory Data Analysis, Data Visualization, Correlation Analysis, Data Modeling, Time Series, Regression Forecast <br>
<br>

## Executive Summary

This analysis report aims to determine the feasibility of establishing a real estate firm in the Baychester District of New York. To accomplish this, I utilized NYC Real Estate SQL data, along with tools such as R Studio, Power BI, and Advanced Excel. The report follows a comprehensive approach, beginning with descriptive analytics for data exploration, followed by predictive analytics using Time Series and Regression forecast models to predict future sales performance. Finally, prescriptive analytics utilizing Excel Solver is employed to assess the profitability of opening an office.<br>
Historical data shows residential sales in Baychester significantly surpass commercial sales: $120.7 million versus $29.76 million. Using a regression forecasting model, we projected residential sales for the next eight quarters (2022-2023), expecting approximately $1,093,024 in revenue. However, considering costs (initial investment, office space, labor, marketing), our estimated net present value of profit is around $430,000, with a 65% return on investment. Opening a Baychester office, focusing on residential sales, appears favorable. Practical aspects include limited manpower with only three employees and the need for in-depth risk analysis before making a final decision.<br>


## Objectives

<li>Determine what type of realty to open<br>
Choose between residential, commercial, mixed-use, or a combination of realty services based on the assigned neighborhood.<br>
<li>Assess the market<br>
  Justify the business's capital requirements to lenders by highlighting the demand for services, expected growth, and the potential for profitable
  operations with satisfactory revenue levels.<br>
<li>Strategic location<br>
  Minimize expenses and maximize efficiency by avoiding heavy competition and reducing travel time for agents. This ensures higher productivity, 
  minimizes opportunity costs, prevents employee fatigue, saves on travel expenses, increases the frequency of closed sales, and establishes expertise in 
  the chosen locale.<br>


## Data Overview

The NYC Real Estate Dataset was from the Boston University MET Lab SQL Server database. We will use 4 entities for analysis: Borough, Neighborhood, NYC transactions, and Building classification. It contains information such as building number, neighborhood area, year of construction, address, date of sale (2009 to 2021), gross profit per square meter, etc.<br>

<details>
<summary>ERD Diagram</summary>
<br>
<img width="405" alt="image" src="https://github.com/HsinFangHu/NYC-Realty-Estate-Analysis/assets/135067776/7ca42d75-2003-45ac-bae3-f97a3d498788">
<br>
BOROUGH<br>
Primary Key: BOROUGH_ID<br>
<br>
NEIGHBORHOOD<br>
Primary Key: NEIGHBORHOOD_ID<br>
Foreign key: BOROUGH_ID<br>
<br>
NYC_TRANSACTION_DATA<br>
Foreign key: NEIGHBORHOOD_ID, BUILDING_CODE_ID<br>
<br>
BUILDING_CLASS<br>
Primary Key: BUILDING_CODE_ID<br>
</details>


## Exploratory Data Analysis

<li>Residential and Commercial Sales of Baychester<br>
In the last year 2021, Baychester's residential sales totaled a whopping $120.7 million. Commercial sales were only $29.76 million compared to residential sales. Therefore, residential type should be targeted to open in this area.<br>
<br>
<li>Commission of Baychester<br>
Suppose the real estate company earns a commission of 5 cents per dollar on residential sales; then the total revenue earned in Baychester over the last year is $6.03 million for our company. The calculation formula in Power BI as follows:<br>
Commission = SUMX(NYC_TRANSACTION_DATA, NYC_TRANSACTION_DATA[SALE_PRICE]*.05)<br>
If the company achieves 12.5% market penetration in Baychester, the revenue would be $754.37 thousand. And the calculation formula in Power BI as follows:<br>
Penetration = SUMX(NYC_TRANSACTION_DATA, NYC_TRANSACTION_DATA[SALE_PRICE])*0.05*0.125<br>
<br>
<img width="424" alt="image" src="https://github.com/HsinFangHu/NYC-Realty-Estate-Analysis/assets/135067776/257f2f8a-fa9c-4d28-8930-edd30ded547b">


