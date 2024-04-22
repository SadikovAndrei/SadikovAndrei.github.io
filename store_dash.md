### Creating a [dashboard](https://github.com/SadikovAndrei/Dark-Mode-Power-BI-dashboard/blob/a160b022fc75d42ac139d49f7c1c7f5837d8d033/BI/Store%20sales%20Dashboard.pbix) with light/dark mode toggle
<img src="images/store_dash.gif?raw=true"/>

### 1. The Retail Store Sales dataset was taken from from [kaggle](https://www.kaggle.com/datasets/mohammadtalib786/retail-sales-dataset)
### 2. The Power BI dashboard was created
<img src="images/light_store_dash.png?raw=true"/>
<img src="images/dark_store_dash.png?raw=true"/>
### 3. To create dark mode option:
- I've created an additional table
<br><br>
<img src="images/mode_table.png?raw=true"/>

- Added slicer
<br><br>
<img src="images/mode_slicer.png?raw=true"/>

- Added measures with if function oriented on the slicer
```DAX
Background Vis = IF(
    SELECTEDVALUE(
        'Mode Selection'[Mode]) = "Light",
        "#ffffff",
        "#303036"
)
```
- Adjusted visualization formats to change automatically according to the measure
At this stage the switch is already working, all that's teft is to add a toggle button which is not that straight-forward.
### 4. Toggle button creating
- Create a bookmarks in this manner (The groupped one should be the switch itself)
<br><br>
<img src="images/bookmarks.png?raw=true"/>
- Pass the following settings
<br><br>
<img src="images/deselection.png?raw=true"/>
- Set the needed parameters in the Style section for defualt, selected, etc. states of the toggle.
<br><br>
<img src="images/toggle_style.png?raw=true"/>
- The last step is to switch the mode slicer and update the bookmarks in the bookmars menu
-Your toggle is ready 🥳🎉🎊
<br><br>
<img src="images/toggle.png?raw=true"/>







