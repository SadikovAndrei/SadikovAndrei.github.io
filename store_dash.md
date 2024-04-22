### Creating a dashboard with light/dark mode toggle
<img src="images/store_dash.gif?raw=true"/>

### 1. The Retail Store Sales dataset was taken from from [kaggle](https://www.kaggle.com/datasets/mohammadtalib786/retail-sales-dataset)
### 2. The Power BI dashboard was created
<img src="images/light_store_dash.gif?raw=true"/>
<img src="images/dark_store_dash.gif?raw=true"/>
### 3. The to create dark mode option:
I've created an additional table
<img src="images/table.png?raw=true"/>
Added slicer
<img src="images/slicer.png?raw=true"/>
Added measures with if function oriented on the slicer
```DAX
Background Vis = IF(
    SELECTEDVALUE(
        'Mode Selection'[Mode]) = "Light",
        "#ffffff",
        "#303036"
)
```
Adjusted visualization formats to change automatically according to the measure
