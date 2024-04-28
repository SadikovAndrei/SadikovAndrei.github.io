### Creating a [countries dashboard](https://github.com/SadikovAndrei/Countries-Dash.git) with KPIs and advanced graphs
<img src="images/countries_gif.gif?raw=true" style="clip-path: inset(0px 50px 0px 50px);"/>

### 1. Preprocessing
The idea is to create a dashboard showing a population growth, GDP, other data and flags.
So here are sorce links:

[GDPs](https://www.kaggle.com/datasets/joebeachcapital/gdp-in-usd-by-country-and-year-1960-2022)
<br><br>
[Flags](https://www.kaggle.com/datasets/andreshg/countries-iso-codes-continent-flags-url)
<br><br>
[Population growth](https://www.kaggle.com/datasets/deeplyft/world-population-growth-annual)
<br><br>
[Additional data](https://www.kaggle.com/datasets/nelgiriyewithana/countries-of-the-world-2023/data)
```Python
df_gdp = pd.read_csv('/content/Historical GDP in USD by Country and Year.csv')
df_flags = pd.read_csv('/content/countries_continents_codes_flags_url.csv')
df_growth = pd.read_csv("/content/The_World_Bank_Population_growth_(annual_).csv")
df_world_data = pd.read_csv('/content/world-data-2023.csv')
```
The data was pulled from 4 Kaggle datasets, so much standartizing work was required:
- Removing duplicates
- Setting datatypes in order
- Dropping excess columns
- Standardizing Country names in all 4 datasets to match by comparing them
  
```Python
difference1 = set(world_countries_list) - set(gdp_countries_list)
difference1
difference2 = set(gdp_countries_list) - set(world_countries_list)
difference2
```
-Exporting to csv files
### 1. Importing the data sets to Power BI
-Importing the datasets
-Creating a pivot tables from growth and GDP datasets for the sake of usability
-Setting relationships
-The ERD we got:
<img src="images/countries_ERD.png?raw=true"/>
-changing datatypes of columns if needed (for example: image url for flag image url)
-After formatting, designing addind supporting tables for KPIs, filling missing or outdates flag urls:
<img src="images/countries_dash.png?raw=true"/>





